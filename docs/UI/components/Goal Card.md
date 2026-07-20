# Journey World
# UI Component - Goal Card

**Versão:** 1.0
**Status:** Draft

> **Visão (pós-MVP).** Modela Objetivo como composto por várias Missões — o MVP ativo usa a relação oposta (Objetivo é subcondição de uma Missão, ver `docs/domain/Glossary.md`). Sobreposição conhecida com `Progress Card.md` — ver `ARCHITECTURE_REVIEW.md` (Categoria 5). Ver `docs/Decision_Log.md` (2026-07-20).

---

# Objetivo

O Goal Card representa um objetivo que a criança deseja alcançar dentro de uma Jornada.

Ele organiza metas de curto, médio ou longo prazo, mostrando claramente o propósito e o progresso até sua conclusão.

Um objetivo normalmente é alcançado através da realização de uma ou mais missões.

---

# Filosofia

Objetivos dão direção.

Missões representam os passos.

O Goal Card deve ajudar a criança a compreender o motivo pelo qual está realizando determinadas atividades, reforçando o significado da jornada.

---

# Estrutura

Cada Goal Card contém:

- Ícone ou ilustração
- Nome do objetivo
- Descrição
- Indicador de progresso
- Estado
- Próxima missão (opcional)

---

# Exemplo

🎹

Tocar minha primeira música completa

Pratique as músicas desta região até conseguir executá-las sem interrupções.

██████░░░░ 60%

Próxima missão:

Praticar "Ode à Alegria"

---

# Tipos

O Goal Card pode representar objetivos de diferentes naturezas.

Exemplos:

- Diário
- Semanal
- Mensal
- Região
- Reino
- Jornada
- Evento
- Personalizado pelos pais

---

# Propriedades

## Nome

Obrigatório.

Exemplo:

"Tocar minha primeira música"

---

## Descrição

Obrigatória.

Explica claramente o objetivo.

---

## Progresso

Opcional.

Pode utilizar:

- barra;
- porcentagem;
- quantidade de missões;
- estrelas relacionadas;
- outro indicador apropriado.

O componente não depende de um único formato.

---

## Próxima Missão

Opcional.

Quando existir, apresenta a próxima ação recomendada.

---

## Estado

Valores possíveis:

- Não iniciado
- Em andamento
- Concluído
- Pausado
- Bloqueado

---

# Interações

Toque:

Abrir detalhes do objetivo.

Quando existir uma próxima missão disponível, poderá oferecer acesso direto.

---

# Reutilização

Este componente poderá ser utilizado em:

- Região
- Jornada
- Dashboard dos Pais
- Eventos
- Planejamento
- Objetivos pessoais

---

# MVP

Implementar:

- nome;
- descrição;
- progresso;
- estado.

---

# Fora do MVP

Não implementar:

- dependências entre objetivos;
- objetivos compartilhados;
- comentários;
- histórico detalhado.

---

# Critérios de Aceitação

A criança deve conseguir responder rapidamente:

- Qual é meu objetivo?
- Como estou evoluindo?
- O que preciso fazer agora?

Sem precisar navegar para outra tela.

---

# Princípios

Os objetivos dão significado às missões.

Eles representam conquistas importantes da jornada e ajudam a criança a compreender que pequenas ações diárias constroem grandes resultados ao longo do tempo.