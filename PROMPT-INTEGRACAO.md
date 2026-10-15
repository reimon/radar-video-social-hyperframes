# Prompt para integrar a melhoria à skill real

Use esta instrução no chat/agente que tenha acesso de leitura e escrita à pasta do projeto e ao pacote de melhoria. Os caminhos abaixo são exemplos: substitua-os pelos caminhos reais e informe somente as cópias da skill que existirem no seu ambiente. Este documento orienta uma integração futura; publicar este repositório não executa essas alterações.

```text
Quero melhorar a skill radar-video-social, trabalhando pelo chat, sem Dot.

PROJETO
/caminho/para/projeto-video

SKILLS EXISTENTES
/caminho/para/skills/radar-video-social/SKILL.md
/caminho/para/projeto-video/skills/radar-video-social/SKILL.md

PERFIL
/caminho/para/projeto-video/editorial/profile.json

MATERIAL DA MELHORIA
Use a cópia local desta extensão radar-video-social-hyperframes
ou o pacote radar-video-social-hyperframes-upgrade disponibilizado no chat.
Encontre seu caminho real; não invente um caminho de Downloads ou de anexo.

OBJETIVO
Integrar um módulo avançado de produção HyperFrames, com animações,
vídeo dentro do vídeo, áudio explícito, referências reais e validação de render.
Preservar o restante da skill e o trabalho editorial existente.

1. LEITURA E COMPARAÇÃO
Leia integralmente os dois SKILL.md, o perfil e as referências locais necessárias.
Informe os arquivos efetivamente lidos. Compare as duas skills, inclusive suas
referências; verifique se algum caminho é symlink para não editar o mesmo alvo
como se fossem cópias independentes.
Não substitua uma skill inteira pela outra. Não presuma que sejam iguais.
Se faltar acesso a um arquivo indispensável, relate o bloqueio e não finja a edição.

2. BACKUP E PLANO DE ALTERAÇÃO
Faça backup datado dos arquivos que serão modificados e registre seus hashes.
Leia o pacote completo. Identifique somente os trechos que precisam mudar.
Preserve nome, frontmatter, regras de pesquisa, fontes, métricas, seleção de temas,
perfil editorial, roteiro, aprovação e publicação. Não edite o profile.json
para fazê-lo caber no módulo. Não mova o projeto nem apague históricos.

3. INTEGRAÇÃO
Acrescente o bloco de SKILL-PATCH.md à parte de produção de cada cópia aplicável.
Se esse bloco já existir, atualize-o sem duplicação.
Coloque os três arquivos references/hyperframes-*.md junto a cada skill aplicável,
respeitando a estrutura que ela já utiliza. Resolva todos os caminhos relativos.
Preserve outros arquivos de references/; não sobrescreva a pasta inteira.
Se já houver arquivos com esses nomes e conteúdo diferente, compare e faça merge.
Mostre o conflito quando a escolha alterar uma regra editorial ou aprovação.

4. COMPATIBILIDADE TÉCNICA
Leia a documentação das skills oficiais HyperFrames disponíveis na versão local.
Confirme CLI e bibliotecas. Exemplos de lançamento são referências, não contrato
universal. Não copie hacks antigos sem reproduzir a necessidade.
Não instale ou atualize dependências sem autorização; mantenha versão rastreável.
Não faça uploads de projeto, publique feedback com dados privados ou ative
serviços pagos como parte desta integração.

5. REFERÊNCIAS REAIS
Consulte ou clone os repositórios oficiais indicados no módulo em uma área
separada de referências. Antes de clonar, confira se o destino já existe.
Para hyperframes-launches, considere Git LFS e não confunda ponteiros com mídia.
Não baixe todos os assets sem necessidade. Registre arquivos e revisão realmente
estudados. Aproveite padrões técnicos; não reutilize mídias sem direitos de uso.
Uma falha de rede deve ser reportada, não convertida em alegação de clonagem.

6. VERIFICAÇÃO DA SKILL
Confirme frontmatter válido, links relativos existentes, ausência de blocos
duplicados e preservação do fluxo editorial. Mostre o diff relevante.
Não confunda essa verificação textual com teste do runtime HyperFrames.

7. TESTE DE INTEGRAÇÃO
Sem tocar nos episódios em produção, prepare uma proposta de ensaio curto
em pasta separada: título cinético, vídeo sintético com contador em janela,
expansão contínua para tela cheia, corte e áudio verificável.
Quando o teste local estiver coberto pela autorização da skill existente,
execute-o; caso ela exija aprovação, apresente a prévia/proposta no gate correto.
Teste Lottie e Three.js separadamente quando forem efetivamente incorporados.
Não marque testes não executados como aprovados. Não exporte um vídeo editorial
final nem publique conteúdo sem a aprovação exigida.

ENTREGA
Informe arquivos alterados, localização dos backups, diferenças relevantes entre
as duas skills, versões observadas, verificações realizadas e pendências.
Confirme separadamente: módulo integrado, comandos de mídia testados,
composição renderizada e revisão visual realizada.
```
