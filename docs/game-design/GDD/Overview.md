# Journey World
## Game Design Document
### Overview

Versão: 1.0

Status: Em elaboração

> **Nota:** `docs/game-design/GDD/GDD.md` continua o documento oficial (fonte única de regras de jogo, `CLAUDE.md`). Este Overview é material de contexto mais amplo. **Atualizado (2026-07-21):** MVP passa a ser a Era 3 (`docs/Decision_Log.md`) — sem XP/níveis (definitivo, ver menções abaixo), Jardim/Reino do Piano substituem a Casa com abas. Conflito ainda não resolvido: "Cronômetro de prática" no MVP entra em tensão com `docs/game-design/Core Gameplay Loop.md`, que mantém a prática fora do aplicativo (ver também `docs/development/Web Platform Constraints.md`, item 3, sobre cronômetro em segundo plano na web). A referência abaixo a "Core Journey Loop" é um nome antigo do atual `docs/game-design/Core Gameplay Loop.md`.

---

# Objetivo

Este documento apresenta uma visão geral do Journey World sob a perspectiva de Game Design.

Seu objetivo é definir a experiência que será construída ao longo dos demais documentos do GDD.

Os detalhes de implementação, regras específicas e sistemas individuais são descritos em documentos próprios.

---

# O que é o Journey World?

Journey World é uma plataforma de jornadas gamificadas que transforma atividades do mundo real em uma experiência divertida, significativa e memorável.

O aplicativo não substitui a prática.

Ele existe para incentivar, acompanhar e celebrar o desenvolvimento da criança.

O primeiro reino é o Reino do Piano.

No futuro, outros reinos poderão ser adicionados utilizando a mesma estrutura de progressão.

Exemplos:

- Piano
- Ginástica Rítmica
- Escola
- Hábitos
- Vida Espiritual

---

# Público-alvo

Primário

• Crianças entre aproximadamente 6 e 12 anos.

Secundário

• Pais ou responsáveis que desejam acompanhar e incentivar o desenvolvimento dos filhos.

---

# Objetivo do Produto

Criar uma experiência que motive a criança a praticar atividades reais com constância, transformando pequenas evoluções em conquistas memoráveis.

O sucesso do Journey World não será medido pelo tempo de uso do aplicativo.

Será medido pelo impacto positivo na rotina da criança.

---

# Filosofia de Design

Todo elemento do jogo deve seguir cinco princípios.

## Realidade em Primeiro Lugar

O progresso acontece fora do aplicativo.

O aplicativo apenas representa essa evolução.

---

## Motivação Sustentável

O objetivo não é criar dependência.

O objetivo é criar disciplina, satisfação e orgulho pela evolução.

---

## Pais como Mentores

Os pais são participantes ativos da jornada.

Eles planejam desafios, acompanham a evolução e celebram conquistas.

Nunca atuam apenas como fiscais.

---

## Crescimento Contínuo

A jornada nunca recomeça.

Tudo que foi conquistado permanece como parte da história da criança.

---

## Memórias Duradouras

O aplicativo deve registrar momentos importantes que poderão ser revisitados no futuro.

Cada medalha, troféu, conquista ou mensagem representa uma lembrança da jornada.

---

# Estrutura do Produto

Journey World é composto por quatro grandes pilares.

## Jornada da Criança

Onde acontece toda a experiência principal.

Inclui:

- personagem;
- missões;
- progressão;
- coleções;
- exploração.

---

## Parent Companion

Espaço dedicado aos pais.

Permite:

- configurar objetivos;
- criar eventos;
- acompanhar progresso;
- validar atividades;
- configurar recompensas;
- enviar mensagens;
- celebrar conquistas.

---

## Motor de Progressão

Sistema responsável por toda a evolução do jogador.

Inclui:

- Árvore do Crescimento;
- estrelas;
- moedas;
- desbloqueios;
- conquistas.

---

## Reinos

Cada Reino representa uma área de desenvolvimento.

Todos compartilham o mesmo sistema de progressão.

Cada Reino possui suas próprias habilidades, objetivos e desafios.

---

# Escopo do MVP

O MVP tem como objetivo validar a hipótese de que a gamificação pode aumentar a motivação da criança para praticar piano.

Inclui:

- Reino do Piano;
- Personagem;
- Casa, Jardim;
- Árvore do Crescimento;
- Missões diárias;
- Painel dos Pais rico (Dashboard, Inbox, Timeline, Relatórios);
- Sistema de estrelas;
- Sistema de moedas;
- Loja de cosméticos;
- Eventos;
- Cronômetro de prática (opcional, não autoritativo).

Tudo o que não contribuir diretamente para validar essa hipótese deverá permanecer no backlog.

---

# Critérios de Sucesso

O MVP será considerado bem-sucedido quando:

- a criança demonstrar vontade espontânea de utilizar o aplicativo;
- a frequência de estudos aumentar;
- os pais participarem ativamente da jornada;
- o aplicativo gerar momentos positivos entre pais e filhos;
- o piano passar a ser associado a uma experiência divertida e significativa.

---

# O que não faz parte do MVP

Não serão desenvolvidos nesta primeira versão:

- multiplayer;
- rankings competitivos;
- chat;
- compras com dinheiro real;
- publicidade;
- minijogos independentes;
- sistemas de energia;
- mecânicas de espera artificial.

---

# Leitura Recomendada

Este documento deve ser lido em conjunto com:

- Product Manifesto;
- Product Vision;
- Product Principles;
- Glossary;
- Game Domain Model;
- Core Gameplay Loop.

Esses documentos formam a base conceitual do Journey World.