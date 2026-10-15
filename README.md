# radar-video-social-hyperframes

Extensão para radar-video-social: produção com HyperFrames, animações, vídeo dentro do vídeo e controle de qualidade.

Este pacote acrescenta orientações à etapa audiovisual de uma skill existente. Ele reúne planejamento de movimento, composição, preparação de mídia, áudio, exportação e critérios de revisão. Não contém a skill completa do Radar, instalador, vídeos ou uma composição pronta para renderizar.

Versão do módulo: 1.0. Preparação original e revisão para publicação: 15/10/2026.

## Recursos

- Planejamento de cenas e movimento com GSAP, SVG e, quando necessário, Lottie ou Three.js.
- Vídeo em janela, tela dividida e expansão contínua para tela cheia.
- Política explícita de áudio e comandos FFmpeg para preparar e inspecionar clipes.
- Orientações de sincronização, busca temporal reproduzível, transições e legendas.
- Revisão de quadros, cortes, áudio e MP4 exportado, com registro de evidências.

As regras de pesquisa, escolha de temas, roteiro, perfil editorial, aprovação e publicação continuam sendo as da skill que receber o módulo. O uso é pelo chat com as ferramentas disponíveis, sem exigir configuração de Dot.

## Arquivos

| Arquivo | Conteúdo |
|---|---|
| [SKILL-PATCH.md](SKILL-PATCH.md) | Bloco para incorporar à etapa de produção do `SKILL.md` existente. |
| [references/hyperframes-producao-avancada.md](references/hyperframes-producao-avancada.md) | Orientações de produção, sincronização, animações e critérios de aceite. |
| [references/hyperframes-comandos.md](references/hyperframes-comandos.md) | Exemplos de comandos para mídia, validação, prévia e exportação. |
| [references/hyperframes-fontes.md](references/hyperframes-fontes.md) | Fontes técnicas e notas de compatibilidade registradas no pacote original. |
| [PROMPT-INTEGRACAO.md](PROMPT-INTEGRACAO.md) | Instrução opcional para conduzir uma integração futura em outro projeto. |
| [VERIFICACAO.md](VERIFICACAO.md) | Testes relatados na preparação original, verificações desta revisão e pendências. |
| `.gitignore` | Exclusões para dados privados, credenciais, mídias e arquivos gerados. |
| `README.md` | Apresentação e instruções de integração. |

## Como integrar a uma skill existente

1. Localize o `SKILL.md` real e suas referências. Se houver mais de uma cópia, compare-as e confira links simbólicos antes de editar. Leia o perfil e o estado da produção apenas no ambiente privado.
2. Faça backup dos arquivos que serão alterados e registre seus hashes. Compare possíveis arquivos com nomes iguais antes de copiar ou mesclar conteúdo.
3. Copie os três arquivos `references/hyperframes-*.md` desta extensão para a pasta `references/` da skill, preservando as referências existentes.
4. Incorpore o conteúdo de `SKILL-PATCH.md` à seção de produção do `SKILL.md`. Preserve o nome, o frontmatter e o restante da skill. Se os marcadores do módulo já existirem, atualize o bloco sem duplicá-lo.
5. Confira os caminhos relativos a partir da pasta da skill. Valide as instruções contra a versão instalada e execute um ensaio isolado antes de usar o módulo em produção.

Não renomeie o README ou o módulo para `SKILL.md`. Guardar estes arquivos ao lado do projeto não comprova que a skill os carregará. A integração precisa manter a referência explícita aos módulos.

O [prompt de integração](PROMPT-INTEGRACAO.md) detalha esse procedimento usando caminhos genéricos. Ele deve ser adaptado ao ambiente de destino; nenhuma integração é executada ao clonar este repositório.

## Pré-requisitos e compatibilidade

A integração pressupõe uma skill principal existente e acesso autorizado ao projeto. Para produzir vídeos, é necessário um ambiente HyperFrames compatível, Node.js e FFmpeg/FFprobe. A documentação consultada na preparação original indicava Node.js 22 ou superior; confirme os requisitos da versão efetivamente utilizada.

Use o CLI ou wrapper já fixado pelo projeto. Confira `--help`, atributos de mídia, adapters e presets antes de aplicar os exemplos. `npx` pode baixar um pacote ausente; não o execute para diagnóstico sem antes conferir a instalação. Esta extensão não instala nem atualiza dependências.

GSAP, plugins, Lottie e Three.js só precisam estar disponíveis quando forem usados. Confira versões, imports e termos de cada fornecedor. Os presets de mídia documentados cobrem SDR opaco; HDR, transparência e áudio multitrilha precisam de tratamento específico.

As URLs em `main` podem mudar. Registre a revisão consultada ao integrar. Código de exemplo, marcas e assets podem ter condições de uso diferentes; preserve a origem e confira os termos de cada mídia.

## Verificação e pendências

Na preparação original, o pacote registrou testes FFmpeg com mídia sintética de dois segundos: All-I com e sem áudio, mapeamento opcional, decodificação, proteção de saída e extração WAV. Esses resultados são relatos preservados do pacote, não testes repetidos nesta publicação.

Nesta revisão, foram lidos os sete arquivos recebidos, removidos caminhos pessoais e identificadores editoriais e conferidos os oito arquivos da cópia pública. Foram verificados links locais, referências documentais, marcadores, blocos de código, sintaxe Bash, JSON ilustrativo e padrões comuns de segredos. O escopo e os limites estão em [VERIFICACAO.md](VERIFICACAO.md).

Continuam pendentes a integração em uma skill, a execução do HyperFrames, os ensaios com GSAP/Lottie/Three.js, a renderização e a inspeção audiovisual. Nenhuma dependência foi instalada e nenhum perfil editorial ou conteúdo em produção foi alterado para publicar este pacote.

## Cuidados ao contribuir

Mantenha as alterações no escopo da extensão, preserve comandos e fontes e informe quais testes foram realmente executados. Não inclua perfis editoriais, credenciais, arquivos `.env`, dados de clientes, conversas, backups, mídias ou históricos de projetos privados. Revise os arquivos preparados para commit mesmo com o `.gitignore` ativo.

Nenhuma licença foi escolhida para este repositório. As ferramentas e fontes citadas mantêm seus próprios termos.
