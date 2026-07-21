# Journey World
## Project Charter

**Versão:** 2.0

**Status:** Ativo

**Autor:** Gabriel Chaves

---

# Visão Geral

Journey World é uma plataforma de gamificação infantil que transforma atividades reais em jornadas de evolução dentro de um universo digital.

O projeto foi concebido para incentivar disciplina, autonomia e prazer pelo aprendizado através de recompensas significativas, progresso visível e uma experiência acolhedora.

O primeiro reino desenvolvido será o **Reino do Piano**, utilizado como MVP para validar a hipótese central do produto.

---

# Objetivo do MVP

Construir uma experiência jogável que motive uma criança a praticar piano diariamente através da gamificação.

O MVP deve ser simples, funcional e suficientemente envolvente para validar a proposta antes da expansão para outros mundos.

---

# Hipótese Principal

> Uma criança que consegue visualizar seu progresso, receber reconhecimento pelas pequenas conquistas e acompanhar sua evolução dentro de uma jornada divertida terá maior motivação para manter uma rotina consistente de estudos.

Todo o desenvolvimento inicial existe para validar essa hipótese.

---

# Público-Alvo

## Primário

- Crianças entre 7 e 10 anos.

## Secundário

- Pais ou responsáveis que acompanham o desenvolvimento da criança.

---

# Problema

O estudo diário costuma ser percebido como uma obrigação.

Essa percepção reduz motivação, consistência e autonomia.

Journey World busca transformar esse processo em uma experiência que a criança deseje continuar espontaneamente.

---

# Escopo do MVP

O MVP será composto pelos seguintes sistemas:

- Casa (Hub Principal)
- Jardim (sinaliza reinos futuros bloqueados; só o Reino do Piano é jogável)
- Reino do Piano (Região → Missão → Conclusão → Storybook)
- Árvore do Crescimento
- Sistema de Missões
- Sistema de Estrelas
- Sistema de Moedas
- Loja
- Coleções (Álbum de Adesivos)
- Sistema de Eventos
- Painel dos Pais
- Salvamento Local (LocalStorage)

Qualquer funcionalidade fora desta lista deverá permanecer no backlog.

---

# Fora do Escopo

Nesta fase NÃO serão desenvolvidos:

- Multiplayer
- Splash
- Login
- Perfil
- Nuvem
- Sincronização entre dispositivos
- Economia complexa
- Marketplace
- Chat
- Ranking
- Loja com dinheiro real
- Sistema de amigos
- Reinos além do Piano jogáveis (aparecem sinalizados no Jardim como bloqueados/"em breve", sem conteúdo real)
- Inteligência Artificial dentro do jogo

---

# Critérios de Sucesso

O MVP será considerado validado quando:

- A criança compreender a interface sem necessidade de explicações constantes.
- Conseguir concluir missões de forma autônoma.
- Demonstrar satisfação ao receber recompensas.
- Solicitar espontaneamente utilizar o Journey World.
- Aumentar a frequência ou a qualidade dos estudos de piano ao longo das semanas.

---

# Princípios do Projeto

Todas as decisões deverão respeitar os seguintes princípios:

1. A vida real sempre vem antes do aplicativo.
2. O jogo recompensa ações reais.
3. Pequenas conquistas possuem grande valor.
4. Constância é mais importante que perfeição.
5. Simplicidade é prioridade.
6. A experiência da criança vale mais do que a tecnologia utilizada.
7. O MVP vale mais do que funcionalidades extras.

---

# Papéis

## Product Owner

Gabriel Chaves

Responsável por:

- visão do produto;
- priorização;
- validação;
- playtests;
- roadmap.

---

## ChatGPT

Responsável por:

- documentação;
- arquitetura do produto;
- game design;
- UX;
- organização;
- estratégia.

---

## Claude Code

Responsável por:

- implementação;
- arquitetura técnica;
- componentes;
- performance;
- manutenção.

---

## Gemini

Responsável por:

- direção de arte;
- identidade visual;
- assets;
- personagens;
- interface ilustrada;
- consistência artística.

---

# Tecnologias

MVP

- HTML
- CSS
- JavaScript
- LocalStorage

Tecnologias futuras serão avaliadas apenas após validação da hipótese principal.

---

# Estratégia de Desenvolvimento

O projeto seguirá ciclos curtos de desenvolvimento.

Cada ciclo possui:

1. Definição da funcionalidade.
2. Documentação.
3. Implementação.
4. Produção de assets.
5. Playtest.
6. Aprendizados.
7. Atualização da documentação.

---

# Indicadores

O projeto acompanhará principalmente indicadores qualitativos.

Exemplos:

- Frequência de uso.
- Tempo médio de estudo.
- Missões concluídas.
- Dias consecutivos.
- Interesse espontâneo da criança.
- Feedback dos pais.

Esses indicadores servirão para orientar futuras decisões de produto.

---

# Riscos Conhecidos

- Complexidade excessiva durante o MVP.
- Produção inconsistente de assets.
- Aumento do escopo antes da validação.
- Dependência excessiva de uma única IA.
- Mecânicas que incentivem uso do aplicativo em vez da prática do piano.

Todos os riscos deverão ser avaliados priorizando a simplicidade.

---

# Próxima Evolução

Após a validação do Reino do Piano poderão ser iniciados estudos para novos reinos, mantendo:

- a mesma identidade visual;
- o mesmo sistema de progressão;
- a mesma economia;
- o mesmo personagem;
- a mesma filosofia de produto.

A expansão do ecossistema somente ocorrerá após a validação bem-sucedida do MVP.

---

# Definição de Conclusão (Definition of Done)

Uma funcionalidade somente será considerada concluída quando:

- atender aos requisitos definidos;
- funcionar corretamente;
- possuir interface consistente;
- utilizar os assets oficiais;
- persistir corretamente os dados;
- não introduzir regressões;
- respeitar os princípios do Journey World;
- estar pronta para ser utilizada em um playtest.