# Journey World
# System - Reward System

**Versão:** 1.0  
**Status:** Draft

---

# Objetivo

Este documento define o sistema oficial de recompensas do Journey World.

Seu objetivo é determinar como recompensas são configuradas, quando são disparadas, como são entregues e como ficam registradas.

O sistema foi projetado para ser reutilizado por todas as jornadas da plataforma.

---

# Filosofia

No Journey World, recompensas existem para reconhecer dedicação, celebrar conquistas e fortalecer a motivação da criança.

Elas nunca devem substituir o prazer da atividade em si.

Uma recompensa é consequência de uma jornada de crescimento, nunca seu objetivo principal.

---

# Responsabilidades

O Reward System é responsável por:

- detectar eventos do jogo;
- validar condições;
- selecionar recompensas;
- entregar recompensas;
- registrar histórico;
- notificar outros sistemas.

Não é responsabilidade deste sistema definir:

- saldo de moedas;
- funcionamento das estrelas;
- economia;
- coleções;
- relatórios.

Esses assuntos pertencem aos seus respectivos sistemas.

---

# Fluxo Geral

```
Evento

↓

Condição

↓

Reward Rule

↓

Reward

↓

Entrega

↓

Histórico

↓

Notificação
```

---

# Eventos (Triggers)

Todo processo de recompensa começa com um evento.

Exemplos:

- Sessão concluída
- Missão concluída
- Objetivo concluído
- Evento concluído
- Sequência de dias
- Apresentação realizada
- Mensagem enviada pelos pais
- Aprovação dos pais
- Data comemorativa
- Ação personalizada

Novos eventos poderão ser adicionados futuramente.

---

# Condições

Após um evento ocorrer, condições podem ser avaliadas.

Exemplos:

- primeira vez;
- terceira conclusão;
- cinco dias consecutivos;
- todas as missões completas;
- quantidade mínima de estrelas;
- objetivo específico;
- data especial.

Uma Reward Rule pode possuir nenhuma, uma ou várias condições.

---

# Reward Rule

Uma Reward Rule define:

**Quando** uma recompensa pode acontecer.

Ela é composta por:

- Trigger
- Condições
- Reward

Exemplo

```
Trigger

Missão concluída

↓

Condição

Primeira conclusão

↓

Reward

Primeiro Acorde
```

---

# Reward

Reward representa uma entrega.

Ela funciona como um contêiner de itens.

Uma Reward pode conter:

- nenhum item;
- um item;
- vários itens.

Isso torna o sistema altamente configurável.

---

# Reward Item

Cada item possui significado próprio.

Tipos iniciais:

- ⭐ Star
- 🪙 Coin
- 📒 Sticker
- 🏅 Medal
- 🏆 Trophy
- 🎁 Chest
- 🔓 Unlock
- 💬 Message
- 🎬 Animation

Novos tipos poderão ser adicionados futuramente.

---

# Quantidade

Cada Reward Item pode definir quantidade quando fizer sentido.

Exemplos

```
Coin

20
```

```
Star

1
```

Itens únicos ignoram quantidade.

Exemplos

- Sticker
- Trophy
- Medal

---

# Exemplos

## Missão diária

```
Reward

↓

Coin

20
```

---

## Sessão perfeita

```
Reward

↓

Coin

50

↓

Star

1
```

---

## Primeira música completa

```
Reward

↓

Sticker

Primeira Música

↓

Coin

100
```

---

## Primeiro recital

```
Reward

↓

Trophy

Primeiro Recital

↓

Message

"Parabéns!"
```

---

# Entrega

Ao ser processada, uma Reward gera uma sequência de entregas.

Cada Reward Item é processado individualmente.

Exemplo

```
Reward

↓

Coin

↓

Sticker

↓

Animation

↓

Message
```

Caso um item falhe, os demais não devem ser perdidos.

O sistema deve registrar quais itens foram entregues com sucesso.

---

# Histórico

Toda recompensa entregue deve permanecer registrada.

Cada registro contém:

- data;
- origem;
- trigger;
- reward rule;
- itens entregues;
- status.

Esse histórico será utilizado por:

- Timeline;
- Parent Companion;
- Estatísticas;
- Relatórios.

---

# Notificações

Após uma Reward ser entregue, eventos podem ser enviados para outros sistemas.

Exemplos:

- Parent Companion;
- Inbox;
- Timeline;
- Diário;
- Estatísticas;
- Analytics.

O Reward System não envia notificações diretamente.

Ele apenas publica eventos.

Cada sistema decide como reagir.

---

# Princípios

Todo novo tipo de recompensa deve seguir os seguintes princípios.

## Um item possui apenas um significado.

## Recompensas nunca removem progresso.

## Toda recompensa deve ser rastreável.

## Recompensas podem ser compostas.

## Recompensas podem ser reutilizadas.

## O sistema deve ser totalmente configurável.

---

# MVP

O MVP contempla:

- Trigger;
- Reward Rule;
- Reward;
- Coin;
- Star;
- Sticker;
- Unlock;
- Message;
- Histórico.

Medalhas, Troféus e Baús poderão ser adicionados posteriormente sem alterar a arquitetura.

---

# Backlog

Possíveis evoluções:

- recompensas sazonais;
- recompensas compartilhadas;
- presentes entre crianças;
- recompensas em grupo;
- recompensas ocultas;
- múltiplas Reward Rules por evento;
- prioridades de execução;
- regras condicionais avançadas.

Todas as evoluções deverão respeitar os princípios definidos neste documento.