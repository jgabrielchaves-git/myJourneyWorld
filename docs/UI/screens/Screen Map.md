# Journey World
# UI - Screen Map

**Versão:** 1.0
**Status:** Draft

> **Nota de status:** Revertido — ver `docs/Decision_Log.md` ("Revertido: MVP passa a ser a Era 3"). O modelo de navegação Jardim → Reino → Região **é o MVP ativo**. Splash, Login e Perfil foram removidos deste documento (confirmado: fora do MVP, nem no curto prazo). Loja, Coleções (Álbum) e Eventos foram movidos de "Funcionalidades Futuras" para o MVP — já implementados e testados em `index.html`. "Configurações" ainda precisa ser conciliado com "Painel dos Pais" (`docs/domain/Glossary.md`) — pendência aberta, não decidir aqui.

---

# Objetivo

Este documento define todas as telas do MVP e como o usuário navega entre elas.

Seu objetivo é fornecer uma visão macro da aplicação antes da implementação detalhada.

---

# Fluxo Principal

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

## Loja

- Itens cosméticos disponíveis para troca por Moedas

---

## Álbum (Coleções)

- Adesivos desbloqueados
- Adesivos bloqueados (sem aleatoriedade — a criança sabe o que falta)

---

## Eventos

- Lista de eventos (nome, contagem regressiva, checklist do repertório)
- Criação de evento pelo Painel dos Pais

---

## Painel dos Pais

Antes chamada "Configurações" neste documento — mesmo conceito de `docs/domain/Glossary.md`/`docs/systems/Parent Companion.md`, nome unificado.

Navegação interna (abas):

- Resumo (Dashboard): estrelas, moedas, objetivos ativos, sequência, eventos próximos, últimas conquistas
- Inbox: notificações e solicitações de aprovação
- Timeline / Diário: mesma base do Storybook, com visão de gestão (adicionar fotos/comentários)
- Reino do Piano: avançar Região/Repertório
- Eventos: criar/editar/remover
- Relatórios: geral, jornada, hábitos, coleções
- Preferências: PIN, Modo Confiança, notificações, som, idioma

---

# Navegação

Casa

├── Jardim

├── Storybook

├── Loja

├── Álbum (Coleções)

├── Eventos

└── Painel dos Pais

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

## 1. Casa

Objetivo:

Hub principal.

---

## 2. Jardim

Objetivo:

Escolher qual Jornada será cultivada.

---

## 3. Reino

Objetivo:

Visualizar progresso da Jornada.

---

## 4. Região

Objetivo:

Apresentar objetivos e missões.

---

## 5. Missão

Objetivo:

Executar uma atividade.

---

## 6. Conclusão

Objetivo:

Celebrar a conquista.

---

## 7. Storybook

Objetivo:

Consultar a jornada vivida.

---

## 8. Loja

Objetivo:

Trocar Moedas por itens cosméticos.

---

## 9. Álbum (Coleções)

Objetivo:

Consultar adesivos desbloqueados e bloqueados.

---

## 10. Eventos

Objetivo:

Acompanhar eventos futuros e seu progresso de preparação.

---

## 11. Painel dos Pais

Objetivo:

Acompanhar, incentivar e configurar a jornada da criança (Dashboard, Inbox, Timeline/Diário, Relatórios, Preferências).

---

# Funcionalidades Futuras

- Inventário
- Pets
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