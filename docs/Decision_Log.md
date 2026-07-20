# Journey World
## Decision Log

**Versão:** 1.1

**Status:** Ativo

**Autor:** Gabriel Chaves (decisões registradas por Claude Code a partir de `ARCHITECTURE_REVIEW.md` e `RECOMMENDATIONS.md`, com autorização de 2026-07-20 para prosseguir)

---

Este documento registra decisões de produto/game design tomadas para resolver contradições encontradas na auditoria crítica de 2026-07-19/20 (`ARCHITECTURE_REVIEW.md`). Cada entrada existe para que a mesma dúvida não seja reaberta em uma conversa futura sem querer.

---

## 2026-07-20 — MVP = modelo de abas (Era 2); Jardim/Reinos/Storybook viram Visão

**Decisão:** A especificação ativa do MVP é a definida por `CLAUDE.md`, `docs/product/Charter.md`, `docs/product/Principles.md`, `docs/game-design/GDD/GDD.md` e `docs/domain/Glossary.md` — Casa com abas (Casa, Missões, Álbum, Loja, Calendário/Eventos), Mundo Piano único, Estrelas + Moedas, loja cosmética, álbum sem aleatoriedade, Painel dos Pais com PIN. É o único modelo com código já implementado e testado ponta a ponta (ver `CURRENT_STATE.md`).

A arquitetura descrita em `FOUNDATION.md` (Casa → Jardim → Reinos → Regiões → Missões → Storybook) e os documentos que a detalham (`docs/domain/Goals.md`, `Progression Model.md`, `World Model.md`, `Tree of Growth.md`, `docs/UI/screens/*`, `docs/mvp/User Flow.md`, `docs/experience/*`) passam a valer como **Visão / Fase 2**, não como MVP. Nenhum desses documentos foi apagado; suas seções "MVP" foram renomeadas para "Visão (pós-MVP)".

**Por quê:** A documentação acumulou duas gerações de design sem que a segunda revogasse formalmente a primeira, criando contradições em quase toda a base de documentos (ver `ARCHITECTURE_REVIEW.md`). A Era 2 já responde à hipótese única do Charter ("a criança quer voltar amanhã?") com uma fração do escopo da Era 3.

**Reabrir quando:** o MVP do Piano for validado com playtest real e o Product Owner decidir avançar para a Fase 2.

---

## 2026-07-20 — Economia: Estrela nunca é gasta; Moeda é o recurso gastável

**Decisão:** Estrela é mérito permanente, nunca é removida nem gasta — apenas comprova marcos e pode ser requisito de desbloqueio. Moeda é o recurso gasto na Loja, nasce da conclusão de missões (inclui a conversão "cada estrela gera moedas" do GDD). `docs/domain/Glossary.md` foi corrigido (entrada "Estrela" e nova entrada "Moeda") para parar de contradizer `Economy.md`/`GDD.md`/o código já implementado.

**Por quê:** `Glossary.md` — documento que o próprio `CLAUDE.md` define como única fonte de nomenclatura — dizia o oposto de todos os outros documentos e do código em produção.

---

## 2026-07-20 — Catálogo da Família fica fora do MVP

**Decisão:** O "Catálogo da Família" e o fluxo de "Pedido de Resgate" (`docs/systems/Economy.md`) — moedas trocadas por sorvete, cinema, passeio, viagem etc. — não fazem parte do MVP. Ficam documentados como Visão/Backlog dentro do próprio `Economy.md`.

**Por quê:** Contradiz diretamente uma regra já congelada em `docs/product/Principles.md` e repetida em `docs/game-design/GDD/GDD.md`: "moedas compram apenas cosmético — nunca vantagem ou progresso". Não é uma funcionalidade necessária para validar a hipótese central do MVP, e adiciona complexidade real (fluxo de aprovação, Inbox dos pais).

**Alternativa mantida em Visão:** se o Product Owner quiser recompensas físicas configuráveis pelos pais no futuro, `FOUNDATION.md` já sugere uma versão mais simples — Estrelas (não Moedas) desbloqueiam recompensas configuradas pelos pais, sem loja/fluxo de aprovação.

---

## 2026-07-20 — XP passa a ser um contador visível derivado de missões

**Decisão:** XP deixa de ser um conceito ambíguo (existe no Glossário/GDD, mas ausente do Progression Model e do slice atual) e passa a ser implementado como um contador simples e visível: cada missão concluída soma XP; o Nível é calculado a partir do XP acumulado (substitui o cálculo anterior, que usava Estrelas diretamente). Não introduz nenhum sistema novo de regras — é a mesma mecânica de progresso que já existia, apenas com o nome e a visibilidade que o Glossário/GDD já pediam.

**Por quê:** `Charter.md`/`CLAUDE.md` já listam XP como item congelado do MVP; `CURRENT_STATE.md` já apontava a lacuna ("XP visível" ausente). Implementar o que já estava especificado é mais simples e menos arriscado do que reabrir e editar o escopo congelado do Charter.

---

## 2026-07-20 — Reward System: removidos "login diário" e recompensas aleatórias

**Decisão:** O trigger "Login diário" foi removido de `docs/systems/Reward System.md`. Os itens "probabilidades", "recompensas aleatórias" e "tabelas de loot" foram removidos do Backlog do mesmo documento.

**Por quê:** Ambos contradizem princípios já congelados sem ambiguidade: `Manifesto.md`/`docs/game-design/GDD/Gameplay.md` proíbem qualquer mecânica que incentive permanecer conectado ao aplicativo (recompensar login recompensaria abrir o app, não praticar piano); `docs/product/Principles.md` proíbe aleatoriedade nas conquistas. Não é uma escolha de design nova — é remover uma contradição direta com regras já aprovadas.

---

## 2026-07-20 — Validação de missão: automática por padrão no MVP

**Decisão:** O comportamento padrão do MVP é validação automática ao concluir uma missão (o que o slice atual já faz). "Modo confiança", validação obrigatória e demais variações configuráveis pelos pais (`docs/systems/Mission System.md`, `Parent Companion.md`) ficam documentados como Visão/V2.

**Por quê:** `Core Gameplay Loop.md`, `GDD/Gameplay.md`, `Mission Screen.md` e `Parent Companion.md` descreviam três comportamentos diferentes para a interação mais central do produto, sem nenhum marcado como padrão.

---

## 2026-07-20 — Direção visual: Design System/Art_Bible vencem sobre Art Direction

**Decisão:** Onde `docs/game-design/Art Direction.md` conflitar com `docs/Art_Bible.md` ou `docs/UI/Design System.md` (ícones preenchidos vs. outline; PNG vs. SVG como formato padrão de interface), prevalece o que já está implementado: SVG para interface e ícones outline arredondados.

**Por quê:** `docs/Art_Bible.md` é a fonte oficial de direção artística segundo o `CLAUDE.md`, mas estava marcada "aguardando definição" enquanto `Art Direction.md` já se autodeclarava oficial com regras conflitantes. `CLAUDE.md` já manda "SVG para interface" como princípio de performance, e é o que o `index.html` já usa.

---

## Decisões técnicas relacionadas (fora do escopo de game design/economia)

Registradas aqui apenas para referência — são decisões de arquitetura/implementação, que já pertencem ao papel do Claude Code segundo o `CLAUDE.md`:

- Caminhos de documentos corrigidos em `CLAUDE.md`, `README.md` e `CURRENT_STATE.md` (apontavam para arquivos que não existem mais).
- `docs/systems/Character.md` e `docs/systems/House.md` preenchidos com a spec mínima do que já está implementado.
