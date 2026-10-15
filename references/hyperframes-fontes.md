# HyperFrames: fontes e notas de compatibilidade

Consulta registrada na preparação original: 15/10/2026. URLs apontadas para `main` podem mudar; registre commit ou versão ao integrar ao projeto. As descrições são notas de consulta, não certificação de que uma biblioteca ou exemplo foi executado.

## Fontes primárias

### [S01] Projeto de lançamento original

`https://github.com/heygen-com/hyperframes-launch-video`

README: composição raiz, 17 subcomposições, pastas e sugestão de --workers 1. A wiki fornecida redirecionou para a raiz do repositório.

### [S02] Projetos de lançamento e licenças

`https://github.com/heygen-com/hyperframes-launches`

README: projetos de VFX e website-to-video, Git LFS e distinção entre licença do código e condições dos assets.

### [S03] Composição raiz original e introdução com vídeos

`https://raw.githubusercontent.com/heygen-com/hyperframes-launch-video/main/compositions/glass-intro.html`

Trechos consultados: wrappers de vídeo, pontos de entrada, recorte e expansão da janela. Não executar seus padrões legados sem validar compatibilidade.

### [S04] Website-to-HyperFrames: composição raiz

`https://raw.githubusercontent.com/heygen-com/hyperframes-launches/main/website-to-hyperframes/index.html`

Trechos consultados: montagem de blocos narrativos e sequência de elementos de vídeo.

### [S05] VFX: composição de lançamento

`https://raw.githubusercontent.com/heygen-com/hyperframes-launches/main/vfx-heygen-combined/index.html`

Trechos consultados: composição de efeitos e callbacks temporais. Referência de intenção visual, não um template validado pela extensão.

### [S06] Contrato central HyperFrames

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-core/SKILL.md`

Regras de raiz, timeline registrada, mídia aninhada, IDs, atributos e validação.

### [S07] Subcomposições

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-core/references/sub-compositions.md`

Formato com template, ligação dos hosts e montagem.

### [S08] Atributos de dados

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-core/references/data-attributes.md`

Referência de timing, duração e atributos de composição e mídia.

### [S09] Variáveis e mídia

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-core/references/variables-and-media.md`

Controle de reprodução pelo framework, colocação de mídia e seleção temporal.

### [S10] Determinismo

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-core/references/determinism-rules.md`

Animação dependente do tempo de composição, não de relógio real ou estados imprevisíveis.

### [S11] Keyframes e transições visuais

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-keyframes/SKILL.md`

Wrappers visuais, transforms, máscaras, limites entre movimento e edição temporal.

### [S12] CLI e fluxo de verificação

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-cli/SKILL.md`

Pré-requisitos, check, snapshots, prévia, presets e inspeção da saída.

### [S13] FFmpeg: codecs / libx264

`https://ffmpeg.org/ffmpeg-codecs.html`

GOP e parâmetros de codificação. O efeito efetivo deve ser verificado com a versão do encoder disponível.

### [S14] FFmpeg: streams e seleção de áudio

`https://ffmpeg.org/ffmpeg.html`

-map, stream opcional, -an, -vn e opções de saída.

### [S15] GSAP: disponibilização dos plugins

`https://gsap.com/blog/3-13/`

Disponibilidade gratuita do conjunto, incluindo os plugins antes restritos. Conferir os termos de licença do fornecedor para o uso específico.

### [S16] Adapter Lottie

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-animation/adapters/lottie.md`

autoplay falso, loop explícito, __hfLottie e limitação de offset por instância.

### [S17] Adapter Three.js

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-animation/adapters/three.md`

hf-seek, duração, preparação de assets e busca temporal de mixer.

### [S18] Notas históricas de produção

`https://raw.githubusercontent.com/heygen-com/hyperframes-launch-video/main/HANDOFF.md`

Relatos de quadros pretos e preenchimento de timeline. Têm datas e estados históricos; não substituem o contrato atual.

### [S19] CLI: prévia e render

`https://raw.githubusercontent.com/heygen-com/hyperframes/main/skills/hyperframes-cli/references/preview-render.md`

Opções de captura, workers e exportação.

### [S20] Visão geral oficial

`https://developers.heygen.com/hyperframes-overview`

HTML/CSS/JS para vídeo, exemplos de WebGL e catálogo de componentes.

### [S21] PR sobre os projetos de lançamento

`https://github.com/heygen-com/hyperframes/pull/696/files`

Divulgação documental dos fontes de launch videos; o repositório de destinos foi consultado diretamente.

### [S22] Raiz original: código

`https://raw.githubusercontent.com/heygen-com/hyperframes-launch-video/main/index.html`

Fonte da montagem com data-composition-src, cenas e tempos.

## Diferenças que não devem ser escondidas

O README do lançamento descreve 17 subcomposições, enquanto o HANDOFF contém estados históricos com outra quantidade e duração. Não derive o projeto atual de contagens em notas antigas; confirme nos arquivos e na timeline montada.

O HANDOFF antigo relata um problema de duração resolvido por um tween sem efeito visual. O contrato central consultado descreve o controle da duração da raiz de outra forma. Isso exige diagnóstico da versão e do nível da composição; não uma regra universal de sempre preencher timelines.

A documentação atual apresenta `check` como caminho de validação e mantém nomes antigos como aliases. Respeite o CLI instalado e registre qualquer divergência.

## Evidência registrada na preparação original

Os itens abaixo reproduzem o registro do pacote original; as consultas e os testes não foram repetidos durante a preparação para publicação.

Documentação e trechos de código: consultados online na preparação original.
Clonagem dos repositórios: tentativa falhou por DNS naquele ambiente.
Skill original do usuário e perfil editorial: não lidos.
Render de exemplo HyperFrames: não executado.
Comandos FFmpeg: ver o resultado efetivo em `../VERIFICACAO.md`.
