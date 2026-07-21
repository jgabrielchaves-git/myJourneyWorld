# Journey World
## Game Domain Model

Versão: 1.0 (Draft)

Status: Ativo

Este documento define o modelo conceitual oficial do Journey World.

Toda funcionalidade implementada deve utilizar este modelo.

Nenhuma entidade poderá ser criada sem atualização deste documento.

> **Nota:** A ordem de autoridade "Game Domain Model → Glossary → Product Owner" descrita ao final deste documento conflita com o `CLAUDE.md`, que define `docs/domain/Glossary.md` como **a única fonte oficial de nomenclatura**. Em caso de dúvida de nomenclatura, `Glossary.md` prevalece. **Atualizado (2026-07-21):** "Mundo" renomeado para "Reino" em todo o documento (`docs/domain/Glossary.md`); XP e Nível removidos como entidades (decisão definitiva — sem XP no MVP, ver `docs/Decision_Log.md`) e substituídos pela Árvore do Crescimento. **Resolvido (2026-07-21):** a relação Objetivo/Missão/Sessão foi decidida pelo Product Owner (`docs/Decision_Log.md`) — Objetivo pertence ao Reino (não é uma condição dentro de uma Missão); Sessão é o registro de execução de uma Missão (não um conceito em avaliação). Camadas abaixo atualizadas para refletir isso.

---

# Objetivo

Padronizar todos os conceitos do domínio.

Evitar duplicidade.

Evitar inconsistências.

Servir como referência para:

- documentação;
- implementação;
- UX;
- assets;
- IA.

---

# Camada 1
## Identidade

Representa quem participa da jornada.

### Criança

A protagonista da experiência.

Possui:

- Personagem
- Progressão
- Coleções
- Histórico
- Reinos

---

### Responsável

Responsável por configurar e acompanhar a jornada.

Nunca participa da progressão.

Nunca possui estrelas.

Interage apenas através do Parent Companion.

---

### Personagem

Representação visual permanente da criança.

Possui:

- roupas
- acessórios
- animações
- emoções

Nunca é substituído.

---

# Camada 2
## Jornada

### Reino

Maior unidade jogável.

Exemplo:

Reino do Piano.

---

Um Reino possui:

- habilidades
- missões
- eventos
- músicas
- conquistas

---

### Jornada

Representa toda a evolução da criança.

Todos os Reinos fazem parte da mesma jornada.

---

### Objetivo

Conquista de um Reino, concluída uma única vez.

Pertence ao Reino — não é uma condição dentro de uma Missão.

Exemplos:

Tocar a primeira música completa.

Dominar as notas naturais.

---

### Sessão

Registro de execução de uma Missão.

Gerada sempre que uma Missão é executada — o cronômetro é apenas uma forma opcional de gerar uma Sessão, não a única.

Uma sessão contém:

- missão de origem
- duração (ou "não aplicável", se sem cronômetro)
- data/hora

---

# Camada 3
## Atividades

### Missão

Atividade oferecida pelo jogo.

Exemplos:

Praticar 1 hora.

Fazer escalas.

Treinar acordes.

---

### Evento

Meta temporária.

Exemplos:

Recital.

Apresentação.

Festival.

---

### Música

Representa uma música completa.

Possui progresso próprio.

---

# Camada 4
## Progressão

### Árvore do Crescimento

Representa a evolução da criança dentro de uma Jornada/Reino.

Cresce a cada Missão concluída. Nunca regride. Substitui XP/Nível (removidos, decisão definitiva).

---

### Estrela

Representa dedicação acumulada.

Características:

✔ Nunca é gasta.

✔ Nunca diminui.

✔ Desbloqueia conteúdos.

✔ Mede progresso global.

Não faz parte da economia.

---

### Moeda

Representa a economia do jogo.

Características:

✔ Pode ser gasta.

✔ Obtida em missões.

✔ Utilizada na loja.

Nunca influencia progressão.

---

# Camada 5
## Coleções

### Adesivo

Colecionável permanente.

Pode possuir versões especiais.

---

### Álbum

Coleção organizada de adesivos.

---

### Medalha

Reconhecimento importante.

Obtida por grandes conquistas.

---

### Troféu

Maior reconhecimento de um Reino.

Representa domínio.

---

# Camada 6
## Parent Companion

### Configuração

Permite personalizar a jornada.

---

### Recompensa

Benefício criado pelos pais.

Exemplos:

Passeio.

Sorvete.

Cinema.

Dormir mais tarde.

As recompensas pertencem ao mundo real.

---

### Mensagem

Mensagem enviada pelos pais.

Pode ser:

- imediata;
- programada;
- desbloqueada.

---

### Diário

Registro emocional da jornada.

---

### Timeline

Linha do tempo permanente.

---

### Relatório

Resumo narrativo da evolução.

---

### Validação

Processo de confirmação das atividades.

Possui modos:

Manual.

Automático.

Híbrido.

---

# Camada 7
## Progressão Permanente

### Árvore de Habilidades

Representa domínio das competências.

---

### Caminho

Sequência dentro de uma árvore.

---

### Conquista

Marco permanente.

Pode gerar:

adesivos

medalhas

troféus

---

# Relacionamentos

Uma Jornada possui vários Reinos.

Um Reino possui vários Objetivos e várias Missões.

Uma Missão, ao ser executada, gera uma Sessão (registro da execução).

Missões geram:

Moedas

Estrelas

Conquistas

Evolução da Árvore do Crescimento

Conquistas geram:

Adesivos

Medalhas

Troféus

Os Pais gerenciam a Jornada através do Parent Companion.

---

# Regras de Domínio

Estrelas nunca são gastas.

A Árvore do Crescimento nunca regride.

Moedas nunca desbloqueiam progresso.

Cosméticos nunca alteram atributos.

Toda recompensa real é criada pelos pais.

Toda conquista é permanente.

Toda funcionalidade nova deve pertencer a uma entidade existente.

Caso contrário:

criar RFC

↓

atualizar Domain Model

↓

atualizar Glossary

↓

implementar

---

# Naming Rules

Não criar sinônimos.

Não alterar conceitos existentes.

Toda entidade utiliza apenas um nome oficial.

Em caso de dúvida:

Game Domain Model

↓

Glossary

↓

Product Owner