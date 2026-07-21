# Journey World
# UI - Region Screen

**Versão:** 1.0
**Status:** Draft

> **Nota de status:** Revertido — ver `docs/Decision_Log.md` ("Revertido: MVP passa a ser a Era 3"). Esta tela **é o MVP ativo** — a Região é uma camada real de navegação, não uma simplificação.

---

# Objetivo

A tela da Região representa uma etapa específica dentro de um Reino.

Ela organiza os objetivos, missões e progresso relacionados àquela fase da jornada.

Seu propósito é ajudar a criança a entender onde está, o que já conquistou e qual é o próximo passo.

---

# Pergunta Principal

"O que posso fazer aqui hoje?"

---

# Filosofia

Cada Região representa um lugar do Reino.

Ela deve transmitir a sensação de descoberta e evolução.

A criança deve perceber que está explorando uma nova parte do mundo, sem se sentir sobrecarregada por informações.

---

# Objetivos da Tela

Permitir que a criança:

- compreenda o propósito da Região;
- visualize seu progresso;
- escolha uma missão;
- acompanhe seus objetivos;
- perceba o crescimento da jornada.

---

# Layout

A tela é composta por cinco áreas principais.

---

## Cabeçalho

Exibe:

- Nome da Região.
- Reino atual.
- Botão para voltar ao mapa do Reino.

Exemplo:

🌱 Bosque das Primeiras Notas

Reino do Piano

---

## Ilustração da Região

Imagem ilustrada representando o ambiente.

Pode conter:

- árvores;
- flores;
- notas musicais;
- elementos decorativos.

É uma imagem estática no MVP.

---

## Objetivo Atual

Exibe o principal objetivo da Região.

Exemplo:

"Conhecer o teclado e localizar o Dó Central."

---

## Lista de Missões

Apresenta as missões disponíveis.

Cada missão exibe:

- nome;
- descrição curta;
- status;
- recompensa;
- dificuldade (opcional).

Exemplo:

○ Encontrar o Dó Central

○ Explorar os sons graves

✔ Conhecer as teclas pretas

---

## Progresso

Resumo da evolução.

Exibe:

- objetivos concluídos;
- estrelas conquistadas;
- progresso da Região.

---

# Estados da Região

Uma Região pode estar:

- Bloqueada
- Disponível
- Em andamento
- Concluída

Mesmo concluída, permanece acessível para revisitas.

---

# Navegação

Mapa do Reino

↓

Região

↓

Missão

↓

Conclusão

↓

Região

---

# MVP

Implementar:

- ilustração;
- objetivo atual;
- lista de missões;
- progresso;
- botão voltar.

---

# Fora do MVP

Não implementar:

- NPCs;
- animações;
- clima;
- efeitos especiais;
- exploração livre.

---

# Critérios de Aceitação

A criança deve:

- entender rapidamente o propósito da Região;
- localizar facilmente a próxima missão;
- perceber seu progresso;
- conseguir iniciar uma missão com um único toque.

---

# Backlog

Possíveis evoluções:

- personagens guias;
- sons ambientes;
- objetos interativos;
- segredos da Região;
- colecionáveis escondidos;
- pequenas animações.

---

# Princípios

A Região deve ser calma.

O foco não é explorar o cenário.

O foco é incentivar a prática.

A ambientação existe para inspirar a criança, enquanto as missões conduzem sua evolução de forma clara e organizada.