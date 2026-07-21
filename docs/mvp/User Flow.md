# Journey World
# MVP - User Flow

**Versão:** 1.0
**Status:** Draft

> **Nota de status:** Revertido — ver `docs/Decision_Log.md` ("Revertido: MVP passa a ser a Era 3"). O fluxo Jardim → Reino → Região → Storybook **é o MVP ativo**. Login (Google/Apple) continua **fora** do MVP — confirmado explicitamente, nem no curto prazo (junto com Splash e Perfil).

---

# Objetivo

Este documento descreve o fluxo principal do MVP do Journey World.

Seu propósito é orientar o desenvolvimento da experiência do usuário, garantindo que todas as telas e funcionalidades estejam conectadas de forma simples e intuitiva.

---

# Princípios

O MVP deve ser:

- simples;
- acolhedor;
- intuitivo;
- rápido;
- fácil de navegar.

Toda tela deve responder apenas uma pergunta.

---

# Fluxo Principal

Abrir App

↓

Casa

↓

Jardim

↓

Escolher Jornada

↓

Entrar no Reino

↓

Escolher Região

↓

Escolher Missão

↓

Executar Atividade

↓

Concluir Missão

↓

Receber Recompensas

↓

Atualizar Progresso

↓

Registrar Storybook

↓

Voltar para Casa

---

# 1. Casa

Pergunta:

"O que quero fazer hoje?"

Função:

Ponto central do aplicativo.

Elementos:

- avatar;
- acesso ao Jardim;
- cartas;
- notificações;
- atalhos;
- resumo do dia.

MVP:

Tela estática.

Sem animações complexas.

---

# 2. Jardim

Pergunta:

"Qual jornada quero cultivar hoje?"

Elementos:

- Árvores;
- Nome da jornada;
- Progresso visual;
- Estrelas;
- Indicador de atividades disponíveis.

Exemplo:

🌳 Árvore da Música

⭐⭐⭐

Missão disponível.

Ação:

Entrar na jornada.

---

# 3. Reino

Pergunta:

"O que quero aprender?"

Exemplo:

🎹 Reino do Piano.

Elementos:

- mapa simples;
- regiões;
- progresso.

---

# 4. Região

Pergunta:

"O que existe neste lugar?"

Exemplo:

🌱 Bosque das Primeiras Notas.

Elementos:

- objetivos;
- missões;
- progresso;
- conquistas.

---

# 5. Missão

Pergunta:

"O que devo fazer agora?"

Exemplos:

- praticar 20 minutos;
- tocar uma escala;
- tocar uma música;
- registrar apresentação.

Elementos:

- descrição;
- duração;
- progresso;
- botão concluir.

---

# 6. Conclusão

Pergunta:

"O que conquistei?"

Exemplo:

✅ Missão concluída

+ 5 moedas

⭐ Nova estrela

🌳 Árvore cresceu

📖 Registro criado

---

# 7. Storybook

Pergunta:

"O que estou construindo?"

Exemplo:

"Hoje você completou sua primeira prática."

---

# 8. Retorno

O usuário volta para:

Casa

ou

Jardim

---

# Fluxo MVP Piano

Casa

↓

Jardim

↓

Árvore da Música

↓

Reino do Piano

↓

Bosque das Primeiras Notas

↓

Missão:

"Praticar 20 minutos"

↓

Conclusão

↓

Estrela

↓

Storybook

↓

Casa

---

# MVP Técnico

Implementar primeiro:

- Casa;
- Jardim;
- Reino do Piano;
- Região 1;
- Missão simples;
- Estrelas;
- Moedas;
- Storybook básico.

Não implementar inicialmente:

- pets;
- animações;
- marketplace;
- multiplayer;
- eventos complexos;
- personalização avançada.

---

# Critério de sucesso

A criança deve conseguir:

- entender o fluxo;
- completar uma missão;
- sentir progresso;
- desejar voltar no dia seguinte.

Sem necessidade de explicações longas.

Sem complexidade desnecessária.

---

# Princípios

Cada clique deve aproximar a criança de:

- aprender;
- cultivar;
- registrar memórias;
- viver sua jornada.