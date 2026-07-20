# Journey World
# UI Component - Reward Card

**Versão:** 1.0
**Status:** Draft

---

# Objetivo

O Reward Card representa uma recompensa obtida ou disponível para a criança.

Seu objetivo é comunicar claramente a recompensa, seu significado e sua origem.

Este componente será utilizado em diversas partes do aplicativo, mantendo uma apresentação consistente para qualquer tipo de recompensa.

---

# Filosofia

A recompensa não é o objetivo da jornada.

Ela representa o reconhecimento pelo esforço realizado.

O Reward Card deve transmitir satisfação sem incentivar comportamento compulsivo.

---

# Estrutura

Cada Reward Card contém:

- Ícone ou ilustração
- Nome da recompensa
- Categoria
- Descrição
- Origem
- Data (quando aplicável)
- Estado

---

# Exemplo

🪙

15 Moedas

Recebidas pela missão:

"Praticar Escala de Dó"

19/07/2026

---

# Categorias

O Reward Card pode representar qualquer tipo de recompensa.

Exemplos:

- Moedas
- Estrelas
- Adesivos
- Cosméticos
- Itens colecionáveis
- Desbloqueios
- Recompensas configuradas pelos pais
- Experiências no mundo real

O componente não assume uma categoria específica.

---

# Propriedades

## Ícone

Obrigatório.

Representa visualmente a recompensa.

---

## Nome

Obrigatório.

Exemplos:

- 20 Moedas
- Primeira Estrela
- Maestro Iniciante
- Nova Roupa

---

## Descrição

Opcional.

Explica rapidamente o motivo da recompensa.

---

## Origem

Opcional.

Exemplos:

- Missão
- Evento
- Objetivo
- Presente dos Pais
- Missão Secreta

---

## Data

Opcional.

Importante principalmente quando exibido no histórico.

---

## Estado

Valores possíveis:

- Recebida
- Disponível para resgate
- Resgatada
- Expirada (futuro)

---

# Interações

Toque:

Visualizar detalhes.

Quando a recompensa for resgatável:

Exibir botão "Resgatar".

---

# Reutilização

Este componente poderá ser utilizado em:

- Tela de conclusão de missão
- Histórico de recompensas
- Storybook
- Perfil
- Loja
- Painel dos Pais
- Notificações

---

# MVP

Implementar:

- ícone;
- nome;
- descrição;
- origem;
- estado.

---

# Fora do MVP

Não implementar:

- animações;
- efeitos especiais;
- visualização 3D;
- compartilhamento.

---

# Critérios de Aceitação

A criança deve conseguir entender:

- o que recebeu;
- por que recebeu;
- se precisa realizar alguma ação;
- onde aquela recompensa poderá ser utilizada.

---

# Princípios

O Reward Card deve valorizar a conquista, nunca criar pressão por acumular recompensas.

Cada recompensa deve reforçar a mensagem de que o verdadeiro progresso aconteceu na vida real, e não dentro do aplicativo.