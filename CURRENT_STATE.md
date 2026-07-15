# CURRENT_STATE

> Última atualização: 2026-07-15

## Onde estamos hoje?

Fase 0 — Fundação. O repositório acabou de ser estruturado: documentação de produto (Charter, Vision, Principles, GDD, Art Bible, UX Bible, Roadmap, Backlog) foi criada a partir do Overview e da Proposta de MVP inicial. Nenhum código de aplicação foi implementado dentro deste repositório ainda.

## O que já existe?

- Estrutura de pastas completa (`docs/`, `assets/`, `src/`, `prompts/`).
- `README.md` e `CLAUDE.md` na raiz.
- Documentação completa do MVP em `docs/00` a `docs/07`.
- Um protótipo "vertical slice" do Mundo Piano em HTML único (`journey_world_vertical_slice.html`, título "Journey World — Mundo Piano"), localizado em `~/Downloads` — **ainda fora deste repositório**. Existem 3 variações do arquivo no Downloads; a mais recente é de 2026-07-13 21:25. Não foi integrado a `src/` ainda por decisão explícita (aguardando confirmação de qual versão é a definitiva).

## O que está funcionando?

Nada dentro deste repositório ainda — é só documentação. O protótipo externo em Downloads não foi validado/revisado dentro deste contexto.

## O que falta?

- Decidir se e qual versão do vertical slice será integrada a `src/`.
- Direção de arte (paleta, personagem, iconografia) — ver [docs/04_Art_Bible.md](docs/04_Art_Bible.md), status "aguardando definição".
- Implementação do MVP em si (Casa, Mundo Piano, Missões, XP, Estrelas, Loja, Álbum, Eventos, Painel dos Pais, Save).
- `git init` e primeiro push para `https://github.com/jgabrielchaves-git/myJourneyWorld`.
- Configuração de GitHub Pages (decidir se serve a partir da raiz, de `/docs`, ou de uma branch `gh-pages` — hoje `docs/` já está em uso para documentação de produto, então é preciso decidir onde o build/site do jogo vai morar).

## Qual é a próxima tarefa?

Revisar o(s) arquivo(s) `journey_world_vertical_slice*.html` do Downloads junto com o usuário, decidir qual vira a base de `src/`, e então iniciar o repositório Git local com o primeiro commit.

## O que não deve ser alterado?

- Os valores do projeto: acolhimento, progresso, simplicidade, alegria, disciplina, constância (ver [docs/02_Product_Principles.md](docs/02_Product_Principles.md)).
- A lista "nunca utilizar": violência, excesso de efeitos, interfaces poluídas, cores agressivas, excesso de texto.
- O princípio de que recompensas não substituem motivação intrínseca (estrelas nunca são removidas; sem aleatoriedade nas conquistas; moedas compram só cosmético).
- A separação de responsabilidades do [CLAUDE.md](CLAUDE.md): Claude decide arquitetura/implementação; **não** decide gameplay, identidade visual, direção de arte, economia ou game design.

## Quais decisões estão congeladas?

- Stack do MVP: HTML, CSS, JavaScript puro (sem frameworks, salvo necessidade real).
- Persistência: LocalStorage no MVP, com código preparado para migração futura online.
- Primeiro mundo: Piano. Mundos futuros (Ginástica Rítmica, Escola, Família, Virtudes, Jornada Espiritual) ficam no backlog até o MVP do Piano ser validado.
- Escopo fechado do MVP: Casa, Mundo Piano, Missões, XP, Estrelas, Loja, Álbum, Eventos, Painel dos Pais, Save — tudo além disso é backlog (ver [docs/07_Backlog.md](docs/07_Backlog.md)).
- Hipótese única a validar: gamificação aumenta motivação/consistência no estudo de piano (ver [docs/00_Project_Charter.md](docs/00_Project_Charter.md)).
