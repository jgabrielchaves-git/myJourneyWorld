# CURRENT_STATE

> Última atualização: 2026-07-21

## Onde estamos hoje?

Fase 0 — Fundação, agora numa segunda reconciliação de escopo. Em 2026-07-19/20, uma auditoria (`ARCHITECTURE_REVIEW.md`) encontrou duas gerações de documentação: o MVP de abas já implementado ("Era 2") e uma visão maior de navegação Jardim/Reinos/Storybook nunca implementada ("Era 3"). A primeira reconciliação (2026-07-20) confirmou a Era 2 como MVP ativo. Em 2026-07-21, o Product Owner reviu essa decisão depois de comparar o código publicado com a documentação da Era 3 e **decidiu o oposto**: **a Era 3 é o MVP ativo agora** (`docs/Decision_Log.md`, "Revertido: MVP passa a ser a Era 3"). Casa → Jardim → Reino do Piano → Região → Missão → Conclusão → Storybook, mais a Árvore do Crescimento e um Painel dos Pais rico, substituem o modelo de abas.

Depois da decisão, foi feita uma reconciliação completa da documentação (~35 arquivos), discutida doc a doc com o usuário.

## O que já existe?

- Toda a documentação (`docs/product`, `docs/domain`, `docs/systems`, `docs/game-design`, `docs/UI`, `docs/worlds`, `docs/experience`, `docs/mvp`, `docs/development`) alinhada à Era 3 como MVP: notas de status revertidas, terminologia unificada (Mundo→Reino, Capítulo→Região com nome narrativo por Reino, Árvore do Crescimento vs. Árvore de Habilidades diferenciadas), Sistema de XP/Nível **removido em definitivo** (não é backlog) e substituído pela Árvore do Crescimento.
- `docs/product/Charter.md` (v2.0) e `CLAUDE.md` com o novo escopo do MVP.
- `docs/domain/Glossary.md` (v1.1) com os termos da Era 3 formalizados: Reino, Região, Conclusão, Storybook, Árvore do Crescimento; XP e Nível removidos.
- Painel dos Pais unificado (nome oficial, não "Configurações") com escopo rico confirmado como MVP: Dashboard, Inbox, Timeline/Diário (mesma base do Storybook), Relatórios, Modo Confiança — só a Loja da Família/Pedidos de Resgate continua fora (contraria "moedas compram só cosmético").
- Splash, Login e Perfil confirmados fora do MVP — nem no curto prazo.
- `docs/development/Web Platform Constraints.md` (novo): registro de limitações técnicas reais de app web vs. nativo (painel dos pais preso ao mesmo dispositivo/LocalStorage; fotos exigem texto no MVP; cronômetro não confiável em segundo plano; notificações push limitadas). A limitação de dispositivo compartilhado foi movida para `docs/Backlog.md` como pendência.
- `index.html` na raiz — **ainda é a implementação antiga (Era 2)**: Casa com abas, barra de XP, sem Jardim/Reino/Região. Nada da reconciliação de 2026-07-21 foi implementado em código ainda — só a documentação foi atualizada.

## O que está funcionando?

- O que está publicado em produção (https://jgabrielchaves-git.github.io/myJourneyWorld/) continua sendo a versão Era 2 testada em 2026-07-20 (Casa com abas, XP visível, Eventos, Missão Semanal) — ver histórico anterior desta seção. Commitado e no ar, mas **desalinhado da documentação atual**.

## O que falta?

Duas pendências foram deliberadamente adiadas pelo usuário durante a reconciliação (não são bloqueio, mas precisam ser retomadas antes de detalhar mais o Reino do Piano):

1. **Hierarquia Objetivo/Missão/Sessão**: três documentos (`FOUNDATION.md`/`Screen Map.md`, `docs/domain/World Model.md`, `docs/domain/Progression Model.md`) descrevem relações diferentes entre Objetivo, Missão e Sessão. Preciso de casos de uso concretos foram levantados na conversa; falta o usuário decidir.
2. **Mapeamento 12 Etapas (`docs/worlds/piano/Learning Path.md`) × 7 Regiões (`docs/worlds/piano/Chapters.md`)**: as Regiões do Piano parecem ser uma versão consolidada das Etapas pedagógicas, mas isso não foi confirmado. Proposta de mapeamento já apresentada ao usuário na conversa.

Depois dessas duas, falta:

- Direção de arte final (ver `docs/Art_Bible.md`) — personagem/avatar atuais são exploração, não arte final.
- **Implementação**: todo o código (`index.html`) precisa ser reescrito para a arquitetura Era 3 (Jardim, Reino do Piano, Regiões, Árvore do Crescimento, Painel dos Pais rico) — nada disso existe em código ainda.

## Qual é a próxima tarefa?

Retomar as duas pendências adiadas (hierarquia Objetivo/Missão/Sessão; mapeamento Etapas×Regiões) e a direção de arte. Só depois disso faz sentido começar a reescrever `index.html` para a Era 3 — implementar antes disso arriscaria retrabalho.

## O que não deve ser alterado?

- Os valores do projeto: acolhimento, progresso, simplicidade, alegria, disciplina, constância (ver [docs/product/Principles.md](docs/product/Principles.md)).
- A lista "nunca utilizar": violência, excesso de efeitos, interfaces poluídas, cores agressivas, excesso de texto.
- O princípio de que recompensas não substituem motivação intrínseca (estrelas nunca são removidas; sem aleatoriedade nas conquistas; moedas compram só cosmético).
- A separação de responsabilidades do [CLAUDE.md](CLAUDE.md): Claude decide arquitetura/implementação; **não** decide gameplay, identidade visual, direção de arte, economia ou game design.

## Quais decisões estão congeladas?

- Stack do MVP: HTML, CSS, JavaScript puro (sem frameworks, salvo necessidade real).
- Persistência: LocalStorage no MVP, com código preparado para migração futura online. Limitação conhecida: Painel dos Pais só funciona no mesmo dispositivo da criança (ver `docs/development/Web Platform Constraints.md`).
- Primeiro Reino: Piano. Reinos futuros (Ginástica Rítmica, Escola, Família, Virtudes, Jornada Espiritual) ficam sinalizados como bloqueados no Jardim, sem conteúdo real, até o MVP do Piano ser validado.
- Escopo fechado do MVP (Era 3, `docs/product/Charter.md` v2.0): Casa, Jardim, Reino do Piano, Árvore do Crescimento, Missões, Estrelas, Moedas, Loja, Coleções (Álbum), Eventos, Painel dos Pais (rico), Save.
- **Sem Sistema de XP/Nível — decisão definitiva, não é item de backlog.** A Árvore do Crescimento representa a progressão.
- Sem Splash, Login ou Perfil — confirmado, nem no curto prazo.
- Hipótese única a validar: gamificação aumenta motivação/consistência no estudo de piano (ver [docs/product/Charter.md](docs/product/Charter.md)).
- Catálogo da Família (moedas trocando por sorvete/cinema/passeio) fica fora do MVP — contraria "moedas compram apenas cosmético" (ver [docs/Decision_Log.md](docs/Decision_Log.md)).
