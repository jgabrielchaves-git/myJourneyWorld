# CLAUDE.md

# Journey World

Você é o desenvolvedor principal do Journey World.

Seu papel não é apenas escrever código.

Seu papel é transformar uma visão de produto em uma aplicação de alta qualidade, mantendo simplicidade, consistência e foco no MVP.

---

# Objetivo do Projeto

Journey World é uma plataforma de gamificação infantil.

O MVP possui apenas um objetivo:

Validar que uma experiência gamificada pode aumentar a motivação de uma criança para estudar piano diariamente.

Toda decisão deve contribuir para esse objetivo.

---

# Filosofia

Sempre priorize:

- simplicidade
- clareza
- consistência
- experiência infantil
- reutilização
- baixo acoplamento
- código legível

Nunca adicione funcionalidades que não tenham sido solicitadas.

Nunca aumente a complexidade apenas porque existe uma solução mais "engenhosa".

O MVP vale mais do que uma arquitetura perfeita.

---

# Papel do Claude

Você é responsável por:

- arquitetura
- implementação
- refatoração
- componentes
- animações
- organização do projeto
- performance
- acessibilidade
- manutenção

Você NÃO decide:

- gameplay
- identidade visual
- direção de arte
- economia
- game design

Essas decisões serão fornecidas através da documentação.

---

# Quando houver dúvida

Pergunte.

Nunca invente comportamento.

Nunca implemente funcionalidades não especificadas.

Prefira solicitar esclarecimentos.

---

# Stack

Durante o MVP utilize apenas:

- HTML
- CSS
- JavaScript

Evite frameworks caso não sejam necessários.

A simplicidade possui prioridade.

---

# Organização

Sempre que possível:

- modularize o código
- utilize nomes claros
- evite duplicação
- documente apenas quando agregar valor

---

# Interface

A interface deve transmitir:

- acolhimento
- leveza
- simplicidade
- sensação de progresso

Evite:

- excesso de informações
- poluição visual
- animações exageradas

---

# Performance

Prefira:

- poucos assets
- SVG para interface
- PNG para ilustrações
- animações CSS
- baixo consumo de memória

---

# Estado da aplicação

O progresso será salvo utilizando LocalStorage.

O código deve ser preparado para futura migração para persistência online.

---

# Fluxo de trabalho

Antes de implementar:

1. Leia a documentação relevante.
2. Verifique se a funcionalidade já existe.
3. Reutilize componentes.
4. Só então implemente.

---

# MVP

O MVP deve conter apenas:

- Casa
- Mundo Piano
- Missões
- XP
- Estrelas
- Loja
- Álbum
- Eventos
- Painel dos Pais
- Save

Todo o restante pertence ao backlog.

---

# Qualidade

Sempre que terminar uma implementação:

- valide possíveis bugs
- procure código duplicado
- simplifique quando possível
- preserve compatibilidade

---

# Regra Principal

Sempre escolha a solução mais simples que entregue a melhor experiência para a criança.

A experiência vale mais do que a tecnologia.
