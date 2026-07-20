# Journey World — Relatório de Revisão Crítica da Documentação

**Data:** 2026-07-19
**Escopo:** Todos os documentos de `/` e `docs/` (leitura integral de 50+ arquivos)
**Natureza:** Análise crítica. Nenhum documento foi alterado. Nenhuma correção é proposta em detalhe — apenas os problemas são apontados.

---

# Sumário Executivo

Os 10 achados mais graves, em ordem de severidade:

1. **O Glossário — a "única fonte oficial de nomenclatura" — contradiz toda a economia do jogo.** `docs/domain/Glossary.md` afirma que a Estrela "é utilizada na loja" e que a Loja é "onde estrelas podem ser trocadas por itens cosméticos". Todos os demais documentos (`FOUNDATION.md`, `docs/systems/Economy.md`, `docs/domain/Progression Model.md`, `docs/domain/Game Domain Model.md`, `docs/product/Principles.md`, `docs/game-design/GDD/GDD.md`, `CURRENT_STATE.md`) dizem o oposto: estrelas **nunca** são gastas e a loja usa **moedas**. Pior: o termo "Moeda" — recurso central do MVP — **não existe no Glossário**. O documento que o `CLAUDE.md` manda tratar como autoridade máxima de vocabulário descreve uma economia que o resto do projeto abandonou.

2. **Existem dois produtos diferentes documentados como se fossem um só.** O "produto A" é o MVP congelado (`CLAUDE.md`, `docs/product/Charter.md`, `docs/game-design/GDD/GDD.md`, `CURRENT_STATE.md`, `index.html`): 5 abas (Casa, Missões, Álbum, Loja, Calendário), estrelas/moedas/XP, PIN dos pais. O "produto B" é o modelo novo (`FOUNDATION.md`, `docs/domain/*`, `docs/UI/screens/*`, `docs/mvp/User Flow.md`): Casa → Jardim → Reinos → Regiões → Missões → Storybook, com Splash, Login, árvores e capítulos. `docs/UI/screens/Screen Map.md` chega a declarar **Loja, Coleções (Álbum), Calendário, Eventos e Notificações como "Funcionalidades Futuras — não fazem parte do MVP"**, contradizendo frontalmente o escopo congelado do `CLAUDE.md`, e inclui **Login**, que o `Charter.md` proíbe explicitamente ("Fora do Escopo: Login, Nuvem").

3. **A hierarquia central do domínio está invertida entre documentos.** `docs/domain/Glossary.md` e `docs/domain/Game Domain Model.md`: Objetivo é uma condição **dentro** de uma Missão ("uma missão pode possuir vários objetivos"). `docs/domain/Goals.md`, `docs/domain/Progression Model.md`, `docs/domain/World Model.md` e `docs/UI/components/Goal Card.md`: **Objetivos são compostos por Missões**. As duas direções são mutuamente exclusivas e ambas estão em documentos "oficiais" de domínio. O mesmo ocorre com Sessão: `Progression Model.md` coloca Sessões **acima** de Missões (Jornada → Objetivos → Sessões → Missões); `World Model.md` e `Mission System.md` dizem que "uma missão pode exigir uma ou mais sessões" (Missão acima de Sessão).

4. **XP e Nível estão no MVP oficial mas não existem nos sistemas que deveriam implementá-los.** XP aparece em `CLAUDE.md`, `Charter.md`, `GDD.md`, `Glossary.md`, `Game Domain Model.md`, `GDD/Overview.md`, `GDD/Gameplay.md` e `Core Gameplay Loop.md`. Porém: o `Progression Model.md` (modelo **oficial** de progressão) não menciona XP nem Nível; `Economy.md` diz que existem "dois recursos"; `Reward System.md` não possui um Reward Item de XP (só Star, Coin, Sticker, Medal, Trophy, Chest, Unlock, Message, Animation); `FOUNDATION.md` afirma "existem apenas dois recursos principais". É impossível conceder XP seguindo os documentos de sistema. O slice atual agrava: nível = estrelas/5+1 (`CURRENT_STATE.md`), contrariando "Nível baseado em XP" do Glossário.

5. **O Catálogo da Família viola um princípio congelado do produto.** `docs/product/Principles.md` e `CURRENT_STATE.md` (decisões congeladas): "Moedas compram **apenas cosmético**". Mas `docs/systems/Economy.md`, `docs/domain/Progression Model.md` ("Loja da Família") e `docs/systems/Parent Companion.md` (CRUD de recompensas com "custo em moedas") definem moedas comprando sorvete, cinema, viagem e privilégios — e colocam isso **no MVP**. Paralelamente, `FOUNDATION.md` e o próprio `Progression Model.md` dizem que recompensas da família são desbloqueadas por **estrelas**. Três modelos incompatíveis para a mesma mecânica.

6. **O conceito central do produto tem três nomes e duas semânticas.** Reino (`FOUNDATION.md`, `Screen Map.md`, `docs/worlds/piano/World Design.md`), Mundo (`Glossary.md`, `Game Domain Model.md`) e Jornada (`World Model.md`, `Progression Model.md`) são usados para a mesma coisa — sendo que `Game Domain Model.md` define Jornada como "toda a evolução da criança" (superconjunto dos Mundos) enquanto `World Model.md` define "Jornada (World)" como um único universo temático. Idem para Região vs Capítulo vs Etapa vs Área (4 nomes para a subdivisão do mundo Piano, em `FOUNDATION.md`, `Chapters.md`, `Learning Path.md` e `GDD.md`).

7. **Três documentos concorrem pela direção visual, com conflitos diretos.** `docs/Art_Bible.md` (fonte oficial segundo o `CLAUDE.md`) declara paleta e estilo "aguardando definição". Mas `docs/game-design/Art Direction.md` se declara "direção artística oficial" e `docs/UI/Design System.md` já define paleta, tipografia e ícones. Conflitos concretos: ícones "**preenchidos**" (Art Direction) vs "**outline** arredondado" (Design System); "PNG é o formato padrão" (Art Direction) vs "SVG para elementos de interface" (`CLAUDE.md`/`Art_Bible.md`). Violação direta da regra de Single Source of Truth.

8. **A hierarquia de documentos do `CLAUDE.md` referencia arquivos que não existem com aqueles nomes.** `Product_Manifesto.md`, `Project_Charter.md`, `Product_Vision.md`, `Product_Principles.md`, `GDD.md` (na raiz), `Glossary.md` (sem caminho) — nenhum existe nesses nomes/caminhos; os reais são `docs/product/Manifesto.md`, `docs/product/Charter.md`, etc. A hierarquia também ignora ~40 documentos reais (domain, systems, UI, worlds, experience), deixando a resolução de conflitos indefinida justamente onde os conflitos estão. `Decision_Log.md` e `Playtest_Log.md` estão vazios; `docs/systems/Character.md` e `docs/systems/House.md` são templates sem conteúdo — a **Casa**, item do MVP, não tem especificação de sistema.

9. **Cada documento define seu próprio "MVP", e a soma é 4–5x o escopo congelado.** Sessões, Loja da Família, Pedidos de Resgate, Dashboard, Inbox, Modo Confiança, Relatórios, Timeline com fotos, Storybook, Diário, Splash, Login social, Perfil, cronômetro de prática, capítulos, objetivos, árvore visual — tudo isso está marcado como "MVP" em algum documento (`Progression Model.md`, `Economy.md`, `Parent Companion.md`, `Storybook.md`, `Timeline.md`, `Screen Map.md`, `User Flow.md`, `GDD/Overview.md`, `Goals.md`, `Tree of Growth.md`). O escopo real do MVP é indeterminável a partir da documentação.

10. **Riscos técnicos estruturais na stack declarada.** Fotos no MVP da Timeline/Storybook são inviáveis em LocalStorage (~5MB, sem blobs); login Google/Apple (`User Flow.md`) exige backend que o `Charter.md` proíbe; a arquitetura orientada a eventos (`Product Architecture.md`) convive com o requisito "arquivo único no MVP" (`GDD.md`); e decisões atuais (estado "Hover (Web)" no Design System, animações CSS, SVG de interface, DOM monolítico) garantem retrabalho pesado numa futura migração React Native/Expo.

---

# Parte 1 — Análise por Perspectiva

## 1. Product Architect

### 1.1 Dois produtos, uma documentação

A documentação descreve duas visões de produto incompatíveis convivendo sem reconciliação:

- **Produto "congelado"** — `CLAUDE.md` (MVP: Casa, Mundo Piano, Missões, XP, Estrelas, Loja, Álbum, Eventos, Painel dos Pais, Save), `docs/product/Charter.md`, `docs/game-design/GDD/GDD.md`, `CURRENT_STATE.md` e o `index.html` já implementado (5 abas: Casa, Missões, Álbum, Loja, Calendário).
- **Produto "novo"** — `FOUNDATION.md` (Casa → Jardim → Reinos → Regiões → Missões → Conclusão → Storybook), `docs/domain/*`, `docs/UI/screens/*`, `docs/mvp/User Flow.md`, `docs/experience/*`.

O produto novo introduz Jardim, Árvores, Reinos, Regiões, Capítulos, Sessões, Storybook, Timeline, Diário — nenhum deles está na lista congelada de 10 itens do `CLAUDE.md`. E o produto novo **remove** do MVP itens congelados: `Screen Map.md` lista Loja, Coleções, Calendário, Eventos e Notificações como "Funcionalidades Futuras". Não há nenhum registro em `docs/Decision_Log.md` (vazio) autorizando essa pivotagem.

### 1.2 Autoridade documental duplicada

- `FOUNDATION.md` se autodeclara "o documento mais importante do projeto"; `CLAUDE.md` diz que `Product_Principles.md` é "o documento mais importante para decisões diárias". Dois topos de hierarquia.
- `FOUNDATION.md` replica regras de economia e recompensas (estrelas, moedas, recompensas de missão) que pertencem a `Economy.md`/`Reward System.md` — violando a regra de SSOT do próprio `CLAUDE.md` ("nunca replique regras entre documentos"). E replica com divergência: omite XP.

### 1.3 Escopo demais para um MVP

O objetivo declarado é validar **uma** hipótese (motivação para piano diário). Para isso, a documentação especifica: 7 tipos de missão, 4 modos de validação, 2 lojas/catálogos, 6 níveis de raridade, sistema de eventos com calendário e contagem regressiva, Timeline com fotos, Storybook multi-fonte, Diário compartilhado, Dashboard/Inbox/Relatórios parentais, motor de recompensas configurável por regras (Trigger → Condição → Reward Rule → Reward → Item). `docs/development/MVP Design Principles.md` prega o oposto ("construir pequeno, validar cedo") — e é ignorado pelos próprios documentos vizinhos.

### 1.4 Detalhes divergentes

- **Público-alvo:** 7–10 anos (`Manifesto.md`, `Charter.md`) vs "aproximadamente 6 e 12 anos" (`GDD/Overview.md`).
- **Papéis:** `Charter.md` atribui "arquitetura do produto" ao ChatGPT e "arquitetura técnica" ao Claude Code; `CLAUDE.md` atribui "arquitetura" ao Claude sem qualificação. `Charter.md` atribui arte ao Gemini, mas `Art_Bible.md` segue "aguardando definição".
- `GDD/Overview.md` recomenda leitura de "Core Journey Loop" — documento que foi **deletado** do repositório (o existente é `docs/game-design/Core Gameplay Loop.md`).

## 2. Software Architect

### 2.1 Arquitetura descrita vs stack declarada

`docs/product/Product Architecture.md` descreve uma plataforma modular orientada a eventos com 6 camadas, barramento de eventos de domínio, Analytics, Timeline e princípio "Configuração > Código". Isso não é impossível em JavaScript puro, mas colide com:

- `docs/game-design/GDD/GDD.md`: "Arquivo único no MVP" (que por sua vez colide com `CLAUDE.md`: "modularize o código").
- A realidade: `index.html` monolítico de ~48KB na raiz.
- O próprio documento admite que Persistência, Eventos de Domínio, Fluxo de Dados e Estados da Aplicação estão "no backlog" — ou seja, exatamente as partes necessárias para implementar o MVP não estão especificadas.

### 2.2 Dependências circulares e acoplamentos

O texto afirma comunicação por eventos, mas as dependências conceituais formam ciclos que nenhum documento resolve:

- **Missões → Recompensas → Desbloqueios → Missões**: `Mission System.md` "integra com Progression"; `Goals.md` diz que conclusão de objetivos desbloqueia conteúdo "definido pelo Progression Model"; desbloqueios liberam novas missões. Ciclo Missão/Objetivo/Progression/Missão.
- **Reward System ↔ Economy**: `Reward System.md` entrega Coins/Stars (escreve na Economy), mas suas Condições incluem "quantidade mínima de estrelas" (lê a Economy). `Economy.md` delega as regras de concessão ao Reward System. Dependência bidirecional.
- **Parent Companion ↔ Mission/Reward**: pais criam e validam missões; a validação dispara recompensas; recompensas notificam a Inbox dos pais.
- **Violação da própria camada Worlds**: a Arquitetura afirma "os mundos nunca implementam regras de economia ou progressão", mas o `GDD.md` (documento do mundo Piano) define regras econômicas centrais: "cada estrela gera moedas", "60 minutos = 1 estrela".

### 2.3 Sistema fantasma e colisão de termos

- A Arquitetura lista **Progression** como um System, mas não existe `docs/systems/Progression.md`. Existe `docs/domain/Progression Model.md`, que mistura modelo de domínio com regras de sistema (lojas, catálogos, MVP). A fronteira domínio × sistema está indefinida.
- **"Evento" significa duas coisas**: evento de domínio/mensageria (`Product Architecture.md`, `Reward System.md`: "publica um evento") e evento do mundo real/recital (`Events.md`, `Glossary.md`). Mesmo termo, dois conceitos técnicos — em um codebase isso é fonte direta de bugs e o Glossário não desambigua.

### 2.4 Persistência subespecificada e contraditória

- `Timeline.md` (MVP: "fotos") e `Storybook.md` (MVP: "Fotos") são incompatíveis com LocalStorage (limite ~5MB, sem armazenamento binário viável).
- `User Flow.md` coloca "login Google; login Apple; modo família" no MVP — exige OAuth/backend, proibidos pelo `Charter.md` ("Fora do Escopo: Login, Nuvem, Sincronização").
- Nenhum documento define o esquema do save, versionamento do estado ou estratégia de migração — apesar de `CLAUDE.md` exigir "código preparado para futura migração para persistência online".

## 3. Game Designer

### 3.1 A economia tem três versões

| Regra | Versão A | Versão B | Versão C |
|---|---|---|---|
| O que a loja consome | Estrelas (`Glossary.md`) | Moedas (`GDD.md`, `Economy.md`, todos os demais) | — |
| Origem das moedas | "Cada estrela gera moedas" (`GDD.md`, slice) | Reward Rules concedem Coins diretamente (`Reward System.md`) | Não definida (`Economy.md`) |
| Recompensa da família | Desbloqueada por estrelas (`FOUNDATION.md`, `Progression Model.md` "liberar recompensas da família") | Comprada com moedas (`Economy.md` Catálogo da Família, `Parent Companion.md` "custo em moedas") | Proibida: "moedas compram apenas cosmético" (`Principles.md`, `GDD.md`, `CURRENT_STATE.md`) |

Não há como implementar a Loja sem escolher arbitrariamente uma das versões — exatamente o que o `CLAUDE.md` proíbe o implementador de fazer.

### 3.2 Progressão: conceitos com significados conflitantes

- **Objetivo**: subcondição de missão (`Glossary.md`, `Game Domain Model.md`) vs meta composta por missões (`Goals.md`, `Progression Model.md`, `World Model.md`, `Goal Card.md`). Inversão total.
- **Sessão**: marcada "🟡 Proposto / Em avaliação" no `Game Domain Model.md`, mas tratada como pilar consolidado (e incluída no MVP) em `Progression Model.md`, `World Model.md`, `Goals.md`, `Content Design.md` e `GDD/Gameplay.md`. Além disso, a posição hierárquica da Sessão inverte entre documentos (contém missões vs é exigida por missões — ver Sumário, item 3).
- **Medalha**: domínio técnico de uma habilidade ("Escalas Ouro" — `Progression Model.md`) vs marco de constância temporal ("100 dias praticando" — `Collections.md`).
- **Troféu**: "maior reconhecimento de um mundo, representa domínio" (`Glossary.md`, `Game Domain Model.md`) vs "não encerram uma jornada; celebram momentos únicos" (`Progression Model.md`).
- **Adesivo**: "as conquistas são adesivos" (`GDD.md`) vs "adesivos representam memórias, não representam progresso" (`Progression Model.md`).
- **Raridade**: Bronze/Prata/Ouro/Brilhante/Arco-íris (`GDD.md`, `Art_Bible.md`) vs Comum/Incomum/Raro/Épico/Lendário/Especial + "Versões Brilhantes" (`Collections.md`). Dois sistemas de graduação sem mapeamento.

### 3.3 XP: o recurso órfão

Ver Sumário, item 4. O `Progression Model.md` v1.1 declara: "se dois elementos responderem à mesma pergunta, um deles provavelmente deve ser removido" — e de fato removeu XP/Nível do modelo. Mas nenhum outro documento foi atualizado: `CLAUDE.md`, `Charter.md`, `GDD.md`, `Glossary.md`, `Game Domain Model.md`, `UX_Bible.md` ("XP sempre visível") e `Core Gameplay Loop.md` continuam exigindo XP. Este é o sintoma mais claro de deriva de conversa longa com IA: uma decisão tomada num documento novo sem propagação.

### 3.4 Contradições com princípios congelados

- `Reward System.md` inclui trigger de **"Login diário"** — recompensa por abrir o aplicativo, contradizendo `Manifesto.md` ("o objetivo é que a criança passe menos tempo olhando para a tela"), `GDD/Gameplay.md` ("nenhuma mecânica deve incentivar permanecer conectado") e `Core Gameplay Loop.md`.
- `Reward System.md` (backlog) lista "probabilidades; recompensas aleatórias; tabelas de loot" — contradizendo o princípio congelado "não há aleatoriedade nas conquistas" (`Principles.md`, `CURRENT_STATE.md`). Mesmo como backlog, é uma direção proibida documentada como evolução natural.
- "Baús"/"Chest" aparecem em `Progression Model.md`, `Economy.md` e `Reward System.md` sem definição em nenhum documento de domínio — e "abrir baús" evoca loot aleatório, tensionando o mesmo princípio.

### 3.5 Conteúdo do Mundo Piano triplicado

Três estruturas paralelas sem mapeamento entre si:

- `GDD.md`: 10 **áreas** (Técnica, Escalas, Acordes, Cifras, Partitura, Ritmo, Repertório, Eventos, Desafios, Mestres).
- `docs/worlds/piano/Chapters.md`: 7 **capítulos/regiões** (Bosque das Primeiras Notas … Palco da Gratidão).
- `docs/worlds/piano/Learning Path.md`: 12 **etapas** (MVP = só as 4 primeiras).

Inconsistência interna adicional: `Learning Path.md` exemplifica "Etapa Primeiras Notas → **Capítulo 3 — Descobrindo as Notas**", mas o Capítulo 3 real em `Chapters.md` é "Colinas do Ritmo"; não existe capítulo "Descobrindo as Notas".

### 3.6 Balanceamento disperso

Valores numéricos espalhados e incompatíveis, sem tabela única: missão diária de 60 min (`GDD.md`) vs exemplos de 10/20/30 min (`Content Design.md`, `Mission Card.md`, `User Flow.md`, `Mission System.md`); recompensas de +5, +10, +15, +20, +50, +100 moedas conforme o documento (`User Flow.md`, `Mission Complete Screen.md`, `Mission Card.md`, `Reward Card.md`, `Reward System.md`, `Economy.md`).

### 3.7 Streak/Calendário

`GDD.md` põe "Calendário e streak" no MVP; `UX_Bible.md` exige streak sempre visível; `Reward System.md` usa "sequência de dias" como trigger; `Screen Map.md` declara Calendário como funcionalidade **futura**; `Progression Model.md` ignora o conceito. "Streak" não está no Glossário.

## 4. UX Designer

### 4.1 O mapa de telas contradiz o MVP

`Screen Map.md` (MVP: Splash, Login, Casa, Jardim, Reino, Região, Missão, Conclusão, Storybook, Perfil, Configurações):

- **Exclui do MVP**: Loja, Álbum/Coleções, Calendário, Eventos — todos itens congelados do `CLAUDE.md`/`Charter.md`.
- **Inclui no MVP**: Login (proibido pelo `Charter.md`), Splash, Perfil, Storybook (fora da lista congelada).
- **Omite completamente o Painel dos Pais** — item do MVP, com PIN exigido pela `UX_Bible.md` e implementado no slice. Não há tela para ele em nenhum documento de UI.

### 4.2 Três "Casas" diferentes

- `GDD.md`: quarto, personagem, piano, estante de **troféus**, acesso à **loja** e ao **álbum**.
- `docs/UI/screens/House Screen.md`: avatar, **Jardim**, Caixa de Correio, Estante da Jornada (= Storybook), configurações — sem piano, sem loja, sem álbum, sem troféus.
- `index.html` (slice, via `CURRENT_STATE.md`): aba "Casa" num layout de 5 abas.

### 4.3 Navegação incompatível com os próprios princípios

O fluxo novo tem 5 níveis de profundidade (Casa → Jardim → Reino → Região → Missão), enquanto `Screen Map.md` exige "qualquer funcionalidade principal em no máximo três interações" — iniciar a missão do dia leva 4+ toques. O slice implementado usa navegação plana por abas, sem Jardim/Reino/Região. Nenhum documento reconcilia os dois padrões.

### 4.4 Componentes redundantes/sobrepostos

- **Journey Card vs Progress Card**: ambos exibem árvore + estrelas + estado + progresso de uma Jornada (`docs/UI/components/Journey Card.md`, `Progress Card.md`); o Progress Card diz servir para "Jornada, Reino, Região ou Objetivo" — englobando o caso de uso do Journey Card. Não há critério de escolha entre eles.
- **Story Card vs Message Card**: "mensagem da família" é um tipo previsto nos **dois** componentes, e ambos declaram reutilização em Storybook e Timeline (`Story Card.md`, `Message Card.md`).
- **Goal Card vs Progress Card**: progresso de Objetivo é coberto por ambos.
- Observação: ao contrário do suspeitado, `Goal Card.md` e `Mission Card.md` **não** estão vazios — têm especificação completa. Os documentos realmente vazios são `docs/systems/Character.md` e `docs/systems/House.md`.

### 4.5 Fluxo de validação incoerente

`Core Gameplay Loop.md` põe "Pais validam as missões" como etapa fixa do loop diário. `GDD/Gameplay.md`, `Mission Screen.md`, `Mission System.md` e `Parent Companion.md` tornam a validação configurável (automática, obrigatória, opcional, modo confiança). O slice implementado valida automaticamente. A interação mais central do produto tem três comportamentos documentados.

### 4.6 HUD de progresso sem lugar

`UX_Bible.md` exige estrelas, XP, streak e repertório "sempre visíveis/acessíveis". Nenhuma tela de `docs/UI/screens/` reserva lugar para esse HUD (a House Screen não exibe nem estrelas), e o Design System não define o componente.

### 4.7 Cronômetro: dentro ou fora do app?

`GDD/Overview.md` e `GDD/Gameplay.md` colocam "cronômetro de prática" no MVP; `Mission Screen.md` o torna opcional; `Core Gameplay Loop.md` manda a criança "fechar o aplicativo" e diz que "no MVP nenhuma prática acontece dentro do jogo". A decisão sobre o app ficar aberto durante a prática — estruturante para o design — está em aberto com três respostas.

## 5. Tech Lead

### 5.1 A documentação não serve como especificação sem ambiguidade

Para implementar hoje seria preciso decidir arbitrariamente: qual economia (3 versões), qual hierarquia de domínio (2 versões), qual navegação (2 versões), qual escopo de MVP (cada documento tem o seu), quais valores de balanceamento (dispersos e conflitantes). O `CLAUDE.md` proíbe o implementador de decidir gameplay/economia — mas a documentação obriga a decidir, porque não converge. Adicionalmente: nenhum documento define contrato de dados (esquema do save em LocalStorage, formato de eventos de domínio, estrutura das entidades), e os documentos de sistema mais críticos para o MVP congelado (`Character.md`, `House.md`) estão vazios.

### 5.2 Riscos concretos para a migração React Native/Expo

- `docs/UI/Design System.md` exige estado "Hover (Web)" em todo componente — inexistente em touch/RN.
- `CLAUDE.md` e `Art_Bible.md` mandam "SVG para interface" e "animações CSS" — RN não tem CSS nem SVG nativos (exigem `react-native-svg`, Reanimated etc.); todo asset e animação seguindo essas regras precisará ser refeito ou adaptado.
- "Arquivo único no MVP" (`GDD.md`) + `index.html` monolítico com lógica, estado e apresentação juntos: sem separação lógica/renderização documentada, a migração é uma reescrita, não um porte.
- LocalStorage citado nominalmente como decisão congelada (`CURRENT_STATE.md`) sem exigência de camada de abstração de persistência — se o código chamar `localStorage` diretamente, a troca por AsyncStorage/nuvem tocará todo o codebase. A Arquitetura deixa "Persistência" e "Sincronização Offline" para o futuro.
- Login social e mídia (fotos/vídeos/áudio na Timeline/Storybook) pressupõem backend e armazenamento de arquivos que nada na stack atual suporta.

### 5.3 Risco existencial da persistência local

A proposta de valor central do produto novo é "memória para a vida" (`Storybook.md`, `Timeline.md`: anos de registros). LocalStorage é apagável por limpeza de cache/navegador e preso a um dispositivo. A documentação promete permanência ("nunca é perdido", "permanece para sempre") que a decisão técnica congelada não pode cumprir — e nenhum documento reconhece esse gap.

---

# Parte 2 — Achados Consolidados (10 categorias)

## Categoria 1 — Inconsistências entre documentos

1. **Estrela gasta na loja vs nunca gasta.** `docs/domain/Glossary.md` vs `docs/systems/Economy.md`, `docs/domain/Progression Model.md`, `docs/domain/Game Domain Model.md`, `FOUNDATION.md`, `docs/product/Principles.md`. Problema: o documento de maior autoridade de vocabulário descreve a mecânica econômica oposta à do resto do projeto.
2. **Objetivo ⊂ Missão vs Missão ⊂ Objetivo.** `Glossary.md`/`Game Domain Model.md` vs `Goals.md`/`Progression Model.md`/`World Model.md`/`docs/UI/components/Goal Card.md`. Problema: a relação entre as duas entidades mais centrais do domínio é indeterminável.
3. **Sessão contém Missões vs Missão exige Sessões.** `Progression Model.md` vs `World Model.md`/`Mission System.md`. Problema: modelagem de dados impossível sem decisão arbitrária.
4. **XP no MVP vs XP inexistente nos sistemas.** `CLAUDE.md`/`Charter.md`/`GDD.md`/`Glossary.md` vs `Progression Model.md`/`Economy.md`/`Reward System.md`/`FOUNDATION.md`. Problema: item do escopo congelado não é implementável pelos documentos de sistema.
5. **Loja/Álbum/Eventos/Calendário no MVP vs "futuros".** `CLAUDE.md`/`Charter.md`/`GDD.md` vs `docs/UI/screens/Screen Map.md`. Problema: contradição direta sobre o escopo congelado.
6. **Login proibido vs Login no MVP.** `Charter.md` ("Fora do Escopo") vs `Screen Map.md` e `docs/mvp/User Flow.md` ("login Google; login Apple"). Problema: viola o escopo e a stack (sem backend).
7. **Validação parental obrigatória vs configurável.** `Core Gameplay Loop.md` vs `GDD/Gameplay.md`/`Mission Screen.md`/`Parent Companion.md`. Problema: o loop central tem dois desenhos.
8. **Casa do GDD vs Casa da House Screen.** `GDD.md` (piano, troféus, loja, álbum) vs `House Screen.md` (Jardim, correio, Storybook). Problema: a tela inicial tem duas especificações incompatíveis.
9. **Público 7–10 vs 6–12.** `Manifesto.md`/`Charter.md` vs `GDD/Overview.md`. Problema: calibragem de conteúdo/linguagem sem alvo único.
10. **Capítulo 3 = "Descobrindo as Notas" vs "Colinas do Ritmo".** `Learning Path.md` vs `Chapters.md`. Problema: os dois documentos do mesmo mundo não batem entre si.
11. **Hierarquia do `CLAUDE.md` vs arquivos reais.** Nomes `Product_*.md`/`Project_Charter.md`/`GDD.md` não existem; reais em `docs/product/*`, `docs/game-design/GDD/`. Problema: a regra "consulte o documento X" aponta para arquivos inexistentes. `README.md` e `CURRENT_STATE.md` (links para `docs/Product_Principles.md`, `docs/Project_Charter.md`, "docs/00 a docs/07") repetem caminhos fantasmas.
12. **Referências cruzadas quebradas.** `docs/Roadmap.md` → `GDD.md` (caminho errado); `GDD.md` → `Backlog.md` e `../CLAUDE.md` (relativos errados a partir de `docs/game-design/GDD/`); `GDD/Overview.md` → "Core Journey Loop" (arquivo deletado); `GDD/Gameplay.md` → "Progression", "Piano World", "UI Flow" (nomes inexistentes). Problema: a malha de navegação documental está podre.

## Categoria 2 — Conceitos duplicados

1. **Duas árvores.** "Árvore de Habilidades" (`Glossary.md`, `Game Domain Model.md`, `GDD.md` — 10 áreas técnicas) e "Árvore do Crescimento/da Música/da Jornada" (`docs/domain/Tree of Growth.md`, `World Design.md`, `Journey Card.md` — símbolo emocional com estados Broto→Madura). Nenhum documento diz se são o mesmo conceito. Envolvidos: 6+ arquivos.
2. **Quatro sistemas de memória.** Álbum de Adesivos (`Collections.md`), Storybook (`docs/experience/Storybook.md`), Timeline (`docs/experience/Timeline.md`, também em `Parent Companion.md` e `Game Domain Model.md`) e Diário (`Parent Companion.md`, `Game Domain Model.md`). Sobreposição massiva de propósito ("preservar memórias/conquistas") com fronteiras definidas apenas parcialmente (`Timeline.md` distingue Timeline×Diário, mas ninguém delimita Storybook×Timeline×Álbum).
3. **Dois documentos de GDD com escopos de MVP diferentes.** `docs/game-design/GDD/GDD.md` (inclui álbum, calendário/streak, missões semanais) e `docs/game-design/GDD/Overview.md` (inclui cronômetro e Parent Companion, omite álbum e save).
4. **Três documentos de direção visual.** `docs/Art_Bible.md`, `docs/game-design/Art Direction.md`, `docs/UI/Design System.md` — todos definem (ou reivindicam definir) estilo, paleta e ícones.
5. **Glossary vs Game Domain Model.** Ambos definem as mesmas ~20 entidades com textos ligeiramente divergentes (ex.: Estrela, Troféu, Objetivo) — a duplicação é exatamente o que gerou as contradições da Categoria 1.
6. **Loop/fluxo principal descrito 5 vezes.** `Core Gameplay Loop.md`, `GDD/Gameplay.md` ("Estrutura Geral da Experiência"), `User Flow.md`, `Screen Map.md`, `Storybook.md` ("Fluxo da Experiência") — com variações entre si.

## Categoria 3 — Conceitos conflitantes

1. **Medalha**: domínio de habilidade (`Progression Model.md`) vs marco de constância (`Collections.md`).
2. **Troféu**: domínio/conclusão de um mundo (`Glossary.md`, `Game Domain Model.md`) vs momento único que não encerra nada (`Progression Model.md`).
3. **Adesivo**: conquista (`GDD.md`, `Glossary.md`) vs memória que "não representa progresso" (`Progression Model.md`).
4. **Jornada**: totalidade da experiência da criança (`Game Domain Model.md`: "todos os mundos fazem parte da mesma jornada") vs sinônimo de um mundo (`World Model.md`: "Jornada (World)"; `Progression Model.md`: "Piano é uma Jornada").
5. **Recompensa da família**: destravada por estrelas vs comprada com moedas vs proibida (ver Sumário, item 5). Arquivos: `FOUNDATION.md`, `Progression Model.md`, `Economy.md`, `Parent Companion.md`, `Principles.md`, `GDD.md`, `CURRENT_STATE.md`.
6. **Ícones**: preenchidos (`Art Direction.md`) vs outline (`Design System.md`); **formato padrão**: PNG (`Art Direction.md`) vs SVG para interface (`CLAUDE.md`, `Art_Bible.md`).
7. **Sessão**: conceito "em avaliação" (`Game Domain Model.md`) vs pilar do MVP (`Progression Model.md`).
8. **Recompensa por login diário** (`Reward System.md`) vs "nenhuma mecânica deve incentivar permanecer conectado" (`GDD/Gameplay.md`, `Manifesto.md`, `Core Gameplay Loop.md`).
9. **Aleatoriedade**: proibida como princípio congelado (`Principles.md`) vs planejada no backlog do `Reward System.md` (loot tables, recompensas aleatórias) e sugerida por "baús".

## Categoria 4 — Dependências circulares

1. **Missão → Recompensa → Progression → desbloqueio → Missão.** `Mission System.md`, `Reward System.md`, `Goals.md`, `Progression Model.md`. Problema: sem um contrato de eventos definido (está no backlog de `Product Architecture.md`), o ciclo vira acoplamento direto na implementação.
2. **Reward System ↔ Economy.** `Reward System.md` escreve moedas/estrelas e lê "quantidade mínima de estrelas" como condição; `Economy.md` delega regras ao Reward System. Dependência de leitura+escrita bidirecional.
3. **Parent Companion ↔ Mission System ↔ Reward System.** Pais criam/validam missões; validação dispara recompensas; recompensas notificam os pais. Três sistemas em anel.
4. **GDD (World) definindo Economy.** A camada Worlds "nunca implementa regras de economia" (`Product Architecture.md`), mas `GDD.md` define conversão estrela→moeda. A dependência invertida quebra a direção das camadas.
5. **Objetivo ↔ Missão ↔ Sessão.** Com as hierarquias invertidas entre documentos (Categorias 1.2 e 1.3), qualquer implementação fiel a dois documentos simultaneamente cria referência circular no modelo de dados.

## Categoria 5 — Documentos redundantes

1. `docs/systems/Character.md` e `docs/systems/House.md` — templates 100% vazios (só headings). A Casa é item do MVP congelado; um esqueleto vazio dá falsa impressão de cobertura.
2. `docs/Decision_Log.md` e `docs/Playtest_Log.md` — "A ser preenchido", embora o `CLAUDE.md` mande consultá-los como passo obrigatório do fluxo.
3. `docs/domain/Glossary.md` × `docs/domain/Game Domain Model.md` — ~80% de sobreposição (ver Cat. 2.5).
4. `docs/Art_Bible.md` × `docs/game-design/Art Direction.md` — o primeiro diz "aguardando definição" do que o segundo já "define oficialmente".
5. `docs/UI/components/Journey Card.md` × `Progress Card.md`; `Story Card.md` × `Message Card.md` — pares com casos de uso sobrepostos (ver 4.4).
6. `docs/game-design/GDD/GDD.md` × `GDD/Overview.md` — dois sumários de game design do mesmo MVP com listas diferentes.
7. Nota factual: `docs/UI/components/Goal Card.md` e `Mission Card.md` **não** estão vazios (suspeita não confirmada) — o problema deles é sobreposição, não ausência de conteúdo.

## Categoria 6 — Problemas de nomenclatura

1. **Reino / Mundo / Jornada** — três nomes para a unidade temática (`FOUNDATION.md`, `Glossary.md`, `World Model.md`, `World Design.md`, `Screen Map.md`). "Reino" e "Jardim" **não existem no Glossário**, apesar de serem a espinha da navegação nova.
2. **Região / Capítulo / Etapa / Área** — quatro nomes para a subdivisão (`FOUNDATION.md`, `Chapters.md`, `Learning Path.md`, `GDD.md`). Nenhum está no Glossário.
3. **Moeda ausente do Glossário** — o recurso econômico gastável do MVP não tem entrada na "única fonte oficial de nomenclatura".
4. **Painel dos Pais vs Parent Companion** — `Glossary.md` define só "Painel dos Pais"; toda a camada de sistemas usa "Parent Companion" (não glossariado).
5. **Álbum vs Pasta de Adesivos** — `Progression Model.md` chama o Álbum de "Pasta de Adesivos".
6. **Loja vs Loja do Jogo vs Catálogo Journey World; Loja da Família vs Catálogo da Família** — `Glossary.md`, `Progression Model.md`, `Economy.md`.
7. **Personagem vs Avatar** — `Glossary.md` afirma que o Personagem "não é um avatar genérico", mas `World Model.md` ("Relação com o Avatar"), `House Screen.md` e `User Flow.md` usam "Avatar".
8. **Termos usados sem existir no Glossário** (violação direta da regra de Domain Vocabulary do `CLAUDE.md`, que exige interromper e propor o termo): Jardim, Reino, Região, Capítulo, Sessão, Moeda, Storybook, Timeline, Diário, Streak, Baú/Chest, Vitrine, Inbox, Dashboard, Pedido de Resgate, Modo Confiança, Caixa de Correio, Estante da Jornada.
9. **Mundos futuros com nomes flutuantes**: Ginástica Rítmica/Ginástica/Movimento/Reino do Movimento; Escola/Conhecimento/Sabedoria; Fé/Vida Espiritual/Jornada Espiritual/Virtudes (`Manifesto.md`, `Vision.md`, `Backlog.md`, `FOUNDATION.md`, `World Design.md`, `Tree of Growth.md`, `Progression Model.md`).
10. **"Evento" ambíguo** — evento de domínio (mensageria) e evento real (recital) compartilham o mesmo termo sem desambiguação (`Product Architecture.md`, `Reward System.md` vs `Events.md`).

## Categoria 7 — Violações do MVP (definido no CLAUDE.md)

1. `Screen Map.md`/`User Flow.md`: adicionam Splash, **Login social**, Perfil, Configurações, Storybook; removem Loja, Álbum, Eventos, Calendário; omitem o Painel dos Pais.
2. `Progression Model.md` (MVP): Sessões, Objetivos, **Loja da Família** — nenhum na lista congelada.
3. `Economy.md` (MVP): Catálogo da Família, Pedidos de Resgate, aprovação, estatísticas — economia "complexa" que o `Charter.md` exclui.
4. `Parent Companion.md` (MVP): Dashboard, Inbox, Modo Confiança, CRUD de recompensas, Relatórios — o item congelado é um "Painel dos Pais" simples com PIN.
5. `Storybook.md`/`Timeline.md` (MVP): Timeline, Diário, **Fotos** — Storybook nem consta na lista congelada; fotos são tecnicamente inviáveis na stack.
6. `Tree of Growth.md` (MVP): árvore visual com estágios — não consta na lista congelada.
7. `Goals.md` (MVP): sistema completo de objetivos com categorias e estados — não consta na lista.
8. `GDD/Overview.md` (MVP): cronômetro de prática — não consta na lista e conflita com o loop "fechar o app".
9. `Events.md` (MVP): criação de eventos, calendário, contagem regressiva — enquanto `Screen Map.md` declara Eventos/Calendário futuros. (Eventos estão na lista congelada, mas com dois escopos incompatíveis.)
10. Consequência agregada: somando as seções "MVP" de todos os documentos, o escopo real é várias vezes maior que os 10 itens congelados — o oposto do que `MVP Design Principles.md` e `CLAUDE.md` pregam.

## Categoria 8 — Riscos de escalabilidade

1. **Permanência prometida vs LocalStorage volátil.** `Storybook.md`/`Timeline.md`/`Progression Model.md` prometem registros "para sempre"; LocalStorage é apagável e preso a um dispositivo (`CLAUDE.md`, `CURRENT_STATE.md`). Risco existencial para a proposta "memória para a vida".
2. **Sem esquema/versionamento de save.** Nenhum documento define o formato do estado persistido nem migrações — cada mudança de estrutura pode corromper saves de crianças reais em uso (`Product Architecture.md` deixa "Persistência" no backlog).
3. **Moedas globais entre jornadas vs estrelas por jornada** (`Economy.md`): sem regras de balanceamento inter-mundos, a adição do segundo mundo inflaciona a economia do primeiro.
4. **Multi-perfil/irmãos ignorado.** O backlog cita irmãos (`Collections.md`, `Timeline.md`), mas nada no modelo de dados/identidade prevê múltiplas crianças por dispositivo/família.
5. **Arquitetura aspiracional sem incrementos definidos.** `Product Architecture.md` promete suportar multiplayer, IA e sincronização "sem alterar conceitos centrais", mas os blocos que permitiriam isso (eventos de domínio, camada de persistência) não estão especificados — o gap entre o documento e o `index.html` monolítico é o maior risco de "reescrever tudo" na Fase 3 do `Roadmap.md`.

## Categoria 9 — Riscos para React Native/Expo

1. **Estado "Hover (Web)" obrigatório em todo componente** (`docs/UI/Design System.md`) — inexistente em touch; a spec de componentes precisará ser revista.
2. **"SVG para interface" + "animações CSS"** (`CLAUDE.md`, `docs/Art_Bible.md`) — RN não tem CSS nem SVG nativos; todos os assets/animações que seguirem essas regras exigirão retrabalho (react-native-svg, Reanimated) ou substituição.
3. **"Arquivo único no MVP"** (`GDD.md`) e o `index.html` monolítico — lógica, estado e DOM entrelaçados tornam a migração uma reescrita; nenhum documento exige separação lógica/apresentação.
4. **LocalStorage sem camada de abstração documentada** (`CURRENT_STATE.md` congela "LocalStorage" nominalmente) — chamadas diretas espalhadas custarão caro na troca para AsyncStorage/nuvem.
5. **Login Google/Apple e mídia (fotos/vídeo/áudio)** (`User Flow.md`, `Timeline.md`, `Storybook.md`) — pressupõem backend, OAuth e storage de arquivos; nada disso tem caminho na stack atual nem na futura sem uma decisão de plataforma que os documentos não registram.
6. **Orientação de tela indefinida** — `Design System.md` prioriza retrato ("paisagem futuro"), o slice do piano historicamente tendia a paisagem (`CURRENT_STATE.md`); em RN essa decisão afeta navegação e layout de todos os componentes.

## Categoria 10 — Oportunidades de simplificação

1. **Unificar Glossário + Game Domain Model** — a duplicação entre eles é a origem direta de várias contradições (Estrela, Troféu, Objetivo). Um único documento de domínio eliminaria a classe inteira de conflito.
2. **Escolher uma única hierarquia** (Objetivo⊃Missão ou Missão⊃Objetivo; posição da Sessão) e propagá-la — hoje, 7+ documentos precisam ser lidos juntos e ainda assim não respondem.
3. **Decidir o destino do XP** — ou reintegrá-lo ao `Progression Model.md`/`Reward System.md`, ou removê-lo do `CLAUDE.md`/`Charter.md`/`GDD.md`/`Glossary.md`/`UX_Bible.md`. Metade dos documentos carrega um conceito morto (ou vivo — impossível saber).
4. **Um único documento de escopo do MVP** — as seções "MVP" espalhadas por 15+ documentos deveriam referenciar (não redefinir) o escopo congelado, como a própria regra de SSOT do `CLAUDE.md` exige.
5. **Adiar Sessão, Catálogo da Família, Storybook/Timeline/Diário e Baús** — nenhum é necessário para validar a hipótese única do MVP ("a criança quer voltar amanhã?"), e todos carregam contradições não resolvidas. `MVP Design Principles.md` já oferece o critério para esse corte; falta aplicá-lo aos demais documentos.
6. **Consolidar a direção visual em um documento** (Art Bible ou Design System, não os três) e alinhar a regra SVG/PNG entre `CLAUDE.md`, `Art_Bible.md` e `Art Direction.md`.
7. **Reduzir o catálogo de cards** — Journey/Progress e Story/Message têm sobreposição suficiente para sugerir que 2 componentes fariam o trabalho de 4.
8. **Corrigir o `CLAUDE.md` para apontar para os arquivos reais** (nomes e caminhos) e incluir na hierarquia os documentos de domínio/sistemas/UI — sem isso, a regra de prioridade em conflitos não funciona exatamente onde é mais necessária.
9. **Preencher ou remover os esqueletos** (`Character.md`, `House.md`) e registrar em `Decision_Log.md` as decisões já tomadas de fato (economia de cosméticos, sem aleatoriedade, PIN 1234, estrutura de abas do slice) — hoje elas só existem implícitas em `CURRENT_STATE.md` e no código.
10. **Escolher entre o "produto A" e o "produto B"** (abas vs Jardim/Reinos) antes de qualquer implementação nova — manter os dois modelos vivos na documentação garante que qualquer implementação viole metade dos documentos.

---

# Apêndice — Divergências entre a estrutura esperada e a real

Durante a auditoria, a própria lista de arquivos fornecida como referência mostrou-se desatualizada em relação ao repositório:

- `docs/design/` não existe — o diretório real é `docs/game-design/` (o histórico do git mostra a pasta antiga `docs/design/` com um "Core Journey Loop.md" deletado).
- `docs/product/Architecture.md` não existe — o arquivo real é `docs/product/Product Architecture.md`.
- `docs/systems/Piano.md` e `docs/systems/Progression.md` **não existem** — apesar de "Progression" ser listado como System em `Product Architecture.md` e de o Piano ser o único mundo do MVP. A documentação do Piano vive em `docs/worlds/`, e a de progressão em `docs/domain/Progression Model.md`.
- `GDD.md` não está em `docs/` — está em `docs/game-design/GDD/GDD.md`, ao lado de `Overview.md` e `Gameplay.md`.
- `docs/UI/components/Goal Card.md` e `Mission Card.md` **não estão vazios** — possuem especificação completa. Os arquivos realmente vazios são `docs/systems/Character.md`, `docs/systems/House.md`, `docs/Decision_Log.md` e `docs/Playtest_Log.md`.

Essas divergências são, em si, um achado: a estrutura documental muda mais rápido do que os índices que a descrevem (`CLAUDE.md`, `README.md`, `FOUNDATION.md`, `CURRENT_STATE.md` — cada um descreve uma árvore de arquivos diferente, e nenhuma corresponde à real).
