# Journey World
## Decision Log

**Versão:** 1.3

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

**Status desta decisão:** **Revertida** pela entrada abaixo (2026-07-20, mesmo dia — o Product Owner decidiu inverter a chamada após revisar o código e o site publicado).

---

## 2026-07-20 — Revertido: MVP passa a ser a Era 3 (Jardim/Reino/Região/Missão/Storybook + Árvore do Crescimento)

**Decisão:** A entrada anterior ("MVP = modelo de abas (Era 2)") é revertida por decisão explícita do Product Owner. O MVP ativo passa a ser a arquitetura da Era 3 — Casa → Jardim → **Reino do Piano** → Região → Missão → Conclusão → Storybook, mais a Árvore do Crescimento e uma tela de Configurações — com o único reino jogável sendo o Piano; os demais reinos aparecem sinalizados no Jardim como bloqueados/"em breve", sem conteúdo real. `docs/product/Charter.md` foi atualizado (v2.0) para refletir esse escopo.

Confirmado explicitamente nesta decisão:
- **Sem** Splash, Login ou Perfil — nem no MVP, nem no curto prazo.
- **Sem** Sistema de XP/Nível separado — **definitivo, não é item de backlog**. A Árvore do Crescimento é quem representa a progressão (não um contador numérico). Isso reverte a decisão de 2026-07-20 "XP passa a ser um contador visível" (ver entrada abaixo) — aquela barra de XP, já implementada no `index.html`, será removida quando chegarmos na implementação. As entradas "XP" e "Nível" foram removidas do `docs/domain/Glossary.md` (não apenas marcadas como fora do MVP).
- Loja, Coleções (Álbum) e Sistema de Eventos continuam no MVP — já implementados, testados, e nada nesta decisão pede para cortá-los (mesmo que `docs/UI/screens/Screen Map.md`, escrito antes desta reconciliação, os listasse como "Funcionalidades Futuras").

**Por quê:** Ao revisar o código publicado e a documentação da Era 3 lado a lado, o Product Owner concluiu que a experiência mais rica (Jardim sinalizando mundos futuros, Reino do Piano com Região/Missão/Storybook, Árvore do Crescimento) é o que o produto deve ser desde o início — não uma segunda fase.

**Reabrir quando:** não aplicável — esta é a decisão vigente. Itens específicos dela (nomenclatura, árvore de crescimento vs. árvore de habilidades, etc.) continuam sendo refinados doc a doc; ver entradas futuras.

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

**Status desta decisão:** **Revertida** pela decisão "MVP passa a ser a Era 3" (acima). Sem Sistema de XP/Nível no MVP — a Árvore do Crescimento assume o papel de representar progressão. A barra de XP já implementada no `index.html` será removida na fase de implementação.

---

## 2026-07-20 — Reward System: removidos "login diário" e recompensas aleatórias

**Decisão:** O trigger "Login diário" foi removido de `docs/systems/Reward System.md`. Os itens "probabilidades", "recompensas aleatórias" e "tabelas de loot" foram removidos do Backlog do mesmo documento.

**Por quê:** Ambos contradizem princípios já congelados sem ambiguidade: `Manifesto.md`/`docs/game-design/GDD/Gameplay.md` proíbem qualquer mecânica que incentive permanecer conectado ao aplicativo (recompensar login recompensaria abrir o app, não praticar piano); `docs/product/Principles.md` proíbe aleatoriedade nas conquistas. Não é uma escolha de design nova — é remover uma contradição direta com regras já aprovadas.

---

## 2026-07-20 — Validação de missão: automática por padrão no MVP

**Decisão:** O comportamento padrão do MVP é validação automática ao concluir uma missão (o que o slice atual já faz). "Modo confiança", validação obrigatória e demais variações configuráveis pelos pais (`docs/systems/Mission System.md`, `Parent Companion.md`) ficam documentados como Visão/V2.

**Por quê:** `Core Gameplay Loop.md`, `GDD/Gameplay.md`, `Mission Screen.md` e `Parent Companion.md` descreviam três comportamentos diferentes para a interação mais central do produto, sem nenhum marcado como padrão.

**Status desta decisão:** **Parcialmente ampliada** pela decisão "MVP passa a ser a Era 3" (2026-07-21): Modo Confiança e as demais opções de validação configuráveis pelos pais entraram no MVP como parte do Painel dos Pais rico (`docs/systems/Parent Companion.md`). O padrão continua sendo validação automática — a mudança é que agora as variações são configuráveis já no MVP, não adiadas para V2.

---

## 2026-07-20 — Direção visual: Design System/Art_Bible vencem sobre Art Direction

**Decisão:** Onde `docs/game-design/Art Direction.md` conflitar com `docs/Art_Bible.md` ou `docs/UI/Design System.md` (ícones preenchidos vs. outline; PNG vs. SVG como formato padrão de interface), prevalece o que já está implementado: SVG para interface e ícones outline arredondados.

**Por quê:** `docs/Art_Bible.md` é a fonte oficial de direção artística segundo o `CLAUDE.md`, mas estava marcada "aguardando definição" enquanto `Art Direction.md` já se autodeclarava oficial com regras conflitantes. `CLAUDE.md` já manda "SVG para interface" como princípio de performance, e é o que o `index.html` já usa.

---

## 2026-07-21 — Resolvido: hierarquia Objetivo / Missão / Sessão, e relação de Eventos com Objetivos/Missões

**Decisão:** Resolve a pendência aberta desde a reversão para a Era 3 (`FOUNDATION.md`, `docs/domain/Game Domain Model.md`, `docs/systems/Mission System.md` — "hierarquia Objetivo/Missão/Sessão ainda em discussão"). O modelo definitivo, fornecido pelo Product Owner:

**Objetivos** — pertencem a um Reino (não a uma Missão). Um Reino pode ter N objetivos. Um objetivo é concluído uma única vez (não recorrente) e permanece registrado após concluído.

Exemplos: "Tocar a primeira música completa", "Ler uma partitura simples", "Dominar as notas naturais".

Isso substitui o modelo anterior do MVP ativo (`docs/domain/Glossary.md` v1.1: "Objetivo = resultado esperado dentro de uma missão"). O modelo antigo é descartado — Objetivo deixa de ser uma subcondição de Missão.

**Missões** — continuam sendo uma única entidade. Um Reino pode ter X missões, configuráveis e dinâmicas. As variações abaixo são apenas características/flags da mesma entidade, nunca entidades separadas: diária, semanal, mensal, única, recorrente, secreta, criada pelos pais, criada pelo sistema, ligada a um evento, opcional. (Isso confirma o que `docs/systems/Mission System.md` já vinha descrevendo em "Tipos de Missão" — resolve a ambiguidade de que pudessem ser entidades distintas.)

**Sessões** — uma Sessão é um registro de prática, ou seja, **Sessão = registro de execução de uma Missão**. O cronômetro é apenas uma das formas possíveis de gerar uma Sessão (não a única, não obrigatória). Uma missão sem cronômetro também gera uma Sessão ao ser concluída, apenas com duração "não aplicável".

Exemplo com cronômetro: Missão "Praticar escalas por 20 minutos" → Iniciar sessão → Timer (opcional) → Encerrar → Sessão registrada (19 minutos).

Exemplo sem cronômetro: Missão "Tocar para a mamãe" → Concluir → Sessão registrada (duração: não aplicável).

Isso **substitui definitivamente** o modelo de `docs/domain/Progression Model.md` (Jornada → Objetivos → **Sessões** → Missões — Sessão como contêiner acima de Missão) e resolve a pendência explícita de `docs/systems/Mission System.md` ("Missão ⊃ Sessões, mas isso pode mudar"). A relação correta é: Missão, ao ser executada, **gera** uma Sessão — não o contrário, e Sessão não é um nível hierárquico entre Objetivo e Missão.

**Eventos** — são ocasionais, configurados pelos pais, e podem gerar Objetivos e Missões (ex.: Evento "Recital da Igreja" → gera Objetivos "Dominar música XPTO" / "Decorar letra" / "Fazer apresentação para os pais" → gera Missão "Praticar música XPTO por 20min"). Ao concluir o evento: registro no Storybook + adesivo comemorativo. Isso confirma e detalha o que `docs/systems/Events.md` já descrevia de forma mais genérica ("objetivos relacionados", integração com Reward System).

**Por quê:** o Product Owner forneceu o modelo completo com exemplos concretos, resolvendo a ambiguidade que existia entre três documentos conflitantes (`World Model.md`, `Progression Model.md`, `Game Domain Model.md`) sobre qual entidade contém qual.

**Impacto na documentação:** `docs/domain/Glossary.md` (fonte única de nomenclatura) foi atualizado: entrada "Objetivo" redefinida, nova entrada "Sessão" adicionada, entradas "Missão" e "Evento" ajustadas. `docs/domain/Goals.md`, `docs/domain/Progression Model.md`, `docs/systems/Mission System.md`, `docs/domain/Game Domain Model.md` e `docs/systems/Events.md` foram reconciliados para não contradizerem este modelo.

**Pendência que continua aberta (não resolvida por esta decisão):** o mapeamento das 12 Etapas pedagógicas (`docs/worlds/piano/Learning Path.md`) para as 7 Regiões narrativas (`docs/worlds/piano/Chapters.md`) — é uma questão de conteúdo/mapeamento, não de hierarquia de entidades.

**Escopo de implementação:** esta decisão resolve o **modelo conceitual**. Não determina, por si só, que Objetivos e Sessões como entidades separadas precisam ser construídas na implementação atual do `index.html` (que hoje trata Missão como item plano, sem Objetivo/Sessão explícitos) — isso é uma decisão de escopo de implementação em aberto, a ser confirmada separadamente com o Product Owner.

---

## Decisões técnicas relacionadas (fora do escopo de game design/economia)

Registradas aqui apenas para referência — são decisões de arquitetura/implementação, que já pertencem ao papel do Claude Code segundo o `CLAUDE.md`:

- Caminhos de documentos corrigidos em `CLAUDE.md`, `README.md` e `CURRENT_STATE.md` (apontavam para arquivos que não existem mais).
- `docs/systems/Character.md` e `docs/systems/House.md` preenchidos com a spec mínima do que já está implementado.
