# HyperFrames: comandos de apoio

Referências: [S12]–[S14] e [S19] no arquivo `hyperframes-fontes.md`.

Os exemplos usam Bash/Zsh e caminhos ilustrativos. Execute no diretório correto, preserve o wrapper e a versão fixada pelo projeto e confirme as opções no CLI instalado. Não instale pacotes nem atualize dependências silenciosamente.

## 1. Diagnóstico

```bash
node --version
ffmpeg -version
ffprobe -version
# Usar a instalação / o wrapper existente do projeto:
npx hyperframes --version
npx hyperframes render --help
```

`npx` pode tentar obter um pacote quando ele não estiver instalado. Confirme a instalação existente antes de executar; os comandos não são uma autorização para baixar uma versão arbitrária.

## 2. Inspecionar a fonte

```bash
ffprobe -v error -show_format -show_streams -of json "in.mp4"
```

Leia duração, FPS, codec, dimensões, pixel format, transferência de cor e streams de áudio. Os presets seguintes são para um clipe comum SDR, opaco. HDR e transparência exigem um pipeline apropriado, não conversão silenciosa para 8-bit sem alpha.

## 3. Cópia All-I, mantendo o primeiro áudio quando existir

```bash
ffmpeg -nostdin -n -i "in.mp4" \
  -map 0:v:0 -map '0:a:0?' \
  -c:v libx264 -preset medium -crf 18 \
  -g 1 -keyint_min 1 -sc_threshold 0 -bf 0 \
  -pix_fmt yuv420p \
  -c:a aac -b:a 192k \
  -movflags +faststart "clip-all-i-com-audio.mp4"
```

O `?` torna o primeiro stream de áudio opcional; não cria áudio onde não há. O preset reencoda áudio para AAC e não preserva todas as faixas de um arquivo multitrilha. A opção `-n` impede sobrescrever uma saída existente. Não muda deliberadamente a proporção nem corta a duração.

## 4. Cópia All-I sem áudio, apenas para apoio silencioso

```bash
ffmpeg -nostdin -n -i "in.mp4" \
  -map 0:v:0 \
  -c:v libx264 -preset medium -crf 18 \
  -g 1 -keyint_min 1 -sc_threshold 0 -bf 0 \
  -pix_fmt yuv420p -an \
  -movflags +faststart "clip-all-i-sem-audio.mp4"
```

**`-an` elimina o áudio dessa cópia.** O arquivo original permanece intacto. Em um clipe com fala, prefira o perfil anterior ou uma faixa separada com sincronização verificada.

O All-I pode aumentar bastante o espaço necessário. Use-o quando o diagnóstico justificar; não como conversão compulsória de toda mídia. Para uma cópia H.264 convencional, retire os parâmetros All-I (`-g`, `-keyint_min`, `-sc_threshold`, `-bf`) e teste novamente.

## 5. Extrair uma faixa para mixagem explícita

```bash
# Só execute depois de confirmar que existe o stream de áudio selecionado.
ffmpeg -nostdin -n -i "in.mp4" \
  -map 0:a:0 -vn -c:a pcm_s16le "fala-separada.wav"
```

Depois de inserir o WAV, impeça que a mesma fala seja mixada também do vídeo. Se houver cortes, recodificação temporal ou deslocamentos de timestamp, confira a sincronização; não deduza que duas faixas estão alinhadas apenas pelo nome.

## 6. Verificar a composição

```bash
# Durante a edição, após mudanças estruturais:
npx hyperframes lint

# Gate final; inclui lint, não precisa de outra chamada redundante antes:
npx hyperframes check

# Tempos ilustrativos: substituir pelos pontos de prova do storyboard.
npx hyperframes snapshot --at 0,2,5.5,8.5
```

Examine as imagens produzidas. Não declare inspeção visual realizada só porque os arquivos foram criados.

## 7. Prévia e exportação

```bash
# Abrir para revisão quando o ambiente suportar:
npx hyperframes preview --background

# Exportação de teste apenas quando coberta pelo pedido/autorização:
npx hyperframes render --quality draft --workers 1 \
  --output "renders/preview-v01.mp4"

# Exportação final depois da aprovação, se este preset existir na versão:
npx hyperframes render --quality delivery --workers 1 \
  --output "renders/final-v01.mp4"
```

`draft` e `delivery` são presets da documentação consultada, não flags universais entre todas as versões antigas. O relatório deve informar o preset efetivamente usado. `--workers 1` é um teste de estabilidade de captura; ele não corrige markup incorreto ou áudio removido.

Nunca trate o início de um processo como render concluído. Acompanhe a execução até um resultado verificável. Não envie o projeto para render na nuvem como fallback automático.

## 8. Inspecionar a saída

```bash
test -s "renders/final-v01.mp4"
ffprobe -v error -show_format -show_streams -of json "renders/final-v01.mp4"

# Decodificar todo o arquivo para investigar erros de vídeo/áudio:
ffmpeg -nostdin -v error -xerror -i "renders/final-v01.mp4" -f null -

# Extrair um quadro de prova; use um caminho novo a cada execução.
ffmpeg -nostdin -n -i "renders/final-v01.mp4" \
  -ss 5.5 -frames:v 1 "renders/qa-frame-5_5s.png"
```

No ensaio documentado em `../VERIFICACAO.md`, `-n` com uma saída já existente preservou o arquivo, mas o FFmpeg retornou código 0 e avisou no stderr. Confirme que a saída corresponde à execução atual, examine o log e não trate um arquivo antigo como um novo render.

O exit code é uma evidência técnica, não aprovação estética. Ouça o MP4 e examine os quadros, principalmente mudanças de cena e camadas WebGL.
