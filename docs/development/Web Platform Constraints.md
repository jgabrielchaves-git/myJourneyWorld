# Journey World
# Development - Web Platform Constraints

**Versão:** 1.0
**Status:** Ativo

---

# Objetivo

Este documento registra limitações técnicas reais de construir o Journey World como uma aplicação web (HTML/CSS/JS, `CLAUDE.md`), quando a visão de produto (`FOUNDATION.md`, `docs/domain/*`, `docs/UI/*`) pede algo que um app nativo faria com mais facilidade ou confiabilidade.

Não é decisão de produto — é o Claude Code sinalizando custo/risco técnico (papel definido em `CLAUDE.md`: arquitetura, performance, manutenção) para que o Product Owner decida com informação completa.

Cada entrada registra: o que a visão pede, por que é difícil/arriscado na web, o que sugerimos para o MVP, e o que fica anotado para uma eventual migração para app nativo.

---

# 1. Painel dos Pais em dispositivo separado do da criança

**O que a visão pede:** um Painel dos Pais rico (Dashboard, Inbox, Timeline, Relatórios — `docs/systems/Parent Companion.md`, MVP confirmado em 2026-07-21) sugere, implicitamente, que os pais possam acompanhar a jornada da criança a qualquer momento, de qualquer lugar.

**Por que é difícil na web (MVP atual):** o app roda 100% no navegador, salvando tudo em LocalStorage — um armazenamento local **por navegador e por dispositivo**, sem sincronização. Isso significa que o Painel dos Pais só enxerga os dados da criança se rodar **no mesmo navegador/dispositivo** onde a criança joga. Não existe hoje uma forma de o pai abrir o Painel no próprio celular e ver o progresso registrado no tablet da criança.

**Sugestão para o MVP:** manter o modelo atual — um dispositivo compartilhado pela família (ex.: um tablet), com o Painel dos Pais protegido por PIN no mesmo app, não um app separado. É exatamente como já está implementado hoje. Deixar isso explícito evita a expectativa de "ver o progresso do celular da mãe".

**Nota para migração futura:** um backend com conta de família e sincronização (mencionado como preparação futura no `CLAUDE.md`) resolveria isso nativamente — os dados deixariam de ser presos a um dispositivo.

---

# 2. Fotos no Diário Compartilhado / Storybook

**O que a visão pede:** `Parent Companion.md` e `Story Card.md` preveem fotos como parte do Diário Compartilhado e do Storybook.

**Por que é difícil na web (MVP atual):** sem backend, fotos precisariam ser guardadas como base64 dentro do LocalStorage, que tem um limite prático de ~5-10MB por site. Poucas fotos em boa resolução já esgotariam esse limite e arriscariam corromper todo o save (estrelas, moedas, progresso) se o navegador recusar gravar.

**Sugestão para o MVP:** o próprio `Parent Companion.md` já previa isso — "No MVP, o diário será composto apenas por mensagens de texto." Mantemos essa restrição, mas agora por um motivo técnico explícito, não só de simplicidade de escopo.

**Nota para migração futura:** fotos exigem armazenamento remoto (mesmo um app nativo precisaria de nuvem para isso, não é uma limitação exclusiva da web) — já está corretamente no Backlog.

---

# 3. Cronômetro de missão em segundo plano

**O que a visão pede:** `Mission Screen.md` prevê um cronômetro (iniciar/pausar/finalizar) durante a prática.

**Por que é arriscado na web:** navegadores (especialmente em celulares) reduzem ou pausam JavaScript quando a aba sai de foco ou a tela é bloqueada. Se a criança trocar de app no meio da prática, o tempo contado pode ficar impreciso.

**Sugestão para o MVP:** tratar o cronômetro como um apoio visual, não como fonte de verdade da recompensa — a conclusão da missão continua sendo uma ação explícita da criança/pais, não um cronômetro que dispara sozinho. Já é como o `Mission Screen.md` descreve ("o cronômetro auxilia a criança, mas não é obrigatório").

**Nota para migração futura:** um app nativo consegue manter contagem confiável em segundo plano (ou usar notificações agendadas do sistema).

---

# 4. Notificações / lembretes automáticos

**O que a visão pede:** `Parent Companion.md` lista "lembretes automáticos" e "notificações push" no Backlog; a hipótese central do produto depende de a criança lembrar de praticar.

**Por que é difícil na web:** Web Push existe, mas exige HTTPS, Service Worker, permissão explícita do usuário — e no iPhone (Safari) só funciona se o site for instalado na tela de início como PWA, com suporte historicamente limitado. Não dá para garantir que um lembrete "hora de praticar piano" chegue de forma confiável em todos os aparelhos.

**Sugestão para o MVP:** nenhuma mudança necessária agora — já está corretamente no Backlog, não no MVP.

**Nota para migração futura:** notificações confiáveis são um dos motivos mais fortes para eventualmente migrar para um app nativo, se lembretes diários se mostrarem importantes após a validação.

---

# Princípios

Nenhum item aqui bloqueia o MVP atual — os próprios documentos de design já haviam optado, na maioria dos casos, pelo caminho mais simples (texto em vez de foto, cronômetro opcional, sem notificações). Este documento existe para tornar explícito **por que** essas escolhas também são as tecnicamente corretas para uma web app, e para servir de checklist na hora de avaliar uma futura migração para app nativo.
