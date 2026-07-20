# Journey World
# UI - Mission Screen

**Versão:** 1.0
**Status:** Draft

> **Parcialmente Visão (pós-MVP).** Navegação via Região, registro no Storybook e validação parental totalmente configurável vão além do MVP ativo. No MVP ativo, a validação é automática por padrão (`docs/Decision_Log.md`, 2026-07-20) e as missões aparecem direto na aba Missões (sem tela dedicada por missão — ver `index.html`).

---

# Objetivo

A tela de Missão representa a atividade que a criança realizará no mundo real.

Ela deve ser simples, objetiva e motivadora.

Seu propósito não é ensinar a atividade, mas acompanhar sua execução e celebrar sua conclusão.

---

# Pergunta Principal

"O que vou fazer agora?"

---

# Filosofia

A missão é um compromisso consigo mesmo.

O aplicativo não substitui a prática.

Ele incentiva, organiza e registra essa prática.

A tela deve minimizar distrações e direcionar toda a atenção para a atividade.

---

# Estrutura

## Cabeçalho

Exibe:

- Nome da missão
- Região
- Botão voltar

Exemplo:

Praticar Escala de Dó

Bosque das Primeiras Notas

---

## Objetivo

Descrição clara da atividade.

Exemplo:

"Pratique a escala de Dó maior utilizando ambas as mãos."

---

## Instruções

Lista simples de passos.

Exemplo:

- Posicione corretamente as mãos.
- Toque lentamente.
- Mantenha ritmo constante.
- Repita 5 vezes.

Sempre que possível, utilizar linguagem infantil.

---

## Tempo

Caso a missão possua duração.

Exemplos:

20 minutos

ou

Sem duração

---

## Cronômetro (Opcional)

Quando habilitado.

Permite:

- iniciar;
- pausar;
- finalizar.

O cronômetro auxilia a criança, mas não é obrigatório.

Pais poderão configurar se desejam utilizá-lo.

---

## Recursos

A missão pode possuir materiais auxiliares.

Exemplos:

- imagem;
- vídeo;
- áudio;
- partitura;
- PDF;
- link externo.

No MVP será implementado apenas quando necessário.

---

## Botão Principal

"Iniciar Missão"

Após iniciada:

"Concluir Missão"

---

# Estados

Disponível

↓

Em andamento

↓

Aguardando confirmação (quando necessário)

↓

Concluída

---

# Validação Parental

Cada missão pode definir sua forma de validação.

Opções:

- Conclusão livre.
- Confirmação dos pais.
- Confirmação automática.
- Cronômetro mínimo.

A estratégia é configurável por jornada ou por missão.

---

# Recompensas

Ao concluir a missão, ela poderá gerar:

- moedas;
- estrelas;
- adesivos;
- desbloqueios;
- progresso da árvore;
- registros no Storybook.

As recompensas são totalmente configuráveis.

Uma missão pode conceder qualquer combinação delas.

---

# Navegação

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

- título;
- descrição;
- botão iniciar;
- botão concluir;
- cronômetro opcional;
- validação simples;
- integração com recompensas.

---

# Fora do MVP

Não implementar:

- vídeos incorporados;
- chat durante missão;
- multiplayer;
- ranking;
- comentários.

---

# Critérios de Aceitação

A criança deve:

- entender rapidamente o que precisa fazer;
- iniciar a missão com um toque;
- concluir a missão sem dúvidas;
- sentir que completou uma etapa importante.

---

# Princípios

A missão deve incentivar a prática no mundo real.

A tela deve desaparecer da atenção da criança o mais rápido possível.

O objetivo não é permanecer no aplicativo.

O objetivo é viver a experiência fora dele e retornar apenas para registrar essa conquista.