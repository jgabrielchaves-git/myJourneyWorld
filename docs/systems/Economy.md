# Journey World
# System - Economy

**Versão:** 1.0  
**Status:** Draft

---

# Objetivo

Este documento define o sistema econômico do Journey World.

Seu objetivo é estabelecer os recursos econômicos existentes, seus significados, seu comportamento e a forma como podem ser utilizados.

A economia do Journey World existe para apoiar a jornada da criança, incentivando dedicação, autonomia e escolhas conscientes.

As regras que determinam quando uma recompensa é concedida pertencem ao documento **Reward System**.

---

# Filosofia

A economia do Journey World não existe para criar escassez.

Ela existe para dar significado às escolhas da criança.

Todo recurso econômico deve incentivar:

- dedicação;
- planejamento;
- autonomia;
- personalização;
- experiências positivas.

Nenhum recurso deve substituir o valor da prática no mundo real.

---

# Princípios

## A prática sempre vem primeiro

Toda recompensa deve ser consequência de uma atividade real.

---

## O progresso nunca é perdido

Estrelas nunca diminuem.

Conquistas nunca desaparecem.

Memórias nunca são apagadas.

---

## Escolhas possuem significado

A criança decide como utilizar suas moedas.

Nem tudo pode ser adquirido imediatamente.

Aprender a escolher também faz parte da jornada.

---

## Simplicidade

Cada recurso possui apenas um propósito.

Nenhum recurso deve duplicar o significado de outro.

---

# Recursos Econômicos

Journey World possui dois recursos econômicos.

## ⭐ Estrelas

Representam dedicação acumulada.

São permanentes.

Nunca são gastas.

Nunca diminuem.

Nunca expiram.

Cada jornada possui sua própria quantidade de estrelas.

As estrelas representam histórico.

Não representam saldo.

---

## 🪙 Moedas

Representam poder de troca.

Permitem adquirir recompensas.

Podem ser acumuladas.

Podem ser gastas.

Nunca expiram.

As moedas pertencem ao perfil da criança e são compartilhadas entre todas as jornadas.

---

# Estrelas

## Significado

As estrelas registram a dedicação da criança dentro de uma jornada.

Elas não representam habilidade.

Não representam talento.

Não representam desempenho.

Representam esforço e constância.

---

## Escopo

Cada jornada possui sua própria contagem.

Exemplo

Piano

⭐⭐⭐⭐⭐⭐⭐⭐⭐

Ginástica

⭐⭐⭐⭐⭐

Escola

⭐⭐⭐⭐⭐⭐⭐⭐⭐⭐

Também é possível visualizar a soma total de estrelas conquistadas em todas as jornadas para fins estatísticos.

---

## Utilização

As estrelas podem ser utilizadas como requisito para desbloqueios permanentes.

Exemplos:

- funcionalidades;
- áreas;
- baús;
- novos conteúdos;
- cosméticos exclusivos;
- recompensas da família.

As estrelas nunca são consumidas.

Elas apenas comprovam que determinado marco foi alcançado.

---

# Moedas

## Significado

Moedas representam recursos de troca.

Permitem que a criança personalize sua experiência.

Também permitem trocar dedicação por experiências configuradas pelos responsáveis.

---

## Utilização

As moedas podem ser utilizadas em diferentes catálogos.

Todos os catálogos compartilham o mesmo saldo.

---

# Catálogo Journey World

Itens digitais.

Exemplos

- roupas;
- acessórios;
- penteados;
- instrumentos;
- pets;
- animações;
- expressões;
- efeitos visuais.

Nenhum item oferece vantagem de gameplay.

Seu objetivo é expressão e personalização.

---

# Catálogo da Família (Visão — pós-MVP)

> Fora do MVP. Contraria o princípio congelado "moedas compram apenas cosmético — nunca vantagem ou progresso" (`docs/product/Principles.md`, `docs/game-design/GDD/GDD.md`). Ver `docs/Decision_Log.md` (2026-07-20). Não implementar sem decisão explícita do Product Owner revendo essa restrição.

Configurado pelos responsáveis.

Exemplos

- sorvete;
- cinema;
- passeio;
- brinquedo;
- viagem;
- escolher o filme da noite;
- passeio de bicicleta;
- dormir um pouco mais tarde.

Cada família define seu próprio catálogo.

---

# Resgate de Recompensas (Visão — pós-MVP)

> Depende do Catálogo da Família (acima), portanto também fora do MVP.

Ao solicitar uma recompensa do Catálogo da Família, é criado um Pedido de Resgate.

Fluxo

Solicitação

↓

Inbox dos Pais

↓

Aprovação

↓

Entrega

↓

Histórico

A aprovação pode ser obrigatória ou automática, conforme configuração dos responsáveis.

---

# Histórico de Moedas

Toda movimentação financeira deve permanecer registrada.

Cada lançamento possui:

- data;
- tipo;
- descrição;
- origem;
- quantidade;
- saldo após movimentação.

Exemplo

+20

Sessão de Piano

---

+50

Missão Semanal

---

-120

Sorvete

---

-350

Cinema

---

+30

Evento Especial

O histórico nunca deve ser apagado.

---

# Estatísticas

Além do saldo atual, o sistema mantém informações históricas.

Exemplos

Saldo Atual

1.250 moedas

---

Total Obtido

8.450 moedas

---

Total Gasto

7.200 moedas

---

Maior Compra

Viagem ao Zoológico

---

Moedas Gastas por Categoria

- Cosméticos
- Pets
- Família
- Eventos

Essas informações alimentam os relatórios do Parent Companion.

---

# Balanceamento

A economia deve incentivar constância.

Nunca repetição excessiva.

É preferível recompensar pequenas práticas frequentes do que longas sessões ocasionais.

A economia deve incentivar hábitos saudáveis.

Nunca gerar ansiedade.

---

# Relação com outros Sistemas

Este documento define apenas os recursos econômicos.

Os seguintes sistemas complementam sua utilização:

- Progression Model
- Reward System
- Parent Companion
- Collections
- Events

---

# MVP

O MVP contempla:

- estrelas por jornada;
- moedas globais;
- saldo;
- histórico de moedas;
- catálogo Journey World (cosméticos).

Catálogo da Família, Pedido de Resgate, aprovação pelos pais e estatísticas de gasto por categoria são Visão pós-MVP (ver seções acima).

---

# Backlog

Possíveis evoluções futuras:

- múltiplos catálogos;
- promoções sazonais;
- itens comemorativos;
- presentes entre irmãos;
- presentes entre amigos;
- recompensas compartilhadas;
- cupons;
- lojas temporárias;
- economia entre jornadas;
- moedas especiais de eventos.

Todos esses recursos deverão respeitar os princípios definidos neste documento.