# Journey World
# UI Component - Progress Card

**Versão:** 1.0
**Status:** Draft

> **Visão (pós-MVP).** Componente do modelo Jardim/Reino/Região (Jornada/Reino/Região/Objetivo), fora do MVP ativo. Sobreposição conhecida com `Journey Card.md` e `Goal Card.md` — ver `ARCHITECTURE_REVIEW.md` (Categoria 5). Ver `docs/Decision_Log.md` (2026-07-20).

---

# Objetivo

O Progress Card apresenta a evolução da criança em uma Jornada, Reino, Região ou Objetivo.

Seu propósito é demonstrar crescimento de forma simples, positiva e motivadora, valorizando a constância e não apenas a conclusão.

---

# Filosofia

O progresso representa crescimento.

Ele não deve gerar ansiedade ou pressão.

O foco está no caminho percorrido, não apenas na chegada.

Sempre que possível, o componente deve comunicar evolução utilizando linguagem positiva.

---

# Estrutura

Cada Progress Card contém:

- Título
- Subtítulo (opcional)
- Indicador visual de progresso
- Resumo textual
- Estado atual

---

# Exemplo

🌱 Evolução da Árvore

Sua árvore está florescendo.

★★★★★

42 estrelas conquistadas

---

# Tipos

O componente poderá representar diferentes tipos de progresso.

Exemplos:

- Jornada
- Reino
- Região
- Objetivo
- Evento
- Coleção
- Desafio

O componente deve ser flexível para atender todos esses cenários.

---

# Propriedades

## Título

Obrigatório.

Exemplos:

- Jornada da Música
- Bosque das Primeiras Notas
- Objetivos da Semana

---

## Subtítulo

Opcional.

Complementa o contexto.

Exemplo:

"Você está evoluindo com constância."

---

## Indicador Visual

Pode utilizar:

- Barra de progresso
- Anel de progresso
- Estrelas
- Estado da Árvore
- Outro indicador apropriado

O tipo de indicador depende do contexto.

---

## Resumo

Obrigatório.

Apresenta uma visão simples da evolução.

Exemplos:

- 4 de 6 objetivos concluídos
- 12 estrelas conquistadas
- 8 missões realizadas este mês

---

## Estado

Valores possíveis:

- Iniciado
- Em evolução
- Florescendo
- Consolidado
- Concluído (quando aplicável)

Nem todo progresso termina.

---

# Interações

Toque:

Abrir detalhes da evolução.

No MVP, essa interação é opcional.

---

# Reutilização

Este componente poderá ser utilizado em:

- Casa
- Jardim
- Região
- Perfil
- Storybook
- Painel dos Pais
- Eventos

---

# MVP

Implementar:

- título;
- indicador visual;
- resumo;
- estado atual.

---

# Fora do MVP

Não implementar:

- gráficos complexos;
- comparações entre crianças;
- rankings;
- previsões;
- estatísticas avançadas.

---

# Critérios de Aceitação

A criança deve conseguir compreender rapidamente:

- em qual contexto está evoluindo;
- quanto já percorreu;
- qual é seu estado atual.

O componente deve transmitir incentivo, nunca frustração.

---

# Princípios

O progresso é uma consequência da constância.

O componente deve celebrar o caminho percorrido, evitando destacar excessivamente aquilo que ainda falta.

Sempre que possível, utilizar linguagem inspiradora em vez de indicadores puramente numéricos.