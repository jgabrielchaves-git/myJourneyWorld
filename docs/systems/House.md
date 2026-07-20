# House

Versão: 1.1

Status: Ativo — descreve o que já está implementado no slice do MVP

---

## Objetivo

A Casa é o hub principal do MVP: o ponto de partida e retorno de toda sessão, e o lugar que visualmente conta a história da dedicação da criança (troféus conquistados, Personagem, progresso de XP).

---

## Experiência do usuário

Ao abrir o app, a criança já está na Casa. Ela vê seu Personagem, o piano do quarto, uma prateleira de troféus (preenchida conforme músicas do repertório são apresentadas) e uma saudação que muda conforme o progresso. Um botão leva direto às Missões do dia — a ação mais provável.

---

## Fluxo

Casa é a tela inicial (`view-home`, ativa por padrão). A partir dela, a navegação lateral leva a Missões, Álbum, Loja e Calendário. Não há sub-telas dentro da Casa no MVP.

---

## Funcionalidades

- Cena do quarto: piano (ilustração SVG), Personagem, janela decorativa.
- Prateleira de troféus: um slot por música do repertório, preenchido quando a música atinge o estágio "Apresentada".
- Saudação rotativa com base no progresso total de estrelas.
- Barra de XP (progresso até o próximo Nível).
- Cor do quarto customizável via Loja (item cosmético "Quarto").
- Botão de atalho para Missões do dia.

---

## Regras de negócio

- A Casa nunca exige interação para ser vista — é sempre o ponto de entrada.
- Elementos exibidos (troféus, XP, Personagem) refletem apenas dados reais já conquistados; nada é decorativo sem lastro em progresso real.

---

## Estados

| Estado | Descrição |
|---|---|
| Padrão | Quarto com cor padrão (creme), sem troféus preenchidos |
| Progressão | Prateleira preenchendo conforme músicas são apresentadas |
| Customizado | Cor do quarto alterada via item comprado na Loja |

---

## Casos extremos

- Se houver mais músicas no repertório do que slots visíveis, a prateleira cresce (mínimo de 3 slots).
- Em orientação retrato em telas estreitas, a ilustração do piano é ocultada para dar espaço ao Personagem (degradação já implementada via media query).

---

## Configurações

Nenhuma configuração pelos pais específica da Casa. A cor do quarto é escolhida pela criança na Loja.

---

## MVP

- Quarto com piano, Personagem, prateleira de troféus.
- Saudação e barra de XP.
- Customização de cor do quarto (cosmético).
- Atalho para Missões.

---

## Pós-MVP

O modelo estendido descrito em `FOUNDATION.md` (Casa → Jardim → Reinos → Regiões) é Visão de longo prazo, registrada em `docs/Decision_Log.md` (2026-07-20). Não faz parte da Casa do MVP atual — não implementar sem decisão explícita de retomar essa fase.

---

## Backlog específico

Nenhum item aprovado no momento.
