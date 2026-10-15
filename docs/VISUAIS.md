# Imagens da documentação

As cinco imagens do README foram criadas para explicar a extensão. São ilustrações conceituais: não mostram a interface real de uma ferramenta, não vieram do projeto privado e não demonstram um render ou teste HyperFrames executado.

| Arquivo | Origem e finalidade |
|---|---|
| `images/capa.png` | Capa original produzida pela ferramenta integrada imagegen. Representação artística de composição, vídeo em janela, timeline e áudio. |
| `images/fluxo-producao.svg` | Diagrama vetorial escrito para esta documentação, com quatro etapas e os pontos de aprovação. |
| `images/video-em-janela.svg` | Storyboard vetorial estático. A paisagem e os contadores são sintéticos e ilustram continuidade entre enquadramentos. |
| `images/movimento.svg` | Storyboard vetorial estático de entrada, explicação e repouso para leitura. |
| `images/qualidade.svg` | Diagrama vetorial de verificações propostas ao redor de um corte e no arquivo exportado. |

Os SVGs são editáveis, têm títulos e descrições de acessibilidade e usam fontes do sistema, sem scripts, dependências ou imagens externas. A renderização dos SVGs para revisão é uma verificação das ilustrações, não uma renderização HyperFrames.

## Direção visual

Fundo azul quase preto, detalhes em ciano e laranja, linhas de timeline e tipografia legível. Cada imagem explica uma parte do fluxo. Os tempos, cenas e estados desenhados são exemplos, sem métricas ou aprovações atribuídas a uma produção real.

## Prompt usado para a capa

Ferramenta: imagegen integrada, sem CLI ou chave de API fornecida pelo usuário. A imagem original foi copiada para `docs/images/capa.png`.

```text
Use case: stylized-concept. Asset type: wide GitHub README hero banner for radar-video-social-hyperframes, an extension about HTML video production, animations, picture-in-picture, timeline synchronization and quality checking. Create a cinematic editorial illustration, ultra-wide 3:1 landscape, with a dark ink background, carefully crafted luminous cyan and warm orange details, fine grid, tactile translucent glass panels, a flowing timeline in perspective, one video window growing into a larger screen, simplified kinetic type blocks and audio waveform. Architectural and precise, beautiful restrained lighting, no stock clipart, no robot, no faces, no logos. Strong asymmetrical composition with about the left 42 percent nearly empty dark negative space. On the left set exactly two large readable text lines in a clean heavy geometric sans serif: 'RADAR VIDEO SOCIAL' and below 'HYPERFRAMES'. Much smaller third line exactly 'MOVIMENTO COM INTENCAO'. All visual objects concentrated to the right and along the bottom. Keep text and critical objects inside generous safe margins. This is an original conceptual documentation illustration, never a screenshot of a real app or an actual render. No claims of tests passing, badges, watermarks or additional text.
```
