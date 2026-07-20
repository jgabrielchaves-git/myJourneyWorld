# Journey World
# UI Component - Story Card

**Versão:** 1.0
**Status:** Draft

> **Visão (pós-MVP).** Componente do Storybook, que não faz parte do MVP congelado (`CLAUDE.md`, `docs/product/Charter.md`). Sobreposição conhecida com `Message Card.md` — ver `ARCHITECTURE_REVIEW.md` (Categoria 5). Ver `docs/Decision_Log.md` (2026-07-20).

---

# Objetivo

O Story Card representa um momento importante registrado na história da criança.

Ele é utilizado pelo Storybook para construir uma narrativa cronológica da jornada, preservando conquistas, memórias e experiências vividas.

Cada Story Card representa uma lembrança.

---

# Filosofia

O Storybook não é um histórico de atividades.

Ele é um livro de memórias.

Cada Story Card deve transmitir a sensação de que aquele momento merece ser lembrado no futuro.

Seu foco é emocional, não estatístico.

---

# Estrutura

Cada Story Card contém:

- Imagem (opcional)
- Data
- Título
- Descrição
- Tipo
- Emoção (opcional)
- Tags (opcional)

---

# Exemplo

🎹

Primeira música completa

"Hoje consegui tocar minha primeira música inteira sem parar."

19 de Julho de 2026

---

# Tipos

Um Story Card pode representar qualquer momento relevante.

Exemplos:

- Missão concluída
- Nova estrela
- Marco importante
- Evento
- Apresentação
- Foto
- Mensagem da família
- Recompensa especial
- Reflexão do diário
- Descoberta

O componente não depende de um tipo específico.

---

# Propriedades

## Imagem

Opcional.

Pode conter:

- fotografia;
- ilustração;
- adesivo;
- imagem da missão.

---

## Data

Obrigatória.

Todo Story Card possui uma data.

---

## Título

Obrigatório.

Resumo curto do acontecimento.

---

## Descrição

Obrigatória.

Texto livre descrevendo o momento.

Pode ser escrito automaticamente pelo sistema ou pelos pais.

No futuro, a própria criança poderá editar ou complementar algumas entradas.

---

## Tipo

Obrigatório.

Utilizado para organizar filtros e categorias.

---

## Emoção

Opcional.

Pode representar o sentimento daquele momento.

Exemplos:

😊 Feliz

😄 Orgulhosa

🎉 Animada

🙏 Grata

---

## Tags

Opcional.

Exemplos:

- Música
- Piano
- Igreja
- Escola
- Família

---

# Interações

Toque:

Abrir a página completa da memória.

---

# Reutilização

Este componente poderá ser utilizado em:

- Storybook
- Timeline
- Perfil
- Painel dos Pais
- Retrospectivas
- Eventos

---

# MVP

Implementar:

- título;
- descrição;
- data;
- imagem opcional;
- tipo.

---

# Fora do MVP

Não implementar:

- comentários;
- curtidas;
- compartilhamento;
- edição colaborativa;
- localização;
- vídeos.

---

# Critérios de Aceitação

A criança deve conseguir identificar facilmente:

- o que aconteceu;
- quando aconteceu;
- por que aquele momento foi registrado.

Cada Story Card deve transmitir a sensação de que representa uma lembrança importante.

---

# Princípios

Os Story Cards são o coração emocional do Journey World.

Com o passar dos anos, eles deixarão de representar apenas atividades realizadas e passarão a contar a história da infância da criança.

O objetivo não é registrar tudo.

O objetivo é preservar aquilo que realmente merece ser lembrado.