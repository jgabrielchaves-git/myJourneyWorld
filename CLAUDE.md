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

# Document Hierarchy

Sempre consulte a documentação antes de implementar qualquer funcionalidade.

Os documentos possuem prioridade hierárquica.

Caso dois documentos entrem em conflito, utilize sempre o documento de maior prioridade.

---

## docs/product/Manifesto.md

Propósito do Journey World.

Consultar quando:

- houver dúvida sobre a filosofia do produto;
- uma funcionalidade parecer fugir do propósito;
- existir conflito entre experiência e tecnologia.

Nunca utilizar para implementar detalhes técnicos.

---

## docs/product/Charter.md

Escopo oficial do MVP.

Consultar quando:

- definir prioridades;
- decidir se uma funcionalidade pertence ao MVP;
- validar objetivos do projeto.

---

## docs/product/Vision.md

Visão de longo prazo.

Consultar quando:

- planejar arquitetura;
- evitar decisões que impeçam crescimento futuro;
- compreender a evolução do ecossistema.

Não utilizar como requisito do MVP.

---

## docs/product/Principles.md

Documento mais importante para decisões diárias.

Consultar antes de implementar qualquer funcionalidade.

Este documento define:

- como tomar decisões;
- critérios de UX;
- critérios de produto;
- prioridades.

Sempre possui prioridade sobre preferências pessoais.

---

## docs/game-design/GDD/GDD.md

Fonte oficial das regras do jogo.

Consultar para:

- missões;
- XP;
- estrelas;
- economia;
- progressão;
- loja;
- eventos;
- álbum;
- recompensas.

---

## docs/Art_Bible.md

Fonte oficial da direção artística.

Consultar para:

- cores;
- assets;
- ilustrações;
- personagens;
- cenários;
- ícones;
- animações.

Nunca criar novos estilos visuais sem consultar este documento.

---

## docs/UX_Bible.md

Fonte oficial da experiência do usuário.

Consultar para:

- fluxos;
- navegação;
- acessibilidade;
- componentes;
- layout.

---

## docs/Roadmap.md

Planejamento.

Nunca implementar funcionalidades futuras sem autorização.

---

## docs/Backlog.md

Lista de ideias.

Itens do Backlog NÃO devem ser implementados automaticamente.

Somente após aprovação explícita.

---

## docs/Decision_Log.md

Registro histórico das decisões.

Consultar quando houver dúvida sobre escolhas anteriores.

Nunca alterar decisões registradas sem aprovação.

---

## docs/Playtest_Log.md

Registro dos testes.

Utilizar para compreender problemas encontrados pelos usuários e orientar melhorias.

---

# Single Source of Truth

Cada assunto possui apenas um documento oficial.

Nunca replique regras entre documentos.

Caso uma informação precise ser alterada, altere apenas seu documento oficial.

Os demais documentos devem apenas referenciá-la.

Sempre que receber uma solicitação:

PASSO 1
Identifique qual área da aplicação será alterada.

PASSO 2
Consulte os documentos responsáveis por essa área.

PASSO 3
Verifique se existe alguma decisão registrada.

PASSO 4
Implemente apenas o que foi solicitado.

PASSO 5
Caso perceba inconsistências na documentação, informe antes de implementar.

Nunca assuma requisitos inexistentes.

# Domain Vocabulary

Journey World utiliza uma linguagem oficial definida em `docs/domain/Glossary.md`.

Antes de implementar qualquer funcionalidade:

1. Utilize sempre os termos existentes no Glossary.
2. Nunca crie sinônimos para conceitos já definidos.
3. Nunca renomeie conceitos existentes.
4. Caso um novo conceito seja necessário e não exista no Glossary:
   - interrompa a implementação desse conceito;
   - informe que foi identificado um novo termo de domínio;
   - proponha uma definição;
   - aguarde aprovação do Product Owner;
   - somente após aprovação o termo poderá ser utilizado no código, documentação e interface.

O Glossary é a única fonte oficial de nomenclatura do Journey World.

## Novo Conceito Proposto

Nome:

Descrição:

Motivação:

Onde será utilizado:

Relacionamentos:

Conceitos semelhantes:

Impacto no produto:

Sugestão de inclusão no Glossary: