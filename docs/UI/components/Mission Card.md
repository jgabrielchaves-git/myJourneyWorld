# Journey World
# UI Component - Mission Card

**Versão:** 1.0
**Status:** Draft

---

# Objetivo

O Mission Card representa uma missão disponível para a criança.

Ele resume todas as informações necessárias para que ela compreenda rapidamente a atividade proposta e possa iniciá-la com um único toque.

Este componente será reutilizado em todas as Jornadas do Journey World.

---

# Filosofia

Uma missão representa uma pequena ação realizada no mundo real.

O Mission Card deve transmitir simplicidade.

A criança deve compreender imediatamente:

- o que fazer;
- quanto tempo levará;
- o que ganhará;
- seu estado atual.

---

# Estrutura

Cada Mission Card contém:

- Ícone da missão
- Nome
- Descrição curta
- Duração (quando existir)
- Tipo
- Recompensas
- Status
- Botão principal

---

# Exemplo

🎹

Praticar Escala de Dó

Treine lentamente utilizando ambas as mãos.

⏱ 20 minutos

⭐ Pode gerar estrela

🪙 +15 moedas

▶ Iniciar

---

# Propriedades

## Nome

Obrigatório.

Texto curto.

Máximo recomendado:

40 caracteres.

---

## Descrição

Obrigatória.

Resumo simples da missão.

Máximo recomendado:

120 caracteres.

---

## Tipo

Exemplos:

- Prática
- Estudo
- Apresentação
- Desafio
- Revisão
- Evento

O tipo influencia apenas a apresentação visual.

---

## Duração

Opcional.

Pode ser:

- 10 minutos
- 20 minutos
- 1 hora

Ou inexistente.

---

## Recompensas

Pode exibir qualquer combinação de:

- moedas;
- estrelas;
- adesivos;
- desbloqueios;
- recompensas configuradas pelos pais.

O componente não assume que todas estarão presentes.

---

## Status

Valores possíveis:

- Disponível
- Em andamento
- Aguardando validação
- Concluída
- Expirada (futuro)
- Bloqueada

---

# Interações

Toque:

Abrir detalhes da missão.

Botão principal:

Iniciar missão.

---

# Estados Visuais

## Disponível

Botão destacado.

---

## Em andamento

Mostrar progresso.

---

## Concluída

Exibir indicador visual.

Sem botão iniciar.

---

## Bloqueada

Exibir motivo do bloqueio.

---

# Reutilização

Este componente poderá ser utilizado em:

- Região
- Objetivos
- Eventos
- Missões Diárias
- Missões Semanais
- Missões Mensais
- Missões Secretas
- Dashboard dos Pais

---

# MVP

Implementar:

- nome;
- descrição;
- duração;
- recompensas;
- status;
- botão iniciar.

---

# Fora do MVP

Não implementar:

- animações;
- contagem regressiva;
- vídeos;
- efeitos sonoros;
- expansão automática.

---

# Critérios de Aceitação

A criança deve conseguir responder rapidamente:

- O que preciso fazer?
- Quanto tempo isso leva?
- Vale a pena fazer agora?
- Como começo?

Sem precisar abrir outra tela.

---

# Princípios

Uma missão deve parecer acessível.

O card deve reduzir qualquer sensação de dificuldade.

O foco é incentivar a criança a dar o próximo pequeno passo.