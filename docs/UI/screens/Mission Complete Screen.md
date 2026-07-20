# Journey World
# UI - Mission Complete Screen

**Versão:** 1.0
**Status:** Draft

> **Parcialmente Visão (pós-MVP).** Evolução da Árvore e registro no Storybook são do modelo Jardim/Reino, fora do MVP ativo. No MVP ativo, a conclusão de missão usa um modal simples (estrela + moeda, ver `index.html`), sem tela dedicada de conclusão. Ver `docs/Decision_Log.md` (2026-07-20).

---

# Objetivo

Celebrar a conclusão de uma missão e apresentar, de forma clara e motivadora, tudo o que foi conquistado.

Esta tela encerra um ciclo da jornada e prepara a criança para o próximo.

---

# Pergunta Principal

"O que conquistei hoje?"

---

# Filosofia

A celebração deve reforçar a dedicação da criança.

O foco não é a recompensa.

O foco é reconhecer o esforço.

As recompensas representam a consequência da prática.

---

# Estrutura

## Mensagem Principal

Mensagem positiva.

Exemplos:

"Parabéns!"

"Você cultivou mais um passo da sua jornada!"

"Hoje sua Árvore da Música ficou mais forte."

As mensagens devem variar para evitar repetição.

---

## Resumo da Missão

Exibe:

- Nome da missão
- Data
- Horário
- Tempo utilizado (quando existir)

---

## Recompensas

Lista tudo que foi obtido.

Exemplo:

+ 10 moedas

⭐ Nova estrela

🌱 Árvore evoluiu

🏅 Novo adesivo

📖 Novo registro no Storybook

Cada recompensa aparece apenas quando aplicável.

---

## Evolução da Árvore

Caso a missão gere progresso visual.

Mostrar:

Estado anterior

↓

Novo estado

No MVP basta trocar a ilustração.

Sem animações.

---

## Storybook

Quando houver registro.

Exemplo:

"Uma nova página foi adicionada à sua história."

Botão:

"Ver Minha História"

Opcional no MVP.

---

## Próximo Passo

Sugestões simples.

Exemplos:

Voltar para Casa

ou

Fazer outra missão

A decisão sempre permanece com a criança.

---

# Estados

Missão simples

Missão com estrela

Missão com adesivo

Missão com desbloqueio

Missão com recompensa dos pais

Todas reutilizam a mesma estrutura.

---

# Navegação

Missão

↓

Conclusão

↓

Casa

ou

Região

---

# MVP

Implementar:

- mensagem de parabéns;
- resumo da missão;
- lista de recompensas;
- botão voltar para Casa;
- botão voltar para Região.

---

# Fora do MVP

Não implementar:

- animações elaboradas;
- fogos de artifício;
- efeitos sonoros complexos;
- personagens comemorando;
- compartilhamento social.

---

# Critérios de Aceitação

A criança deve:

- entender que concluiu a missão;
- visualizar claramente suas conquistas;
- sentir satisfação pela prática realizada;
- conseguir retornar rapidamente ao fluxo principal.

---

# Princípios

Celebrar o esforço.

Valorizar a constância.

Nunca exagerar na recompensa.

A missão termina, mas a jornada continua.