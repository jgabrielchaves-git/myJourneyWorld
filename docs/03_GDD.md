# 03 — Game Design Document (GDD)

> Este documento descreve o design de jogo do MVP. Decisões aqui pertencem ao produto/game design, não a Claude (ver [CLAUDE.md](../CLAUDE.md) — "Papel do Claude").

## Escopo do MVP

- Personagem kawaii
- Casa simples
- Missões diárias
- Missões semanais
- Estrelas
- Moedas
- XP e níveis
- Loja de cosméticos
- Álbum de adesivos (conquistas)
- Árvore de habilidades do piano
- Calendário e streak
- Painel dos pais com PIN
- LocalStorage

## Mundo Piano

### Áreas

- Técnica
- Escalas
- Acordes
- Cifras
- Partitura
- Ritmo
- Repertório
- Eventos
- Desafios
- Mestres

## Missões Diárias

- 60 minutos de estudo = 1 estrela
- Rodada de escalas = 1 estrela
- Bom comportamento = 1 estrela

## Repertório

Cada música possui progresso em 4 estágios:

1. Aprendendo
2. Quase pronta
3. Dominada
4. Apresentada

## Eventos

Eventos utilizam músicas do repertório (igreja, escola, recital, natal, apresentações futuras).

Cada evento possui:

- data
- checklist
- progresso
- recompensas

## Economia

- Estrelas representam mérito permanente.
- Cada estrela gera moedas.
- Moedas compram apenas cosméticos (nunca vantagem ou progresso).

## Álbum de Adesivos

- As conquistas são adesivos.
- Não há aleatoriedade.
- Algumas conquistas possuem versões: Bronze, Prata, Ouro, Brilhante e Arco-íris.

## Casa

MVP contém:

- quarto
- personagem
- piano
- estante de troféus
- acesso à loja
- acesso ao álbum

## Troféus e Medalhas

Conquistas importantes geram medalhas e troféus, exibidos na estante da casa.

## Requisitos Técnicos

- HTML/CSS/JavaScript
- Responsivo para celular
- Offline
- Arquivo único no MVP
- Salvar em LocalStorage
- Código modular preparado para migração ao Claude Code

## Fora de Escopo (Backlog)

Ver [07_Backlog.md](07_Backlog.md) para a lista completa de funcionalidades pós-MVP.
