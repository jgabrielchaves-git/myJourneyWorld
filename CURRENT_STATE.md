# CURRENT_STATE

> Última atualização: 2026-07-20

## Onde estamos hoje?

Fase 0 — Fundação. Em 2026-07-19/20, uma auditoria crítica (`ARCHITECTURE_REVIEW.md`) encontrou uma pivotagem de produto não declarada: a documentação acumulou duas gerações — o MVP de abas já implementado ("Era 2": `CLAUDE.md`, `docs/product/Charter.md`, `docs/game-design/GDD/GDD.md`) e uma visão bem maior de navegação Jardim/Reinos/Storybook nunca implementada ("Era 3": `FOUNDATION.md`, `docs/domain/*`, `docs/UI/screens/*`). Isso foi resolvido (`RECOMMENDATIONS.md`, `docs/Decision_Log.md`, 2026-07-20): a Era 2 foi confirmada como MVP ativo; os documentos da Era 3 foram rotulados como Visão pós-MVP (sem apagar nada). Em seguida, três lacunas de escopo do slice foram fechadas (Eventos, XP visível, Missão Semanal) e testadas ponta a ponta num navegador headless, sem erros de console.

## O que já existe?

- Estrutura de pastas completa (`docs/`, `assets/`, `src/`, `prompts/`).
- `README.md` e `CLAUDE.md` na raiz, com os caminhos de documentos corrigidos (apontavam para nomes/pastas que não existem mais).
- Documentação completa do MVP em `docs/product/`, `docs/domain/`, `docs/systems/`, `docs/game-design/` e `docs/UI/`. Os documentos da Era 3 (visão Jardim/Reinos) agora têm uma nota de status "Visão (pós-MVP)" no topo, apontando para `docs/Decision_Log.md`.
- `ARCHITECTURE_REVIEW.md` (auditoria crítica completa) e `RECOMMENDATIONS.md` (leitura, opinião e estratégia de MVP) na raiz.
- `docs/Decision_Log.md` agora populado com as decisões de 2026-07-20 (antes vazio).
- `docs/systems/Character.md` e `docs/systems/House.md` preenchidos com a spec do que já está implementado (antes eram só templates vazios).
- `src/index.html` — o vertical slice integrado, agora baseado em `journey_world_vertical_slice (3).html` do Downloads (timestamp 2026-07-15 01:41, a versão mais recente — substitui a integração anterior baseada no arquivo de 21:25). As variações mais antigas do Downloads (`.html` 21:25, `(1)` idêntica por hash, `(2)` mais pesada de 16:51) não foram usadas.
- Essa versão (3) reverteu duas decisões que existiam na 21:25: a tela de bloqueio obrigatório em paisagem ("Gire o aparelho") foi removida — voltou à degradação suave em retrato (`@media (orientation:portrait)`), o que resolve o conflito com a UX Bible apontado antes; e a foto real do piano voltou a ser a ilustração em SVG.
- `assets/character/` (char-base, char-blink, char-cheer, char-bow) e `assets/avatar/avatar-default.webp` — as 5 imagens embutidas em base64 no HTML foram extraídas para arquivos reais, reduzindo `index.html` de 252 KB para ~48 KB. `src/index.html` referencia todas via caminho relativo (`../assets/...`). Não há mais foto de piano como asset (voltou a ser SVG desenhado no próprio HTML).
- Durante a integração, três bugs foram corrigidos: duas regras CSS duplicadas (`.cta-row` e `.modal`, cada uma com uma segunda declaração parcial redundante mais adiante no arquivo) e uma `<div class="floor-space">` aninhada duas vezes por engano ao redor do SVG do piano.

## O que está funcionando?

- Fluxo completo testado (headless, via Playwright): navegação entre as 5 abas (Casa, Missões, Álbum, Loja, Calendário), completar uma missão (estrelas/moedas/streak atualizam no topo, modal de recompensa aparece), o personagem comemora, um adesivo é desbloqueado automaticamente com seu próprio modal, e o Painel dos Pais abre com o PIN padrão (1234). Nenhum erro de console.
- **Novo (2026-07-20), também testado ponta a ponta sem erros de console:**
  - **XP visível**: barra de XP na Casa, abaixo da saudação (XP = estrelas × 10; Nível = XP / 50, mesma matemática de antes, agora nomeada e visível).
  - **Eventos**: seção "Eventos" na aba Calendário (nome, contagem regressiva, progresso das músicas do repertório escolhidas). Criados pelo Painel dos Pais (nome, data, checklist de músicas). Ao chegar a data, concede +30 moedas automaticamente.
  - **Missão Semanal**: card "Semana Dedicada" na aba Missões — praticar em 5 dias na semana concede +1 estrela e +50 moedas (bônus mesclado no modal da missão do dia).
- Save em LocalStorage, economia (estrelas nunca somem, moedas só compram cosmético), adesivos sem aleatoriedade — conferido no código, consistente com as decisões congeladas abaixo.

## O que falta?

- **Última lacuna de escopo vs. o MVP congelado**: a Árvore de Habilidades do Mundo Piano. O GDD lista 10 áreas (Técnica, Escalas, Acordes, Cifras, Partitura, Ritmo, Repertório, Eventos, Desafios, Mestres); o slice só implementa Repertório. Definir o conteúdo pedagógico das outras 9 áreas é game design/currículo musical — fora do papel do Claude Code (`CLAUDE.md`) — e não foi implementado por não caber a mim decidir. Precisa de decisão do Product Owner sobre o que cada área exige na prática.
- Direção de arte (paleta, personagem, iconografia) — ver [docs/Art_Bible.md](docs/Art_Bible.md), status "em decisão ativa" (ver seção de estilos visuais A/B/C/D/E discutida com o usuário em 2026-07-15). O personagem/avatar já extraídos são ilustrações de exploração/IA, não arte final.
- ~~Configuração de GitHub Pages~~ — decidido em 2026-07-15: serve a partir da raiz do repositório. `index.html` foi movido de `src/` para a raiz (caminhos de assets ajustados de `../assets/` para `assets/`), e `.nojekyll` foi adicionado. `src/` permanece reservado para organização futura do código-fonte caso o projeto cresça além de um único arquivo.

## Qual é a próxima tarefa?

Commit e push feitos em 2026-07-20 — site publicado em https://jgabrielchaves-git.github.io/myJourneyWorld/ já reflete a reconciliação Era 2/Era 3, XP visível, Eventos e Missão Semanal. Próximo passo: decidir com o usuário o conteúdo pedagógico da Árvore de Habilidades (única lacuna restante) e a direção de arte final.

## O que não deve ser alterado?

- Os valores do projeto: acolhimento, progresso, simplicidade, alegria, disciplina, constância (ver [docs/product/Principles.md](docs/product/Principles.md)).
- A lista "nunca utilizar": violência, excesso de efeitos, interfaces poluídas, cores agressivas, excesso de texto.
- O princípio de que recompensas não substituem motivação intrínseca (estrelas nunca são removidas; sem aleatoriedade nas conquistas; moedas compram só cosmético).
- A separação de responsabilidades do [CLAUDE.md](CLAUDE.md): Claude decide arquitetura/implementação; **não** decide gameplay, identidade visual, direção de arte, economia ou game design.

## Quais decisões estão congeladas?

- Stack do MVP: HTML, CSS, JavaScript puro (sem frameworks, salvo necessidade real).
- Persistência: LocalStorage no MVP, com código preparado para migração futura online.
- Primeiro mundo: Piano. Mundos futuros (Ginástica Rítmica, Escola, Família, Virtudes, Jornada Espiritual) ficam no backlog até o MVP do Piano ser validado.
- Escopo fechado do MVP: Casa, Mundo Piano, Missões, XP, Estrelas, Loja, Álbum, Eventos, Painel dos Pais, Save — tudo além disso é backlog (ver [docs/Backlog.md](docs/Backlog.md)).
- Hipótese única a validar: gamificação aumenta motivação/consistência no estudo de piano (ver [docs/product/Charter.md](docs/product/Charter.md)).
- Navegação em abas (não Jardim/Reinos/Storybook) é o modelo do MVP ativo; o modelo de navegação maior é Visão pós-MVP (ver [docs/Decision_Log.md](docs/Decision_Log.md), 2026-07-20).
- Catálogo da Família (moedas trocando por sorvete/cinema/passeio) fica fora do MVP — contraria "moedas compram apenas cosmético" (ver [docs/Decision_Log.md](docs/Decision_Log.md)).
