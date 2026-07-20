# Journey World
# UI - Screen Map

**Versão:** 1.0
**Status:** Draft

> **Visão (pós-MVP).** Este documento descreve o modelo de navegação Jardim → Reino → Região, incluindo Login/Splash — fora do escopo do MVP congelado (`CLAUDE.md`, `docs/product/Charter.md`, que proíbe Login). Ver `docs/Decision_Log.md` (2026-07-20). "MVP" abaixo refere-se ao MVP dessa visão futura, não ao MVP ativo. Não implementar sem decisão explícita retomando esta fase.

---

# Objetivo

Este documento define todas as telas do MVP e como o usuário navega entre elas.

Seu objetivo é fornecer uma visão macro da aplicação antes da implementação detalhada.

---

# Fluxo Principal

Splash

↓

Login

↓

Casa

↓

Jardim

↓

Reino

↓

Região

↓

Missão

↓

Conclusão

↓

Casa

---

# Estrutura do MVP

## Autenticação

- Splash
- Login

---

## Home

- Casa

---

## Jardim

- Jardim
- Seleção de Jornada

---

## Reino

- Mapa do Reino
- Seleção de Região

---

## Região

- Objetivos
- Missões

---

## Missão

- Detalhes da Missão
- Concluir Missão

---

## Conclusão

- Resumo da Missão
- Recompensas
- Atualização da Árvore
- Registro no Storybook

---

## Storybook

- Timeline
- Diário (MVP simples)

---

## Perfil

- Perfil da Criança

---

## Configurações

- Conta
- Família
- Preferências

---

# Navegação

Splash

↓

Login

↓

Casa

├── Jardim

├── Storybook

├── Perfil

└── Configurações

---

Jardim

↓

Escolher Jornada

↓

Mapa do Reino

↓

Escolher Região

↓

Objetivos

↓

Missões

↓

Conclusão

↓

Casa

---

# Telas MVP

## 1. Splash

Objetivo:

Inicializar aplicação.

---

## 2. Login

Objetivo:

Autenticação.

---

## 3. Casa

Objetivo:

Hub principal.

---

## 4. Jardim

Objetivo:

Escolher qual Jornada será cultivada.

---

## 5. Reino

Objetivo:

Visualizar progresso da Jornada.

---

## 6. Região

Objetivo:

Apresentar objetivos e missões.

---

## 7. Missão

Objetivo:

Executar uma atividade.

---

## 8. Conclusão

Objetivo:

Celebrar a conquista.

---

## 9. Storybook

Objetivo:

Consultar a jornada vivida.

---

## 10. Perfil

Objetivo:

Visualizar informações da criança.

---

## 11. Configurações

Objetivo:

Gerenciar a aplicação.

---

# Funcionalidades Futuras

- Loja
- Inventário
- Pets
- Coleções
- Calendário
- Eventos
- Notificações
- Marketplace
- Social
- Conquistas avançadas

Essas telas não fazem parte do MVP.

---

# Princípios

O usuário deve conseguir acessar qualquer funcionalidade principal em no máximo três interações.

A navegação deve ser simples, previsível e consistente.

Cada tela deve possuir uma responsabilidade clara e bem definida.