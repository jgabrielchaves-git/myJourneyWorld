# Journey World
# Domain - World Model

**Versão:** 1.0
**Status:** Draft

> **Visão (pós-MVP).** Este documento inclui Capítulos e Sessões como parte obrigatória de toda Jornada — o MVP ativo do Reino do Piano usa Região (não "Capítulo") e não expõe Sessão como entidade própria (`docs/game-design/GDD/GDD.md`). Ver `docs/Decision_Log.md` (2026-07-20).
>
> **Correção (2026-07-21):** a relação "Sessão ⊃ Missões" nas seções "Missões"/"Sessões" abaixo está **desatualizada** — o modelo oficial (`docs/Decision_Log.md`) é o oposto: uma Missão, ao ser executada, gera uma Sessão (registro da execução), não o contrário. Ver `docs/domain/Glossary.md`. A seção "MVP" abaixo refere-se ao MVP desta visão futura, não ao MVP ativo.

---

# Objetivo

Este documento define o conceito de Jornada (World) dentro do Journey World.

Uma Jornada representa um universo temático onde a criança desenvolve habilidades específicas através da plataforma.

Cada Jornada possui identidade própria, conteúdo próprio e progressão própria, mas reutiliza todos os sistemas centrais do Journey World.

---

# Filosofia

Cada criança vive diversas jornadas ao longo da vida.

Aprender piano.

Aprender a ler.

Praticar esportes.

Desenvolver sua vida espiritual.

O Journey World transforma cada uma dessas jornadas em uma experiência significativa, mantendo uma linguagem e uma experiência unificadas.

---

# O que é uma Jornada?

Uma Jornada é um conjunto organizado de experiências relacionadas a um determinado tema.

Ela possui:

- identidade visual;
- objetivos;
- capítulos;
- missões;
- eventos;
- coleções;
- progressão.

Ela não implementa regras próprias de economia, recompensas ou gamificação.

Esses comportamentos pertencem aos sistemas da plataforma.

---

# Estrutura

Toda Jornada é composta por:

- Identidade
- Capítulos
- Objetivos
- Missões
- Sessões
- Eventos
- Progressão
- Coleções
- Configurações

---

# Identidade

Cada Jornada possui personalidade própria.

Pode definir:

- nome;
- descrição;
- ícone;
- cor principal;
- cores secundárias;
- música ambiente;
- efeitos sonoros;
- cenário;
- mascote;
- personagens;
- estilo artístico.

A identidade deve permitir que a criança reconheça imediatamente em qual mundo está.

---

# Capítulos

Os capítulos organizam o progresso macro da Jornada.

Exemplo:

Piano

Capítulo 1

Conhecendo o Instrumento

Capítulo 2

Primeiras Melodias

Capítulo 3

Acordes

Capítulo 4

Primeiras Apresentações

Cada Jornada define sua própria estrutura.

---

# Objetivos

Cada capítulo contém objetivos.

Os objetivos representam grandes conquistas de aprendizado.

Exemplos:

- Conhecer o teclado.
- Aprender a primeira música.
- Dominar escalas maiores.

---

# Missões

Cada objetivo é dividido em pequenas missões.

As missões representam tarefas concretas e executáveis.

Exemplos:

- Encontrar o Dó Central.
- Praticar mão direita.
- Executar uma escala.

---

# Sessões

As sessões representam momentos reais de prática.

Exemplo:

30 minutos de estudo.

Uma missão pode exigir uma ou mais sessões.

---

# Eventos

Uma Jornada pode possuir eventos.

Exemplos:

- recital;
- apresentação;
- culto;
- competição;
- avaliação.

Eventos aproximam a experiência digital da vida real.

---

# Progressão

Cada Jornada define:

- ordem dos capítulos;
- desbloqueios;
- dependências;
- novos conteúdos.

A lógica de progressão utiliza o Progression Model da plataforma.

---

# Coleções

Cada Jornada pode possuir:

- adesivos;
- medalhas;
- troféus;
- coleções exclusivas.

Esses itens utilizam o Collections System.

---

# Configurações

Cada Jornada pode configurar:

- duração das sessões;
- tipos de missão;
- frequência sugerida;
- eventos;
- recompensas disponíveis;
- coleções;
- validação.

---

# Relação com os Systems

Uma Jornada reutiliza os sistemas da plataforma.

Utiliza:

- Mission System;
- Goal System;
- Reward System;
- Economy;
- Collections;
- Parent Companion;
- Events;
- Progression.

Ela nunca implementa esses sistemas.

---

# Relação com o Avatar

Todas as Jornadas compartilham o mesmo Avatar.

O progresso é específico da Jornada, mas a identidade da criança permanece única em toda a plataforma.

---

# Relação com a Casa

As conquistas obtidas em qualquer Jornada podem ser exibidas na Casa.

Exemplos:

- troféus;
- medalhas;
- itens decorativos;
- lembranças.

A Casa funciona como um espaço compartilhado entre todas as Jornadas.

---

# Expansibilidade

Novas Jornadas devem ser criadas apenas adicionando conteúdo.

Não deve ser necessário alterar a arquitetura da plataforma.

---

# MVP

O MVP contempla:

- uma Jornada (Piano);
- capítulos;
- objetivos;
- missões;
- sessões;
- eventos;
- coleções;
- progressão.

As demais Jornadas serão adicionadas posteriormente reutilizando esta estrutura.

---

# Backlog

Possíveis evoluções:

- Jornadas colaborativas;
- Jornadas sazonais;
- Jornadas patrocinadas;
- Jornadas criadas pela comunidade;
- Marketplace de Jornadas;
- Jornadas geradas por IA.

---

# Princípios

Toda Jornada deve:

- possuir identidade própria;
- reutilizar os sistemas da plataforma;
- incentivar crescimento real;
- preservar memórias;
- ser facilmente expandida.

Nenhuma Jornada deve depender da implementação de outra.

Todas devem seguir a mesma arquitetura.