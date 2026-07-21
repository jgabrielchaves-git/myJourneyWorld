# Journey World
# UI - House Screen

**Versão:** 1.0
**Status:** Draft

> **Nota de status:** Revertido — ver `docs/Decision_Log.md` ("Revertido: MVP passa a ser a Era 3"). Esta Casa (Jardim, Caixa de Correio, Estante da Jornada) **é o MVP ativo** — substitui a Casa com abas descrita em `docs/systems/House.md` (Era 2, ver pendência de reconciliação nesse doc).

---

# Objetivo

A Casa é o ponto central do Journey World.

Ela representa o lar da criança dentro do aplicativo.

É o lugar onde ela retorna após concluir suas jornadas, acompanha novidades e inicia um novo dia de aprendizado.

A Casa transmite segurança, acolhimento e pertencimento.

---

# Pergunta Principal

"O que quero fazer hoje?"

---

# Filosofia

A Casa não é um dashboard.

Ela não deve parecer uma tela administrativa.

Ela deve transmitir a sensação de estar em casa.

Cada elemento presente possui significado e contribui para contar a história da criança.

---

# Objetivos da Tela

Permitir que a criança:

- inicie sua jornada diária;
- visualize novidades importantes;
- acesse rapidamente o Jardim;
- acompanhe mensagens da família;
- consulte seu Storybook.

---

# Layout

O MVP utilizará uma ilustração simples de uma casa.

Não haverá movimentação do personagem.

A navegação acontecerá por áreas clicáveis.

---

# Estrutura

## Cabeçalho

Elementos:

- Nome da criança.
- Saudação.
- Painel dos Pais.

Exemplo:

"Bom dia, Ana Paula!"

---

## Sala Principal

Representa o ambiente inicial.

Elementos:

- Avatar.
- Acesso ao Jardim.
- Caixa de Correio.
- Estante da Jornada.

---

# Avatar

O avatar representa a criança.

No MVP:

Imagem estática.

Sem animações.

No futuro poderá utilizar roupas, acessórios e expressões.

---

# Jardim

Elemento de maior destaque da Casa.

Representa todas as Jornadas disponíveis.

Ao tocar no Jardim, o usuário acessa a tela Garden.

---

# Caixa de Correio

Permite visualizar mensagens.

Exemplos:

- mensagens dos pais;
- lembretes;
- comunicações do sistema.

No MVP:

Lista simples de mensagens.

---

# Estante da Jornada

Representa o Storybook.

Ao selecionar, a criança poderá revisitar sua história.

No MVP:

Acesso direto ao Storybook.

---

# Navegação

Casa

↓

Jardim

↓

Reino

---

Casa

↓

Storybook

---

Casa

↓

Mensagens

---

Casa

↓

Painel dos Pais

---

# MVP

Implementar:

- Avatar.
- Jardim.
- Caixa de Correio.
- Estante da Jornada.
- Painel dos Pais.

---

# Fora do MVP

Não implementar:

- pets circulando;
- personagem caminhando;
- troca de cômodos;
- decoração da casa;
- móveis personalizados;
- iluminação dinâmica;
- clima.

---

# Critérios de Aceitação

A criança deve:

- compreender que a Casa é seu ponto de partida;
- localizar facilmente o Jardim;
- perceber que recebeu novas mensagens;
- conseguir acessar o Storybook rapidamente.

---

# Backlog

Possíveis evoluções:

- novos cômodos;
- decoração personalizada;
- pets interativos;
- objetos colecionáveis;
- aquário;
- biblioteca;
- oficina;
- quarto;
- sala de música;
- álbum de fotografias físico;
- calendário de eventos.

---

# Princípios

A Casa deve transmitir paz.

Ela representa um lugar seguro.

Não deve competir visualmente com os Reinos.

Sua função é acolher a criança antes e depois de cada jornada, reforçando que o aprendizado faz parte da vida cotidiana e que sempre existe um lugar para retornar.