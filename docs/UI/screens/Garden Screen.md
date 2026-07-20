# Journey World
# UI - Garden Screen

**Versão:** 1.0
**Status:** Draft

> **Visão (pós-MVP).** Tela do modelo de navegação Jardim/Reino/Região, fora do MVP congelado (`CLAUDE.md`, `docs/product/Charter.md`). Ver `docs/Decision_Log.md` (2026-07-20).

---

# Objetivo

O Jardim representa todas as jornadas da criança.

É o espaço onde ela visualiza seu crescimento e escolhe qual área da vida deseja cultivar naquele momento.

O Jardim não é um menu.

É um ambiente vivo que reflete sua evolução.

---

# Pergunta Principal

"Qual jornada quero cultivar hoje?"

---

# Objetivos da Tela

Permitir que a criança:

- visualize todas as jornadas disponíveis;
- acompanhe a evolução de cada árvore;
- identifique atividades disponíveis;
- escolha facilmente para onde deseja ir.

---

# Layout

O MVP utilizará uma tela simples.

Elementos:

- Fundo ilustrado.
- Caminho.
- Árvores.
- Nome da jornada.
- Indicadores de progresso.

Não haverá movimentação do personagem.

---

# Componentes

## Cabeçalho

Exibe:

- Saudação.
- Data (opcional).
- Botão voltar para Casa.

---

## Jardim

Lista visual das árvores.

Cada árvore representa uma Jornada.

Exemplo:

🌳 Música

🌳 Escola

🌳 Fé

🌳 Movimento

As jornadas bloqueadas aparecem discretamente.

---

## Card da Árvore

Cada árvore apresenta:

- Nome da Jornada.
- Ilustração da árvore.
- Quantidade de estrelas.
- Indicador de missão disponível.
- Estado de crescimento.

---

# Estados da Árvore

Cada árvore pode estar em um dos estados:

- Broto
- Pequena
- Em crescimento
- Florescendo
- Frutificando
- Madura

O crescimento é permanente.

---

# Interações

Ao tocar em uma árvore:

Abrir Reino correspondente.

---

Ao manter pressionado:

Exibir informações da jornada.

(MVP: opcional)

---

# Indicadores

Uma árvore pode exibir:

⭐ Nova estrela disponível

📌 Missão pendente

🎁 Recompensa disponível

✨ Novo marco conquistado

Esses indicadores devem ser discretos.

---

# Navegação

Casa

↓

Jardim

↓

Selecionar Árvore

↓

Reino

---

# MVP

Implementar apenas:

- Árvore da Música
- Estrutura preparada para futuras árvores
- Indicador de missão
- Quantidade de estrelas
- Estado visual da árvore

---

# Fora do MVP

Não implementar inicialmente:

- animações;
- clima dinâmico;
- ciclo dia/noite;
- personagem caminhando;
- jardim explorável;
- decoração do jardim.

---

# Critérios de Aceitação

- O usuário entende que cada árvore representa uma jornada.
- É possível entrar no Reino da Música com um único toque.
- O crescimento da árvore é facilmente percebido.
- A tela permanece simples e organizada.

---

# Backlog

- Sons ambientes.
- Estações do ano.
- Jardim da família.
- Árvores comemorativas.
- Banco para descanso.
- Lago.
- Animais.
- Flores desbloqueáveis.
- Decorações.

---

# Princípios

O Jardim deve transmitir paz.

Ele representa cuidado.

Não deve parecer um menu de opções.

Deve parecer um lugar onde o crescimento acontece lentamente.

Ao abrir essa tela, a criança deve sentir orgulho ao observar tudo aquilo que já cultivou e curiosidade para continuar fazendo suas árvores florescerem.