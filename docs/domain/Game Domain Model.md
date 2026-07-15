# Journey World
## Game Domain Model

Versão: 1.0 (Draft)

Status: Ativo

Este documento define o modelo conceitual oficial do Journey World.

Toda funcionalidade implementada deve utilizar este modelo.

Nenhuma entidade poderá ser criada sem atualização deste documento.

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
- Mundos

---

### Responsável

Responsável por configurar e acompanhar a jornada.

Nunca participa da progressão.

Nunca possui XP.

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

### Mundo

Maior unidade jogável.

Exemplo:

Mundo Piano.

---

Um mundo possui:

- habilidades
- missões
- eventos
- músicas
- conquistas

---

### Jornada

Representa toda a evolução da criança.

Todos os mundos fazem parte da mesma jornada.

---

### Sessão (Proposto)

Representa um período de prática.

Estado:

🟡 Em avaliação.

Caso aprovado, substituirá o conceito de "tempo de estudo".

Uma sessão poderá conter:

- início
- fim
- duração
- objetivos
- validação

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

### Objetivo

Uma condição específica dentro de uma missão.

Uma missão pode possuir vários objetivos.

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

### Estrela

Representa dedicação acumulada.

Características:

✔ Nunca é gasta.

✔ Nunca diminui.

✔ Desbloqueia conteúdos.

✔ Mede progresso global.

Não faz parte da economia.

---

### XP

Representa experiência.

Utilizado para subir níveis.

Nunca pode ser gasto.

---

### Nível

Representa evolução contínua.

Obtido através de XP.

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

Maior reconhecimento de um mundo.

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

Uma Jornada possui vários Mundos.

Um Mundo possui várias Missões.

Uma Missão possui vários Objetivos.

Uma Sessão pode concluir várias Missões.

Missões geram:

XP

Moedas

Estrelas

Conquistas

Conquistas geram:

Adesivos

Medalhas

Troféus

Os Pais gerenciam a Jornada através do Parent Companion.

---

# Regras de Domínio

Estrelas nunca são gastas.

XP nunca pode diminuir.

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