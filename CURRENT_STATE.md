# CURRENT_STATE

> Última atualização: 2026-07-15

## Onde estamos hoje?

Fase 0 — Fundação, saindo do zero de código. O vertical slice do Mundo Piano (antes só em `~/Downloads`) foi revisado e integrado como base de `src/`. O app roda, foi dirigido ponta a ponta num navegador headless (Casa → completar missão → recompensa → adesivo → Painel dos Pais) sem erros de console, mas ainda tem lacunas de escopo conhecidas (ver "O que falta?").

## O que já existe?

- Estrutura de pastas completa (`docs/`, `assets/`, `src/`, `prompts/`).
- `README.md` e `CLAUDE.md` na raiz.
- Documentação completa do MVP em `docs/00` a `docs/07`.
- `src/index.html` — o vertical slice integrado, agora baseado em `journey_world_vertical_slice (3).html` do Downloads (timestamp 2026-07-15 01:41, a versão mais recente — substitui a integração anterior baseada no arquivo de 21:25). As variações mais antigas do Downloads (`.html` 21:25, `(1)` idêntica por hash, `(2)` mais pesada de 16:51) não foram usadas.
- Essa versão (3) reverteu duas decisões que existiam na 21:25: a tela de bloqueio obrigatório em paisagem ("Gire o aparelho") foi removida — voltou à degradação suave em retrato (`@media (orientation:portrait)`), o que resolve o conflito com a UX Bible apontado antes; e a foto real do piano voltou a ser a ilustração em SVG.
- `assets/character/` (char-base, char-blink, char-cheer, char-bow) e `assets/avatar/avatar-default.webp` — as 5 imagens embutidas em base64 no HTML foram extraídas para arquivos reais, reduzindo `index.html` de 252 KB para ~48 KB. `src/index.html` referencia todas via caminho relativo (`../assets/...`). Não há mais foto de piano como asset (voltou a ser SVG desenhado no próprio HTML).
- Durante a integração, três bugs foram corrigidos: duas regras CSS duplicadas (`.cta-row` e `.modal`, cada uma com uma segunda declaração parcial redundante mais adiante no arquivo) e uma `<div class="floor-space">` aninhada duas vezes por engano ao redor do SVG do piano.

## O que está funcionando?

- Fluxo completo testado (headless, via Playwright): navegação entre as 5 abas (Casa, Missões, Álbum, Loja, Calendário), completar uma missão (estrelas/moedas/streak atualizam no topo, modal de recompensa aparece), o personagem comemora, um adesivo é desbloqueado automaticamente com seu próprio modal, e o Painel dos Pais abre com o PIN padrão (1234). Nenhum erro de console.
- Save em LocalStorage, economia (estrelas nunca somem, moedas só compram cosmético), adesivos sem aleatoriedade — conferido no código, consistente com as decisões congeladas abaixo.

## O que falta?

- **Lacunas de escopo vs. o MVP congelado** (Casa, Mundo Piano, Missões, XP, Estrelas, Loja, Álbum, Eventos, Painel dos Pais, Save) — decisão pendente do usuário sobre cada uma:
  - **Eventos**: não existe nenhuma tela/dado — ausente por completo do slice atual.
  - **XP visível**: o nível é calculado a partir das Estrelas (`Math.floor(estrelas/5)+1`); não há um XP separado e visível na tela, embora a UX Bible peça XP visível como reforço de progresso.
  - **Missões semanais**: só as 3 missões diárias fixas existem; GDD também previa uma trilha semanal.
  - **Árvore de habilidades do Mundo Piano**: o GDD lista 10 áreas (Técnica, Escalas, Acordes, Cifras, Partitura, Ritmo, Repertório, Eventos, Desafios, Mestres); o slice só implementa Repertório (dentro da aba Missões).
- Direção de arte (paleta, personagem, iconografia) — ver [docs/Art_Bible.md](docs/Art_Bible.md), status "em decisão ativa" (ver seção de estilos visuais A/B/C/D/E discutida com o usuário em 2026-07-15). O personagem/avatar já extraídos são ilustrações de exploração/IA, não arte final.
- Primeiro push para `https://github.com/jgabrielchaves-git/myJourneyWorld` — repositório git local já existe (`git init` feito), mas ainda sem remote configurado.
- ~~Configuração de GitHub Pages~~ — decidido em 2026-07-15: serve a partir da raiz do repositório. `index.html` foi movido de `src/` para a raiz (caminhos de assets ajustados de `../assets/` para `assets/`), e `.nojekyll` foi adicionado. `src/` permanece reservado para organização futura do código-fonte caso o projeto cresça além de um único arquivo.

## Qual é a próxima tarefa?

Decidir com o usuário o que fazer com as lacunas de escopo listadas acima (tratar como pendências de backlog imediato ou implementar antes de seguir), e então `git init` + primeiro commit.

## O que não deve ser alterado?

- Os valores do projeto: acolhimento, progresso, simplicidade, alegria, disciplina, constância (ver [docs/Product_Principles.md](docs/Product_Principles.md)).
- A lista "nunca utilizar": violência, excesso de efeitos, interfaces poluídas, cores agressivas, excesso de texto.
- O princípio de que recompensas não substituem motivação intrínseca (estrelas nunca são removidas; sem aleatoriedade nas conquistas; moedas compram só cosmético).
- A separação de responsabilidades do [CLAUDE.md](CLAUDE.md): Claude decide arquitetura/implementação; **não** decide gameplay, identidade visual, direção de arte, economia ou game design.

## Quais decisões estão congeladas?

- Stack do MVP: HTML, CSS, JavaScript puro (sem frameworks, salvo necessidade real).
- Persistência: LocalStorage no MVP, com código preparado para migração futura online.
- Primeiro mundo: Piano. Mundos futuros (Ginástica Rítmica, Escola, Família, Virtudes, Jornada Espiritual) ficam no backlog até o MVP do Piano ser validado.
- Escopo fechado do MVP: Casa, Mundo Piano, Missões, XP, Estrelas, Loja, Álbum, Eventos, Painel dos Pais, Save — tudo além disso é backlog (ver [docs/Backlog.md](docs/Backlog.md)).
- Hipótese única a validar: gamificação aumenta motivação/consistência no estudo de piano (ver [docs/Project_Charter.md](docs/Project_Charter.md)).
