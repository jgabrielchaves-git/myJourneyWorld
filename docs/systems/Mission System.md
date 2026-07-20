# Journey World
# System - Mission System

**Versão:** 1.0
**Status:** Draft

---

# Objetivo

O Mission System é responsável por definir, organizar e acompanhar todas as missões existentes no Journey World.

Missões representam pequenas tarefas que incentivam a criança a desenvolver hábitos consistentes e evoluir em direção aos seus objetivos.

Este sistema é reutilizado por todas as jornadas da plataforma.

---

# Filosofia

Grandes conquistas são construídas por pequenas ações repetidas.

As missões existem para transformar objetivos distantes em passos simples, claros e alcançáveis.

Elas devem incentivar constância, nunca sobrecarga.

---

# Responsabilidades

O Mission System é responsável por:

- criar missões;
- organizar recorrência;
- acompanhar progresso;
- controlar estados;
- integrar com Reward System;
- integrar com Progression;
- integrar com Parent Companion.

---

# O que é uma Missão?

Uma missão representa uma tarefa que pode ser executada pela criança.

Ela possui início, critérios de conclusão e recompensas configuráveis.

Exemplos:

- Praticar piano por 30 minutos.
- Executar a escala de Dó maior.
- Resolver cinco exercícios.
- Ajudar a organizar o quarto.
- Ler um capítulo de um livro.

---

# Estrutura de uma Missão

Toda missão possui:

- nome;
- descrição;
- jornada;
- categoria;
- dificuldade;
- recorrência;
- critérios de conclusão;
- recompensas;
- status.

---

# Tipos de Missão

## Diária

Reinicia diariamente.

Exemplos:

- Praticar piano.
- Fazer alongamento.
- Ler 15 minutos.

---

## Semanal

Reinicia semanalmente.

Exemplos:

- Aprender uma nova música.
- Participar da aula.

---

## Mensal

Objetivos maiores.

Exemplos:

- Concluir um módulo.
- Memorizar três músicas.

---

## Missão da Jornada

Relacionada ao progresso permanente daquela jornada.

Exemplos:

- Aprender todos os acordes maiores.
- Dominar escalas naturais.

Essas missões normalmente não possuem recorrência.

---

## Missão Especial

Criada para eventos específicos.

Exemplos:

- Preparação para recital.
- Desafio de férias.
- Semana da música.

---

## Missão Secreta

Não aparece inicialmente para a criança.

É revelada apenas após sua conclusão ou quando determinadas condições forem atendidas.

Seu objetivo é incentivar curiosidade e criar momentos de surpresa.

---

## Missão Personalizada

Criada pelos responsáveis.

Exemplos:

- Ajudar a preparar o jantar.
- Organizar os brinquedos.
- Fazer uma boa ação.

---

# Recorrência

Uma missão pode possuir:

- única;
- diária;
- semanal;
- mensal;
- personalizada.

---

# Estados

Uma missão pode estar em:

- Bloqueada
- Disponível
- Em andamento
- Aguardando validação
- Concluída
- Expirada (caso aplicável)

Nem todas as missões utilizam todos os estados.

---

# Critérios de Conclusão

Cada missão define seus próprios critérios.

Exemplos:

- tempo mínimo;
- quantidade;
- conclusão manual;
- confirmação dos pais;
- validação automática;
- combinação de regras.

O Mission System não define como essas validações acontecem.

Ele apenas registra o resultado.

---

# Sessões

Algumas missões podem exigir uma ou mais sessões.

Exemplo:

Missão

↓

Praticar Piano

↓

Sessão

30 minutos

↓

Sessão concluída

↓

Missão atualizada

Sessões representam momentos de prática.

Não são obrigatórias para todas as missões.

---

# Relação com Objetivos

Missões aproximam a criança de seus objetivos.

Exemplo:

Objetivo

↓

Aprender "Ode à Alegria"

↓

Missões

- Escala
- Mão direita
- Mão esquerda
- Juntar as mãos

---

# Relação com Eventos

Eventos podem criar missões temporárias.

Exemplo:

Recital

↓

Missões

- Ensaiar música
- Revisar postura
- Treinar entrada no palco

---

# Relação com Reward System

Ao concluir uma missão, o Mission System publica um evento.

O Reward System decide quais recompensas serão concedidas.

---

# Relação com Parent Companion

Os responsáveis podem:

- criar missões;
- editar missões;
- ativar ou desativar missões;
- acompanhar progresso;
- validar conclusão.

---

# Organização

As missões podem ser agrupadas por:

- jornada;
- categoria;
- prioridade;
- recorrência.

Essa organização facilita a navegação da criança e dos responsáveis.

---

# MVP

O MVP contempla:

- missões diárias;
- semanais;
- da jornada;
- personalizadas;
- progresso;
- estados;
- integração com Reward System.

Missões secretas e especiais poderão ser adicionadas posteriormente.

---

# Backlog

Possíveis evoluções:

- missões cooperativas;
- cadeias de missões;
- missões ramificadas;
- missões sazonais;
- sugestões por IA;
- dificuldade adaptativa;
- missões em grupo;
- missões surpresa;
- missões compartilhadas entre irmãos.

---

# Princípios

Toda missão deve:

- ser simples de compreender;
- possuir um objetivo claro;
- incentivar constância;
- respeitar o ritmo da criança;
- contribuir para a evolução da jornada.

Missões nunca devem incentivar excesso de prática, comparação entre crianças ou sentimento de punição.