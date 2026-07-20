# Journey World — Leitura, Opinião e Recomendações

**Autor:** Claude Code
**Data:** 2026-07-20
**Base:** `ARCHITECTURE_REVIEW.md` (auditoria crítica) + leitura direta de `CLAUDE.md`, `FOUNDATION.md`, `CURRENT_STATE.md`, `README.md`, `docs/product/*`, `docs/development/MVP Design Principles.md`, `docs/domain/Glossary.md`, `docs/game-design/GDD/GDD.md`, `docs/systems/Economy.md`.

> Este documento contém **opinião e recomendações**, não decisões. Nada aqui foi implementado. Por regra do `CLAUDE.md`, eu não decido gameplay, economia ou game design — decido apenas quando a resposta é puramente técnica. Onde a recomendação toca game design/economia/produto, ela é uma sugestão aguardando sua aprovação.

---

# Parte 1 — Minha leitura do projeto

## O que o Journey World realmente é

Por trás da complexidade documental, a ideia central é simples e boa: um filho pratica piano todo dia; o app transforma esse hábito em uma jornada visível, com estrelas que nunca somem, uma casa que conta a história dessa dedicação, e pais que participam como mentores — nunca como fiscais. `Manifesto.md` é o texto mais forte do projeto: "nosso papel não é convencer uma criança a estudar, é fazer com que ela queira voltar amanhã." Todo o resto da documentação deveria servir só a essa frase.

Os princípios de produto são consistentes e bons, e aparecem repetidos (de forma redundante, mas coerente) em quase todo documento fundacional:
- a vida real vem antes do app;
- a criança nunca perde, nunca sente que errou;
- recompensa é mérito, nunca aleatoriedade;
- moedas compram só cosmético;
- pais são mentores, nunca fiscais;
- simplicidade acima de sofisticação.

Esse núcleo filosófico está bem estabelecido e **não precisa de nenhuma correção**.

## O que realmente aconteceu com a documentação

Lendo os documentos em ordem cronológica (pelas datas e pelo que cada um pressupõe já existir), dá para reconstruir a história do projeto:

1. **Era 1 — numerada.** `CURRENT_STATE.md` e `README.md` ainda referenciam `docs/00` a `docs/07` e caminhos como `docs/Project_Charter.md`. Essa estrutura não existe mais no repositório. É a primeira geração de documentação, já abandonada duas vezes.
2. **Era 2 — o MVP congelado.** `CLAUDE.md`, `docs/product/Charter.md`, `docs/product/Principles.md`, `docs/game-design/GDD/GDD.md` e `docs/domain/Glossary.md` descrevem um produto pequeno e coerente: Casa com 5 abas (Casa, Missões, Álbum, Loja, Calendário), Mundo Piano único, Estrelas + Moedas + XP, loja cosmética, álbum sem aleatoriedade, Painel dos Pais com PIN. **Esse é o único pedaço da documentação com código real por trás**: `CURRENT_STATE.md` descreve um vertical slice já testado ponta a ponta via Playwright, sem erros de console, rodando em `index.html`.
3. **Era 3 — a nova visão.** `FOUNDATION.md`, `docs/domain/*` (exceto Glossary), `docs/UI/screens/*`, `docs/mvp/User Flow.md`, `docs/experience/*`, `docs/worlds/*`, `docs/game-design/Art Direction.md`, `Content Design.md` e `Core Gameplay Loop.md` descrevem um produto bem mais ambicioso: Casa → Jardim → Reinos → Regiões → Missões → Storybook, com múltiplas "jornadas" simultâneas, Timeline com fotos, Diário, Login. Nada disso está implementado — `FOUNDATION.md` termina com "Próxima etapa: Implementação do MVP utilizando Claude Code", ou seja, é uma proposta, não um estado atual.

O problema não é ter uma visão de longo prazo ambiciosa — isso é saudável e está até bem guiado por `Vision.md` (múltiplos mundos no futuro, mesma identidade). **O problema é que a Era 3 foi escrita como se fosse o novo MVP**, sem nunca revogar formalmente a Era 2, e sem ninguém verificar se ela ainda cabia no que `Charter.md` já tinha congelado. É exatamente o padrão clássico de deriva em sessões longas de co-criação com IA: cada conversa nova reabre decisões antigas para "melhorá-las" e produz um documento novo e mais rico, mas ninguém volta para reconciliar com o que já existia — e o que já existia inclui código funcionando.

Isso explica praticamente todas as contradições que a auditoria encontrou: elas não são erros aleatórios, são o rastro de uma pivotagem de produto que nunca foi declarada como pivotagem.

## Minha opinião

**A Era 2 já venceu — só falta reconhecer isso por escrito.** Vocês têm um vertical slice funcional, testado, alinhado ao `Charter.md`, ao `CLAUDE.md` e aos princípios congelados. A Era 3 é um documento de visão de produto muito bem escrito, mas é uma reescrita completa do jogo (5 níveis de navegação em vez de abas, um sistema de "memória para a vida" que a stack atual nem consegue sustentar) disfarçada de "próximo passo do MVP". Se ela for implementada como está documentada, vocês não estarão terminando o MVP — estarão jogando fora um MVP validável e começando um produto novo, maior, sem nunca ter testado a hipótese original com uma criança de verdade.

A pergunta que `MVP Design Principles.md` manda fazer — "a criança sente vontade de voltar amanhã?" — pode ser respondida com o que já existe: Casa, uma missão diária, uma estrela, uma loja simples, um álbum. Jardim, Reinos, Storybook e Timeline são ótimas ideias para depois que essa resposta vier que sim.

Minha recomendação central, que orienta todas as sugestões abaixo: **congelar formalmente a Era 2 como o MVP, e reclassificar toda a Era 3 como Visão / Fase 2 — sem apagar nada, só rotulando corretamente.**

---

# Parte 2 — Estratégia recomendada para seguir com o MVP

1. **Declarar a pivotagem por escrito.** Adicionar uma entrada em `docs/Decision_Log.md` (hoje vazio) registrando: "MVP = modelo de abas (Era 2). Jardim/Reinos/Storybook (Era 3) viram Visão/Backlog até o MVP do Piano ser validado com playtest real." Isso sozinho resolve a Categoria 1, 3 e 7 quase inteiras.
2. **Escolher o modelo de abas (Era 2) como spec ativa.** Ele já está implementado, já passou por teste ponta a ponta, e é o que `Charter.md`/`CLAUDE.md` realmente descrevem.
3. **Rebaixar formalmente os documentos da Era 3** (não deletar): trocar os cabeçalhos "MVP" desses documentos para "Visão (pós-validação)" e mover FOUNDATION.md de "documento mais importante do projeto" para "visão de longo prazo — não é a spec do MVP atual". Isso preserva todo o trabalho de design para quando fizer sentido.
4. **Fechar as lacunas reais do slice atual antes de qualquer coisa nova** — as que `CURRENT_STATE.md` já lista: tela de Eventos (não existe), XP visível (hoje é só nível derivado de estrelas), decidir se entra Missão Semanal, decidir se a Árvore de Habilidades do piano entra no MVP ou fica só "Repertório".
5. **Corrigir a economia em um único lugar**: `Glossary.md` (Estrela "usada na loja", sem "Moeda") diverge de tudo o resto. Alinhar o Glossário ao que `GDD.md`/`Economy.md`/o código já fazem: Estrela nunca é gasta, Moeda é gasta, Moeda nasce de Estrela.
6. **Decidir o destino do Catálogo da Família agora, antes de codar Loja/Recompensas** — é o ponto de maior risco de contradição (ver Categoria 3, item 5). Minha sugestão está detalhada na Parte 3.
7. **Consolidar o domínio**: unificar `Glossary.md` + `Game Domain Model.md` em um único documento, com o Glossary vencendo o formato e a Era 2 vencendo o conteúdo onde há conflito.
8. **Corrigir os índices**: `CLAUDE.md`, `README.md` e `CURRENT_STATE.md` apontam para caminhos que não existem mais. Isso é puramente mecânico — recomendo eu mesmo fazer essa correção quando você aprovar, é trabalho de arquitetura/organização, dentro do meu papel.
9. **Depois — e só depois — retomar a Era 3** como projeto de expansão (V2), com o mesmo rigor: um documento por conceito, sem reabrir o que já foi congelado no MVP.

---

# Parte 3 — Sugestão para cada item do `ARCHITECTURE_REVIEW.md`

Organizado pelas mesmas 10 categorias e numeração da Parte 2 do relatório, para facilitar a conferência cruzada. Não repito os achados da Parte 1 do relatório (as 5 perspectivas) porque, como o próprio relatório observa, eles são o mesmo conjunto de problemas visto de outros ângulos — a resolução é a mesma.

## Categoria 1 — Inconsistências entre documentos

1. **Estrela gasta vs nunca gasta** → Vence "nunca gasta" (`Economy.md`, `GDD.md`, `Principles.md`, código). Corrigir a entrada "Estrela" do Glossary.
2. **Objetivo ⊂ Missão vs Missão ⊂ Objetivo** → Vence a definição do Glossary/GDD (Objetivo é a condição de conclusão de uma Missão) porque é o modelo do MVP em produção. A hierarquia invertida (`Goals.md`, `Progression Model.md`) pertence à Era 3 — rotular como Visão, não reconciliar agora.
3. **Sessão contém Missões vs Missão exige Sessões** → "Sessão" não existe no MVP (Era 2) nem no Glossary. Não decidir a hierarquia agora: mover o conceito inteiro para Visão/Backlog até a Era 3 ser retomada.
4. **XP no MVP vs XP inexistente nos sistemas** → Ver recomendação detalhada na Categoria 7, item 8. Resumo: ou implementar XP de verdade (ele já está no Glossary/GDD) ou removê-lo formalmente do escopo — as duas opções são aceitáveis, a inação não é.
5. **Loja/Álbum/Eventos/Calendário "futuros" (Screen Map) vs MVP congelado** → Vence o congelado (`Charter.md`/`CLAUDE.md`). `Screen Map.md` é Era 3 — rotular como Visão.
6. **Login proibido vs Login no MVP** → Vence a proibição (`Charter.md`, e a stack não suporta OAuth sem backend). Remover Login de qualquer seção "MVP" em `User Flow.md`/`Screen Map.md`.
7. **Validação parental obrigatória vs configurável** → Recomendo "configurável" (mais flexível, já é o desenho mais recente), mas com um padrão default explícito para o MVP: automática (é o que o slice já faz). Registrar essa decisão no Decision Log.
8. **Casa do GDD vs Casa da House Screen** → Vence a Casa do GDD/slice (quarto, piano, troféus, loja, álbum) para o MVP. A House Screen (Jardim, correio, Storybook) é Era 3.
9. **Público 7–10 vs 6–12** → Manter 7–10 (`Manifesto.md`/`Charter.md`, é a definição mais antiga e mais citada). Corrigir `GDD/Overview.md`.
10. **Capítulo 3 divergente entre `Learning Path.md` e `Chapters.md`** → Ambos são Era 3/backlog (trilha de capítulos do Piano não está no MVP atual, que só tem "Repertório"). Corrigir quando a trilha for retomada; não é urgente.
11. **Hierarquia do `CLAUDE.md` aponta para arquivos inexistentes** → Corrigir mecanicamente os caminhos (`docs/product/Manifesto.md` etc.) e incluir Glossary/Economy/GDD na lista de consulta obrigatória. Posso fazer essa correção diretamente, é organização, não game design.
12. **Referências cruzadas quebradas** (`Roadmap.md`→`GDD.md`, `GDD/Overview.md`→arquivo deletado, etc.) → Corrigir mecanicamente junto com o item 11.

## Categoria 2 — Conceitos duplicados

1. **Duas árvores** (Árvore de Habilidades vs Árvore do Crescimento) → São conceitos diferentes por natureza (uma é uma skill tree técnica do Piano, a outra é um símbolo emocional de progresso geral). Recomendo manter só a **Árvore de Habilidades** no MVP (já está no Glossary/GDD) e mover a Árvore do Crescimento/Jornada para Visão — ter as duas ao mesmo tempo é redundante para o objetivo do MVP.
2. **Quatro sistemas de memória** (Álbum, Storybook, Timeline, Diário) → No MVP, só **Álbum de Adesivos** (já implementado). Storybook/Timeline/Diário são a mesma necessidade emocional ("preservar a jornada") reformulada três vezes — quando a Era 3 for retomada, escolher **um** desses três, não os três.
3. **Dois GDDs com escopos diferentes** (`GDD.md` vs `GDD/Overview.md`) → `GDD.md` vence (é o mais alinhado ao código real e ao Charter). `Overview.md`/`Gameplay.md` são material de Era 3 — se forem mantidos, remover as seções "MVP" deles.
4. **Três documentos de direção visual** → `docs/UI/Design System.md` vence para o MVP (é o que reflete o que já está implementado: SVG, ícones outline). `Art_Bible.md` deveria ser atualizado para parar de dizer "aguardando definição" e simplesmente referenciar o Design System. `Art Direction.md` (ícones preenchidos, PNG) fica marcado como proposta não adotada — decisão de arte não é minha, mas a inconsistência técnica (SVG vs PNG) eu recomendo resolver a favor de SVG por performance, como o próprio `CLAUDE.md` já manda.
5. **Glossary vs Game Domain Model** → Fundir em um documento único (ver Parte 2, item 7). O Glossary deve ser o único que sobra.
6. **Loop principal descrito 5 vezes** → Manter `Core Gameplay Loop.md` como único documento de loop para o MVP; os outros quatro devem referenciá-lo, não redefini-lo.

## Categoria 3 — Conceitos conflitantes

1. **Medalha**: domínio de habilidade vs marco de constância → Recomendo "marco de constância" (mais fácil de implementar sem uma árvore de skills completa, e mais alinhado à filosofia "constância > perfeição" do `Manifesto.md`). Corrigir `Progression Model.md` (que é Era 3 mesmo).
2. **Troféu**: domínio de um mundo vs momento único → Manter a definição do Glossary (maior reconhecimento permanente de um mundo) para o MVP; é a mais simples de implementar (1 mundo = no máximo 1-2 troféus).
3. **Adesivo**: conquista vs memória → Manter "conquista" (Glossary/GDD, já implementado, sem aleatoriedade).
4. **Jornada**: totalidade da experiência vs sinônimo de mundo → Manter a definição do Glossary (Jornada = experiência completa, superset de todos os Mundos). É a única definição que não colide com "Mundo Piano" já existente.
5. **Recompensa da família**: estrelas vs moedas vs proibida → Este é o mais importante de resolver antes de codar. Minha recomendação: **fora do MVP.** Não é necessária para validar a hipótese central (motivação para praticar piano), é o item com mais contradição documental, e introduz fluxo de aprovação/inbox que aumenta bastante a complexidade. Se vocês quiserem manter alguma recompensa física configurável pelos pais no MVP, sugiro a versão mais simples já sugerida em `FOUNDATION.md`: Estrelas (não Moedas) desbloqueiam recompensas configuradas pelos pais, sem loja, sem pedido de resgate, sem inbox — só um marco que o pai define e entrega manualmente. Decisão final é sua.
6. **Ícones preenchidos vs outline; PNG vs SVG** → Ver Categoria 2, item 4.
7. **Sessão "em avaliação" vs pilar do MVP** → Já resolvido: Sessão fica fora do MVP (Categoria 1, item 3).
8. **Recompensa por login diário vs "nenhuma mecânica deve incentivar permanecer conectado"** → Remover o trigger de "login diário" do `Reward System.md`. Viola um princípio do Manifesto explicitamente, sem ambiguidade — recomendo remoção direta, não é uma escolha de gosto.
9. **Aleatoriedade proibida vs backlog com loot tables** → Recomendo remover "recompensas aleatórias"/"loot tables" até do backlog do `Reward System.md`, ou marcá-las explicitamente como "direção rejeitada" para não ressurgir sem querer numa conversa futura.

## Categoria 4 — Dependências circulares

1. **Missão → Recompensa → Progression → Missão** → No MVP (Era 2) isso nem existe como ciclo: o slice atual concede recompensa direto na conclusão da missão, sem motor de eventos. Recomendo manter assim para o MVP — o "motor de eventos de domínio" da `Product Architecture.md` é over-engineering para o estágio atual (vale a pena registrar como decisão técnica futura, não implementar agora).
2. **Reward System ↔ Economy** → Mesma resposta: no MVP a relação é direta (concluir missão → creditar estrela/moeda), sem "condições" configuráveis lendo o saldo de volta. Guardar o motor de regras para quando houver necessidade real (Parent Companion customizável).
3. **Parent Companion ↔ Mission/Reward** → Idem — no MVP, validação de missão e Painel dos Pais são simples (PIN + aprovar/rejeitar), sem Inbox/notificações formais.
4. **GDD (World) definindo Economy** → Aceitar essa "violação de camada" no MVP: com um único mundo (Piano), não há razão prática para a camada de Worlds ser agnóstica de economia. Vale a pena isolar isso só quando houver 2+ mundos de verdade.
5. **Objetivo ↔ Missão ↔ Sessão** → Resolvido junto com Categoria 1, itens 2 e 3.

## Categoria 5 — Documentos redundantes

1. **`Character.md`/`House.md` vazios** → Preencher com a spec mínima do que já está implementado (Casa: quarto, personagem, piano, estante de troféus, loja, álbum — direto do `GDD.md`). Recomendo eu mesmo fazer isso, é documentar o que já existe, não inventar.
2. **`Decision_Log.md`/`Playtest_Log.md` vazios** → Começar a preencher o Decision Log agora com as decisões implícitas já tomadas (ver Parte 2, item 1). Playtest Log só faz sentido depois do primeiro playtest real.
3. **Glossary × Game Domain Model** → Fundir (Categoria 2, item 5).
4. **Art Bible × Art Direction** → Reconciliar em um só (Categoria 2, item 4).
5. **Journey/Progress Card, Story/Message Card** → Esses componentes pertencem à Era 3 (telas Jardim/Reino/Storybook não existem no MVP de abas). Não vale a pena resolver a sobreposição agora — endereçar quando essas telas forem de fato construídas.
6. **`GDD.md` × `GDD/Overview.md`** → Resolvido (Categoria 2, item 3).

## Categoria 6 — Problemas de nomenclatura

1. **Reino/Mundo/Jornada** → "Mundo" é o termo oficial do MVP (já no Glossary, já implementado). Reino/Jardim ficam propostos para quando a Era 3 for formalmente retomada — devem passar pelo fluxo de "Novo Conceito Proposto" do `CLAUDE.md` antes de voltar a aparecer em qualquer documento.
2. **Região/Capítulo/Etapa/Área** → Mesma resposta: fora do MVP, propor formalmente quando retomado.
3. **"Moeda" ausente do Glossary** → Adicionar agora — é um recurso do MVP ativo, não deveria faltar.
4. **Painel dos Pais vs Parent Companion** → Usar "Painel dos Pais" (já é o termo do Glossary e do MVP); "Parent Companion" é nome de documento técnico, não precisa virar termo de domínio.
5. **Álbum vs Pasta de Adesivos** → Usar "Álbum" (Glossary). Corrigir `Progression Model.md`.
6. **Loja vs Loja do Jogo vs Catálogo Journey World** → Usar "Loja" no MVP (é o termo do Glossary/Charter). "Catálogo Journey World"/"Catálogo da Família" só fazem sentido se/quando a Era 3 (múltiplos catálogos) for adotada.
7. **Personagem vs Avatar** → Usar "Personagem" (Glossary é explícito: "não é um avatar genérico"). Corrigir `World Model.md`/telas que usam "Avatar".
8. **Termos sem entrada no Glossary** (Jardim, Reino, Sessão, Storybook, Streak, etc.) → Todos pertencem à Era 3. Não propor agora em lote — cada um deve passar pelo fluxo formal do `CLAUDE.md` quando for de fato priorizado, não antes.
9. **Nomes flutuantes dos mundos futuros** → Sem urgência, são só ideias de backlog (`Vision.md` já cobre isso adequadamente como visão, não como escopo).
10. **"Evento" ambíguo** (domínio/mensageria vs recital) → Já que o MVP não tem motor de eventos de domínio (Categoria 4), esse conflito não existe na prática ainda. Quando a arquitetura de eventos for implementada de verdade, renomear um dos dois (sugiro "Evento" só para o conceito de jogo/recital, e "Sinal" ou "Trigger" para o técnico).

## Categoria 7 — Violações do MVP

1. **Screen Map/User Flow adicionam Splash/Login/Perfil/Storybook e removem Loja/Álbum/Eventos/Calendário** → Rotular essas seções como Visão (Parte 2, item 3).
2. **Progression Model com Sessões/Objetivos/Loja da Família no "MVP"** → Idem.
3. **Economy com Catálogo da Família/Pedidos de Resgate no "MVP"** → Resolvido na Categoria 3, item 5 — recomendo fora do MVP.
4. **Parent Companion com Dashboard/Inbox/Modo Confiança/Relatórios no "MVP"** → Simplificar para o que o Charter pede: painel com PIN, aprovar/rejeitar missão, ver progresso. O resto é V2.
5. **Storybook/Timeline com Fotos no "MVP"** → Fora do MVP — e tecnicamente inviável em LocalStorage de qualquer forma (Categoria 8, item 1).
6. **Tree of Growth no "MVP"** → Fora do MVP (é a "segunda árvore", Categoria 2, item 1).
7. **Goals.md com sistema completo de objetivos no "MVP"** → Fora do MVP; o MVP usa Objetivo só como subcondição de Missão (Categoria 1, item 2).
8. **Cronômetro de prática no "MVP" de `GDD/Overview.md`** → Recomendo manter fora do app (alinhado a `Core Gameplay Loop.md` e ao Manifesto: "menos tempo olhando pra tela"). A criança pratica offline; o app só registra a conclusão.
9. **Events.md com calendário/countdown completo no "MVP" vs Screen Map "futuro"** → Eventos estão no Charter congelado, então ficam no MVP — mas na versão simples do `GDD.md` (evento = data + checklist + progresso + recompensa), não na versão elaborada de `Events.md`.
10. **Escopo agregado 4-5x maior que o congelado** → Consequência direta de tratar Era 3 como MVP. Resolvida pela reclassificação em massa (Parte 2, item 3).

## Categoria 8 — Riscos de escalabilidade

1. **Permanência prometida vs LocalStorage volátil** → Não prometer "para sempre" em nenhum texto voltado à família enquanto a persistência for só local. Ajustar a linguagem de `Storybook.md`/`Timeline.md` quando (e se) esses sistemas forem retomados; no MVP atual isso não é uma promessa ativa, então não é urgente.
2. **Sem esquema/versionamento de save** → Recomendo implementar antes de qualquer expansão de features: um campo `schemaVersion` no objeto salvo em LocalStorage, mesmo que hoje não haja migração nenhuma. É uma decisão técnica pura — posso propor isso quando formos mexer no código.
3. **Moedas globais entre jornadas sem balanceamento** → Não é um problema real com um único Mundo (Piano). Endereçar só quando o segundo mundo for de fato desenvolvido.
4. **Multi-perfil/irmãos ignorado** → Fora de escopo do MVP (não está no Charter). Registrar como decisão consciente no Decision Log para não ser "esquecido" e sim "adiado".
5. **Arquitetura aspiracional sem incrementos definidos** → A `Product Architecture.md` deveria ser reescrita como roadmap técnico em fases (Fase MVP: arquivo único; Fase 2: separar módulos; Fase 3: camada de persistência abstrata; Fase 4: eventos de domínio), não como uma arquitetura-alvo única e imediata. Posso propor essa reescrita.

## Categoria 9 — Riscos para React Native/Expo

Essas são decisões técnicas — dentro do meu papel — então minha recomendação é mais direta:

1. **Estado "Hover (Web)" obrigatório** → Remover essa exigência do Design System para componentes que também existirão em touch; hover deve ser tratado como enhancement opcional de web, nunca requisito.
2. **SVG para interface + animações CSS** → Manter para o MVP web (é a decisão certa agora: leve, simples, sem framework). Só recomendo introduzir uma camada de abstração (ex.: nomes de ícones em vez de paths SVG inline espalhados) se/quando a migração para RN for de fato planejada — não antes, seria over-engineering agora.
3. **Arquivo único / DOM monolítico** → Aceitável para o MVP (é literalmente o que `GDD.md` pede). Recomendo já isolar a lógica de estado/regras (funções puras de estrelas/moedas/missões) do código de renderização DOM dentro do próprio `index.html`, sem separar em módulos ainda — isso não custa nada agora e economiza retrabalho depois.
4. **LocalStorage sem camada de abstração** → Recomendo criar já uma camada mínima (`SaveStore.get()/set()`) em vez de chamar `localStorage` direto pelo código — troca barata agora, cara depois. Posso implementar isso na próxima vez que mexermos no `index.html`.
5. **Login social e mídia** → Já fora do MVP (Categoria 7, item 1 e 5). Não é um risco atual.
6. **Orientação de tela indefinida** → Fixar retrato como padrão do MVP (já é o comportamento atual do slice, segundo `CURRENT_STATE.md`), documentar isso no Design System para não reabrir a discussão.

## Categoria 10 — Oportunidades de simplificação

O relatório já lista 10 boas sugestões nessa categoria. Minha contribuição aqui não é substituí-las, é sequenciá-las — o que fazer primeiro:

1. **Primeiro**: registrar a pivotagem (Decision Log) e reclassificar Era 3 como Visão. Sem isso, qualquer outra correção é remendo.
2. **Segundo**: corrigir a economia no Glossary (Estrela/Moeda) e decidir o destino do Catálogo da Família — são os dois pontos que bloqueiam qualquer implementação nova de Loja/Recompensas.
3. **Terceiro**: decidir o destino do XP (Categoria 1, item 4).
4. **Quarto**: preencher `Character.md`/`House.md` e corrigir os caminhos quebrados em `CLAUDE.md`/`README.md`/`CURRENT_STATE.md`.
5. **Depois disso**: fechar as lacunas de escopo que `CURRENT_STATE.md` já lista (Eventos, XP visível, Missão Semanal, Árvore de Habilidades) — essas sim bloqueiam considerar o MVP "completo".
6. **Só então**: retomar a Era 3 como projeto de V2, com o mesmo cuidado (um documento por conceito, aprovação explícita de novos termos).

---

# Resumo de uma linha

Vocês não têm um projeto quebrado — têm **dois projetos bons** empilhados no mesmo repositório sem que ninguém tenha formalmente escolhido qual vem primeiro. O menor dos dois já está implementado e testado. Minha recomendação é declarar isso por escrito, terminar de validar esse primeiro, e só então voltar para o segundo.
