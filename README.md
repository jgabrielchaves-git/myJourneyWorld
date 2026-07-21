# Journey World

Journey World é uma plataforma de gamificação infantil criada para transformar o aprendizado em uma jornada divertida, acolhedora e significativa.

O projeto nasceu com um objetivo simples:

> Fazer uma criança querer voltar espontaneamente para praticar piano todos os dias.

O primeiro reino do jogo é o **Reino do Piano**, onde a criança evolui através de missões diárias, desafios, repertório, eventos, conquistas e uma progressão visual (a Árvore do Crescimento) que recompensa consistência e dedicação.

No futuro, Journey World poderá expandir para outros Reinos, como Ginástica Rítmica, Escola, Família, Virtudes e Jornada Espiritual, todos compartilhando o mesmo personagem, economia e progressão.

## Objetivos do MVP

- Validar a hipótese de que gamificação aumenta o engajamento no estudo de piano.
- Criar uma experiência acolhedora para crianças.
- Desenvolver disciplina através de pequenas conquistas.
- Tornar o progresso visível.
- Criar uma rotina prazerosa de prática.

## Tecnologias

Atualmente o projeto utiliza:

- HTML
- CSS
- JavaScript
- LocalStorage

A arquitetura será preparada para futuras migrações sem comprometer o MVP.

## Estrutura do Projeto

```
myJourneyWorld/
│
├── README.md
├── CLAUDE.md
├── CURRENT_STATE.md
├── index.html
│
├── docs/
│   ├── product/       (Manifesto, Charter, Vision, Principles)
│   ├── domain/         (Glossary e outros modelos de domínio)
│   ├── systems/        (Economy, Reward System, Mission System...)
│   ├── game-design/    (GDD, Art Direction, Content Design...)
│   ├── UI/              (Design System, telas, componentes)
│   ├── Art_Bible.md
│   ├── UX_Bible.md
│   ├── Roadmap.md
│   ├── Backlog.md
│   └── Decision_Log.md
│
├── assets/
├── src/
└── prompts/
```

## Filosofia

Journey World não é um jogo sobre ganhar estrelas.

É um jogo sobre celebrar pequenas vitórias.

Toda funcionalidade deve responder à pergunta:

> "Isso torna a jornada da criança mais divertida e significativa?"

Caso contrário, ela provavelmente não pertence ao MVP.
