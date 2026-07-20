# Journey World
# Architecture

**Versão:** 0.1 (Draft)
**Status:** Em evolução

---

# Objetivo

Este documento descreve a arquitetura conceitual do Journey World.

Seu objetivo é explicar como os diferentes sistemas da plataforma se relacionam, quais são suas responsabilidades e quais princípios devem orientar sua implementação.

Este documento não define tecnologias específicas (React, Firebase, Supabase, etc.). Seu foco é a arquitetura do produto.

---

# Princípios Arquiteturais

A arquitetura do Journey World deve ser:

- Modular;
- Orientada a domínio;
- Orientada a eventos;
- Configurável;
- Escalável;
- Extensível;
- Simples para o MVP.

Sempre que possível, novos recursos devem ser adicionados por configuração, e não por alteração da arquitetura existente.

---

# Camadas

```
Product

↓

Journeys (Worlds)

↓

Gameplay

↓

Systems

↓

Persistence

↓

Platform
```

---

# Domínio

O domínio representa os conceitos permanentes do produto.

Exemplos:

- Jornada
- Objetivo
- Sessão
- Missão
- Estrela
- Moeda
- Adesivo
- Medalha
- Troféu

Esses conceitos são independentes de qualquer mundo.

---

# Worlds

Cada mundo implementa apenas seu conteúdo.

Exemplos:

- Piano
- Ginástica
- Escola
- Vida Espiritual

Os mundos nunca implementam regras de economia ou progressão.

Eles apenas utilizam os sistemas existentes.

---

# Gameplay

Responsável pela experiência da criança.

Exemplos:

- interface;
- interações;
- animações;
- navegação;
- feedback visual.

O Gameplay nunca altera diretamente a economia ou a progressão.

---

# Systems

Os Systems concentram toda a lógica reutilizável da plataforma.

Exemplos:

- Progression
- Economy
- Reward System
- Parent Companion
- Collections
- Events

Os mundos utilizam esses sistemas, mas não os implementam.

---

# Comunicação

Os sistemas se comunicam através de eventos.

Fluxo simplificado:

Gameplay

↓

Evento

↓

Reward System

↓

Eventos de Domínio

↓

Economy

Collections

Parent Companion

Timeline

Analytics

Cada sistema reage apenas aos eventos que lhe interessam.

---

# Responsabilidades

## World

Produzir eventos.

Exemplo:

Objetivo concluído.

---

## Reward System

Avaliar regras.

Entregar recompensas.

---

## Economy

Atualizar moedas.

Atualizar estrelas.

---

## Collections

Atualizar adesivos.

Atualizar medalhas.

Atualizar troféus.

---

## Parent Companion

Atualizar Inbox.

Gerar notificações.

Atualizar relatórios.

---

## Timeline

Registrar acontecimentos importantes da jornada.

---

# Configuração

Sempre que possível:

Configuração > Código

Novas jornadas devem reutilizar os sistemas existentes.

---

# Evolução

A arquitetura foi projetada para suportar:

- múltiplas jornadas;
- novos sistemas;
- multiplayer;
- sincronização;
- IA;
- plataforma mobile;
- plataforma web.

Sem necessidade de alterar os conceitos centrais.

---

# Documentos Relacionados

- Product Vision
- Game Domain Model
- Progression Model
- Economy
- Reward System

---

# Backlog

Este documento será expandido futuramente com:

- Arquitetura Front-end
- Arquitetura Back-end
- Persistência
- Sincronização Offline
- Eventos de Domínio
- Fluxo de Dados
- Estados da Aplicação
- Sistema de Plugins
- Assets Pipeline
- Performance
- Segurança