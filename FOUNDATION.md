# Journey World
# FOUNDATION.md

> Este é o documento mais importante do projeto.
>
> Todo novo colaborador (humano ou IA) deve lê-lo antes de consultar qualquer outro documento.
>
> Seu objetivo é apresentar a visão, os princípios, a arquitetura e o estado atual do Journey World.

> **Nota de status (2026-07-20):** A Missão, Visão e Filosofia abaixo continuam válidas como norte de longo prazo. Porém a "Arquitetura Conceitual" (Casa → Jardim → Reinos → Regiões → Missões → Conclusão → Storybook) é **Visão pós-MVP**, não o MVP ativo. O MVP ativo é o modelo congelado em `CLAUDE.md`/`docs/product/Charter.md`/`docs/game-design/GDD/GDD.md` (Casa com abas, Mundo Piano, Missões, Estrelas, Moedas, XP, Loja, Álbum, Eventos, Painel dos Pais), já implementado em `index.html`. Para regras de MVP em vigor, `CLAUDE.md` continua sendo o documento de maior prioridade para decisões diárias. Ver `docs/Decision_Log.md` (2026-07-20).

---

# O que é o Journey World?

Journey World é um aplicativo de gamificação para desenvolvimento infantil.

Seu propósito não é transformar a vida em um jogo.

Seu propósito é transformar o crescimento pessoal em uma jornada significativa.

O aplicativo acompanha a criança durante anos, registrando seu desenvolvimento, fortalecendo hábitos saudáveis e preservando suas memórias.

O Journey World deve crescer junto com a criança.

---

# Missão

Ajudar crianças e famílias a cultivarem hábitos, talentos e valores através de pequenas ações diárias, registrando essa jornada para toda a vida.

---

# Visão

Cada criança está escrevendo uma história.

O Journey World existe para ajudá-la a cultivar essa história.

---

# Filosofia

A vida é construída todos os dias.

Pequenas escolhas diárias transformam uma vida inteira.

O aplicativo não substitui a vida real.

Ele incentiva a vivê-la.

---

# Princípios Fundamentais

Sempre priorizar:

- simplicidade;
- acolhimento;
- propósito;
- constância;
- autonomia;
- participação da família.

Nunca utilizar mecânicas que incentivem dependência do aplicativo.

---

# Arquitetura Conceitual

Casa

↓

Jardim

↓

Reinos

↓

Regiões

↓

Missões

↓

Conclusão

↓

Storybook

---

# Conceitos Fundamentais

## Casa

Representa o lar da criança.

É o ponto de partida e retorno de todas as jornadas.

---

## Jardim

Representa todas as Jornadas.

Cada árvore corresponde a uma área da vida.

---

## Reinos

Representam grandes áreas de desenvolvimento.

Exemplos:

- Música
- Escola
- Fé
- Movimento

Novos Reinos podem ser adicionados futuramente.

---

## Regiões

Cada Reino é dividido em Regiões.

As Regiões representam grandes etapas de aprendizado.

Não são níveis.

São fases naturais de crescimento.

---

## Missões

Representam pequenas ações realizadas no mundo real.

São a principal mecânica do aplicativo.

---

## Storybook

Registro permanente da jornada da criança.

Reúne:

- conquistas;
- diário;
- fotos;
- mensagens;
- eventos;
- memórias.

---

# Sistemas Principais

Atualmente o projeto possui documentação para:

- Product Principles
- Product Vision
- Domain Model
- Game Design Document
- Gameplay
- Progression
- Economy
- Rewards
- Parent
- Mission System
- Events
- Storybook
- World Design
- Piano Learning Path

---

# Economia

Existem apenas dois recursos principais.

## Estrelas

Representam grandes conquistas.

Nunca diminuem.

São permanentes.

Podem desbloquear conteúdos, funcionalidades, recompensas ou experiências configuradas pelos pais.

Não são uma moeda.

Nunca são gastas.

---

## Moedas

Representam recompensas de curto prazo.

Podem ser gastas.

Podem ser acumuladas.

Podem desbloquear cosméticos e outras recompensas.

Todo gasto deve permanecer registrado em histórico.

---

# Árvores

Cada Jornada possui sua própria árvore.

A árvore representa crescimento.

Nunca regride.

Seu crescimento é permanente.

---

# Recompensas

Uma missão pode conceder qualquer combinação de:

- moedas;
- estrelas;
- adesivos;
- desbloqueios;
- registros;
- recompensas configuradas pelos pais.

Nenhuma recompensa é obrigatória.

---

# Participação da Família

Os pais fazem parte da jornada.

Podem:

- aprovar missões;
- enviar mensagens;
- configurar recompensas;
- acompanhar evolução;
- consultar relatórios;
- receber notificações importantes.

A validação das missões é configurável.

---

# MVP

O objetivo do MVP é validar hipóteses.

Não construir um jogo completo.

As principais hipóteses são:

- a criança deseja voltar amanhã;
- a árvore gera sensação de progresso;
- as missões incentivam prática;
- a família percebe valor;
- o Storybook cria vínculo emocional.

---

# Princípios de Desenvolvimento

Sempre preferir:

- reutilização;
- simplicidade;
- componentes compartilhados;
- baixo acoplamento;
- documentação viva.

Evitar:

- animações complexas;
- sistemas desnecessários;
- funcionalidades sem hipótese clara.

---

# Estrutura da Documentação

docs/

product/

domain/

systems/

worlds/

ui/

features/

architecture/

development/

backlog/

---

# Estado Atual

Arquitetura conceitual concluída.

Documentação principal concluída.

Design System iniciado.

Fluxo do MVP definido.

Reino da Música definido.

Próxima etapa:

Implementação do MVP utilizando Claude Code.

---

# Como tomar decisões

Quando surgir uma nova ideia, sempre responder:

1. Ela melhora a experiência da criança?

2. Ela fortalece a missão do produto?

3. Ela ajuda a validar o MVP?

4. Ela aumenta demasiadamente a complexidade?

5. Pode ser implementada reutilizando componentes existentes?

Caso a resposta para as perguntas 1, 2 ou 3 seja negativa, a funcionalidade deve permanecer no backlog.

---

# Regra mais importante

Journey World não é um jogo.

Journey World é um companheiro para a vida real.

Toda decisão de produto deve reforçar esse princípio.