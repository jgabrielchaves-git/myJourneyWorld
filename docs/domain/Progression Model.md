# Journey World
# Progression Model

**Versão:** 1.2
**Status:** Draft

> **Parcialmente Visão (pós-MVP).** O modelo de Jornada/Objetivos e a "Loja da Família" descritos aqui são posteriores ao MVP congelado (`CLAUDE.md`, `docs/product/Charter.md`) e contradizem, em alguns pontos, o modelo ativo (`docs/domain/Glossary.md`, `docs/game-design/GDD/GDD.md`) — ver `docs/Decision_Log.md` (2026-07-20). Em especial: Loja da Família não faz parte do MVP ativo (contraria o princípio "moedas compram apenas cosmético"). A seção "MVP" abaixo refere-se ao MVP desta visão futura, não ao MVP ativo.
>
> **Correção (2026-07-21):** a hierarquia "Jornada → Objetivos → Sessões → Missões" abaixo está **desatualizada** — Sessão não é um nível acima de Missão. O modelo oficial (`docs/Decision_Log.md`, 2026-07-21) é: Objetivo pertence ao Reino (não é um contêiner de Sessões); uma Missão, ao ser executada, **gera** uma Sessão (registro da execução). Ver `docs/domain/Glossary.md`. Os diagramas abaixo permanecem como referência histórica desta visão, mas não devem ser seguidos para a relação Objetivo/Sessão/Missão.

---

# Objetivo

Este documento define o modelo oficial de progressão do Journey World.

Seu propósito é estabelecer o significado de cada elemento da jornada da criança, garantindo consistência entre gameplay, sistemas, interface, economia e futuras jornadas.

Sempre que surgir um novo sistema, ele deverá reutilizar os conceitos descritos neste documento.

Este documento responde **o que cada elemento representa**, não como ele será implementado.

---

# Filosofia

O Journey World não mede desempenho.

O Journey World registra crescimento.

Cada elemento da progressão existe para responder uma pergunta diferente sobre a jornada da criança.

Se dois elementos responderem à mesma pergunta, um deles provavelmente deve ser removido.

---

# Hierarquia da Progressão

Toda experiência segue a mesma estrutura.

```
Jornada
    ↓
Objetivos
    ↓
Sessões
    ↓
Missões
    ↓
Validação
    ↓
Recompensas
```

Cada nível possui uma responsabilidade própria.

---

# Jornada

Uma Jornada representa uma área importante da vida da criança.

Exemplos:

- Piano
- Ginástica Rítmica
- Escola
- Vida Espiritual
- Hábitos
- Tarefas da Casa

Características:

- permanente;
- nunca termina;
- possui identidade própria;
- possui objetivos próprios;
- possui progresso próprio;
- pode evoluir continuamente.

---

# Objetivos

Objetivos representam conquistas planejadas.

São metas de médio ou longo prazo.

Exemplos:

- Aprender a música "Noite Feliz";
- Preparar apresentação da igreja;
- Dominar escalas maiores;
- Melhorar leitura de partitura.

Características:

- possuem progresso próprio;
- podem durar dias ou meses;
- são compostos por várias sessões;
- podem gerar grandes recompensas ao serem concluídos.

Uma jornada pode possuir vários objetivos simultaneamente.

---

# Sessões

> **Ver correção no topo do documento (2026-07-21):** uma Sessão é gerada por uma Missão executada (não o contrário). O texto abaixo é mantido como referência histórica desta visão.

Uma Sessão representa um período de prática.

Exemplos:

- Estudo de Piano;
- Aula de Ginástica;
- Estudo Escolar.

Características:

- possui início;
- possui encerramento;
- registra tempo;
- registra atividades realizadas;
- gera progresso.

Uma sessão aproxima a criança de seus objetivos.

---

# Missões

Missões representam pequenas ações executáveis.

Elas orientam a sessão.

Exemplos:

- Praticar escalas;
- Estudar durante 1 hora;
- Treinar compassos 1–8;
- Revisar leitura.

Tipos possíveis:

- Diária
- Semanal
- Mensal
- Objetivo
- Evento
- Jornada
- Secreta
- Personalizada pelos Pais

Missões são altamente configuráveis.

O tipo é apenas uma característica.

---

# Validação

Após concluir uma sessão, suas missões podem ser validadas.

A validação pode ocorrer de diferentes formas:

- automática;
- confirmação dos pais;
- aprovação parcial;
- modo de confiança.

A forma de validação é configurável por jornada e por missão.

---

# Estrelas

## Significado

Representam dedicação acumulada.

Não representam talento.

Não representam desempenho.

Representam constância.

---

## Características

- nunca diminuem;
- nunca expiram;
- nunca são gastas;
- pertencem a uma jornada;
- permanecem registradas para sempre.

---

## Utilização

As estrelas podem:

- desbloquear funcionalidades;
- liberar conteúdos;
- abrir baús;
- desbloquear áreas;
- liberar recompensas da família;
- servir como indicador histórico.

---

# Moedas

## Significado

Representam poder de troca.

São utilizadas para adquirir recompensas.

---

## Características

- podem ser acumuladas;
- podem ser gastas;
- podem ser obtidas novamente.

---

## Catálogos

As moedas podem ser utilizadas em diferentes lojas.

### Loja do Jogo

- roupas;
- acessórios;
- pets;
- animações;
- cosméticos.

### Loja da Família

Configurada pelos responsáveis.

Exemplos:

- sorvete;
- cinema;
- passeio;
- viagem;
- brinquedos;
- privilégios.

Novos catálogos poderão surgir futuramente.

---

# Adesivos

## Significado

Adesivos representam memórias.

Eles registram acontecimentos importantes da jornada.

Não representam progresso.

Não representam economia.

Representam lembranças.

---

## Exemplos

- Primeira música;
- Primeiro recital;
- Primeiro hino;
- 100 horas de estudo;
- Natal 2027;
- Aniversário;
- Missão secreta descoberta.

---

## Álbum

Todos os adesivos ficam organizados em uma Pasta de Adesivos.

Ela representa visualmente a história da criança.

Podem existir raridades e versões brilhantes.

---

# Medalhas

## Significado

Representam domínio.

Cada medalha está ligada a uma habilidade.

Exemplos:

- Escalas Bronze;
- Escalas Ouro;
- Leitura Musical Prata;
- Partitura Ouro.

As medalhas permitem visualizar claramente o desenvolvimento técnico da criança.

---

# Troféus

## Significado

Representam acontecimentos extraordinários.

Não encerram uma jornada.

Celebram momentos únicos.

Exemplos:

- Primeiro recital;
- Festival de Piano;
- Um ano de prática;
- 500 sessões realizadas.

Os troféus ficam expostos na Casa como elementos decorativos e emocionais.

---

# Relação entre os Elementos

```
Jornada
    ↓
Objetivos
    ↓
Sessões
    ↓
Missões
    ↓
Validação
    ↓
Recompensas

⭐ Estrelas
Dedicação

🪙 Moedas
Troca

📒 Adesivos
Memórias

🏅 Medalhas
Domínio

🏆 Troféus
Momentos extraordinários
```

Cada elemento possui um significado único.

Nenhum deve substituir outro.

---

# Princípios

Toda evolução do Journey World deverá respeitar os seguintes princípios:

1. O progresso nunca deve ser perdido.
2. A dedicação vale mais do que o talento.
3. Toda conquista deve possuir significado.
4. Toda recompensa deve incentivar continuidade.
5. Toda memória deve ser preservada.
6. A jornada fortalece a relação entre pais e filhos.
7. Toda nova funcionalidade deve reutilizar este modelo.
8. Jornadas nunca terminam; elas evoluem continuamente.

---

# MVP

O MVP implementará:

- Jornadas;
- Objetivos;
- Sessões;
- Missões;
- Validação;
- Estrelas;
- Moedas;
- Loja do Jogo;
- Loja da Família;
- Álbum de Adesivos.

Medalhas e Troféus poderão ser implementados inicialmente de forma simplificada.

---

# Evolução Futura

Este modelo foi projetado para suportar qualquer nova jornada do Journey World.

Novos mundos não devem criar novos conceitos de progressão.

Eles devem reutilizar os conceitos definidos neste documento, garantindo consistência em toda a plataforma.