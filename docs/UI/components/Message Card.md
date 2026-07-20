# Journey World
# UI Component - Message Card

**Versão:** 1.0
**Status:** Draft

> **Visão (pós-MVP).** Componente ligado à Caixa de Correio/Storybook, fora do MVP ativo (o Painel dos Pais do MVP não tem inbox — ver `docs/systems/Parent Companion.md`). Sobreposição conhecida com `Story Card.md` — ver `ARCHITECTURE_REVIEW.md` (Categoria 5). Ver `docs/Decision_Log.md` (2026-07-20).

---

# Objetivo

O Message Card representa uma mensagem exibida dentro do Journey World.

Seu objetivo é apresentar comunicações de forma simples, acolhedora e organizada.

As mensagens podem ser pessoais, familiares ou geradas pelo próprio sistema.

---

# Filosofia

Uma mensagem deve aproximar pessoas.

Ela não deve parecer uma notificação fria.

Sempre que possível, deve transmitir cuidado, incentivo ou celebrar um momento importante.

---

# Estrutura

Cada Message Card contém:

- Ícone ou avatar
- Remetente
- Título
- Conteúdo
- Data
- Estado de leitura
- Categoria

---

# Exemplo

👩 Mamãe

Bom trabalho hoje!

Estou muito orgulhosa da sua dedicação ao piano.

Hoje • 19:30

---

# Categorias

O Message Card pode representar diferentes tipos de mensagens.

Exemplos:

- Família
- Sistema
- Recompensas
- Eventos
- Lembretes
- Conquistas
- Convites

A categoria influencia apenas a apresentação visual.

---

# Propriedades

## Remetente

Obrigatório.

Exemplos:

- Mamãe
- Papai
- Journey World

---

## Avatar

Opcional.

Quando existir um remetente humano, pode exibir sua foto ou avatar.

---

## Título

Opcional.

Utilizado principalmente em mensagens do sistema.

---

## Conteúdo

Obrigatório.

Texto curto.

Recomendado:

até 250 caracteres.

---

## Data

Obrigatória.

Exibe quando a mensagem foi enviada.

---

## Estado

Valores possíveis:

- Não lida
- Lida
- Arquivada (futuro)

---

# Interações

Toque:

Abrir mensagem completa.

Pressionar (futuro):

Exibir ações rápidas.

---

# Reutilização

Este componente poderá ser utilizado em:

- Caixa de Correio
- Storybook
- Timeline
- Painel dos Pais
- Notificações
- Histórico

---

# MVP

Implementar:

- remetente;
- conteúdo;
- data;
- indicador de leitura.

---

# Fora do MVP

Não implementar:

- respostas dentro do card;
- anexos;
- emojis personalizados;
- reações;
- edição.

---

# Critérios de Aceitação

A criança deve conseguir identificar facilmente:

- quem enviou;
- quando foi enviada;
- qual é a mensagem;
- se já foi lida.

---

# Princípios

As mensagens devem fortalecer o vínculo entre a criança, sua família e sua jornada.

Sempre que possível, devem incentivar, reconhecer ou celebrar momentos importantes, evitando excesso de notificações puramente informativas.