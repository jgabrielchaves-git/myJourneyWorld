# Journey World
# UI Component - Journey Card

**Versão:** 1.0
**Status:** Draft

> **Nota de status:** Revertido — ver `docs/Decision_Log.md` ("Revertido: MVP passa a ser a Era 3"). O Jardim é MVP ativo — este componente também. Distinção de `Progress Card.md`: ver nota em `Progress Card.md`.

---

# Objetivo

O Journey Card representa uma Jornada disponível para a criança.

Ele é utilizado principalmente no Jardim, mas poderá aparecer em outras telas como favoritos, histórico, recomendações e eventos.

Cada card resume o estado atual de uma Jornada.

---

# Filosofia

Uma Jornada não é uma tarefa.

Ela representa uma área importante da vida da criança.

O card deve transmitir progresso, cuidado e propósito.

---

# Estrutura

Cada Journey Card contém:

- Ilustração da Árvore
- Nome da Jornada
- Estado da Árvore
- Quantidade de estrelas
- Missão disponível (indicador)
- Progresso geral
- Botão/Ação para entrar

---

# Exemplo

🌳

Música

⭐⭐⭐⭐⭐

🌱 Florescendo

📌 1 missão disponível

[ Entrar ]

---

# Propriedades

## Nome

Obrigatório

Exemplo:

- Música
- Escola
- Fé

---

## Árvore

Imagem correspondente à Jornada.

Obrigatória.

---

## Estado da Árvore

Valores possíveis:

- Broto
- Pequena
- Em crescimento
- Florescendo
- Frutificando
- Madura

---

## Estrelas

Quantidade total conquistada.

Nunca diminui.

Pode ser exibida como:

★★★★★

ou

⭐ 18

A forma será definida pelo Design System.

---

## Missões

Indicadores possíveis:

Nenhuma

↓

Missão disponível

↓

Missão concluída hoje

↓

Evento disponível

---

## Progresso

Representa a evolução geral da Jornada.

Exemplo:

Região atual

ou

Objetivos concluídos

A implementação será definida posteriormente.

---

# Estados

## Disponível

Pode ser acessada.

---

## Bloqueada

Exibe apenas ilustração reduzida.

Sem botão Entrar.

---

## Nova

Primeira vez que aparece.

Pode possuir um pequeno destaque.

---

## Evento

Possui evento ativo.

---

# Interações

Toque:

Entrar na Jornada.

Pressionar (futuro):

Mostrar detalhes.

---

# Reutilização

Este componente poderá ser utilizado em:

- Jardim
- Perfil
- Dashboard dos Pais
- Eventos
- Recomendações
- Favoritos

---

# MVP

Implementar:

- árvore;
- nome;
- estrelas;
- indicador de missão;
- botão entrar.

---

# Fora do MVP

Não implementar:

- animações;
- efeitos;
- partículas;
- preview do Reino.

---

# Critérios de Aceitação

A criança deve conseguir identificar rapidamente:

- qual Jornada representa;
- seu nível de evolução;
- se existe algo para fazer hoje;
- como entrar nela.

---

# Princípios

O Journey Card deve incentivar a criança a cultivar aquela área da vida.

Ele representa uma Jornada viva, em constante crescimento.