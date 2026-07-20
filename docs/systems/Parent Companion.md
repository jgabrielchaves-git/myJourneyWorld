# Journey World
# System - Parent Companion

**Versão:** 1.0  
**Status:** Draft

> **Parcialmente Visão (pós-MVP).** Dashboard, Inbox, Modo Confiança, Timeline, Diário Compartilhado e Pedidos de Resgate (ligados à Loja da Família) vão além do "Painel dos Pais" simples do MVP congelado (`CLAUDE.md`, `docs/product/Charter.md`) — ver `docs/Decision_Log.md` (2026-07-20). No MVP ativo, o Painel dos Pais contempla apenas: PIN, resumo (estrelas/sequência), avançar repertório, criar/remover Eventos, alterar PIN. A seção "MVP" abaixo refere-se ao MVP desta visão futura, não ao MVP ativo.

---

# Objetivo

O Parent Companion é o sistema responsável por conectar a família à jornada da criança.

Seu propósito é permitir que os responsáveis acompanhem, incentivem, configurem e participem ativamente do crescimento da criança dentro do Journey World.

Este sistema não deve ser visto como um painel administrativo.

Ele faz parte da experiência do produto.

---

# Filosofia

A criança é a protagonista da jornada.

Os pais são seus maiores apoiadores.

O Parent Companion existe para fortalecer essa relação.

Toda funcionalidade deve aproximar pais e filhos, nunca transformar os responsáveis apenas em fiscais.

---

# Responsabilidades

O Parent Companion é responsável por:

- acompanhar a evolução;
- validar atividades;
- configurar jornadas;
- configurar recompensas;
- enviar mensagens;
- visualizar relatórios;
- administrar configurações;
- acompanhar notificações;
- registrar acontecimentos importantes.

---

# Dashboard

O Dashboard apresenta uma visão geral da jornada.

Exemplos:

- estrelas conquistadas;
- moedas atuais;
- objetivos ativos;
- sessões realizadas;
- sequência de dias;
- eventos próximos;
- últimas conquistas.

O objetivo é permitir que os pais compreendam rapidamente como está a evolução da criança.

---

# Inbox

A Inbox centraliza toda a comunicação entre o jogo e os responsáveis.

Exemplos:

- recompensa resgatada;
- novo adesivo;
- medalha conquistada;
- troféu desbloqueado;
- mensagem da criança;
- objetivo concluído;
- solicitação de aprovação;
- evento próximo;
- lembretes.

Cada notificação permanece registrada até ser arquivada ou lida.

---

# Timeline

A Timeline registra acontecimentos importantes da jornada.

Exemplos:

- primeira apresentação;
- nova música aprendida;
- recital;
- aniversário;
- sequência de estudos;
- conquista rara.

A Timeline representa uma linha do tempo da infância da criança.

---

# Validação

As atividades podem exigir aprovação.

Cada jornada poderá configurar seu modo de validação.

Modos previstos:

- automático;
- confirmação obrigatória;
- confirmação opcional;
- modo confiança.

---

# Modo Confiança

Quando ativado, determinadas atividades não exigem aprovação manual.

Os pais continuam acompanhando os acontecimentos por meio da Inbox e dos relatórios.

Esse modo reduz o esforço operacional sem perder visibilidade.

---

# Configuração de Recompensas

Os responsáveis podem criar recompensas personalizadas.

Cada recompensa poderá definir:

- nome;
- descrição;
- categoria;
- imagem;
- custo em moedas;
- quantidade disponível;
- validade;
- necessidade de aprovação.

Exemplos:

- Sorvete
- Cinema
- Passeio
- Viagem
- Escolher o filme da noite

---

# Pedidos de Resgate

Quando a criança resgata uma recompensa da Família, um Pedido de Resgate é criado.

Fluxo:

Solicitação

↓

Inbox

↓

Aprovação

↓

Entrega

↓

Histórico

Todos os pedidos permanecem registrados.

---

# Mensagens

Os responsáveis podem enviar mensagens para a criança.

Exemplos:

- incentivo;
- parabéns;
- versículos;
- lembretes;
- comemorações.

As mensagens podem ser associadas a:

- recompensas;
- eventos;
- objetivos;
- sessões;
- datas especiais.

---

# Diário Compartilhado

Pais e filhos podem registrar momentos importantes da jornada.

Exemplos:

- fotos;
- comentários;
- pequenas histórias;
- reflexões.

Esse diário representa uma memória permanente da infância.

No MVP, o diário será composto apenas por mensagens de texto.

---

# Relatórios

O Parent Companion disponibiliza relatórios de evolução.

Exemplos:

## Geral

- estrelas;
- moedas;
- sessões;
- tempo estudado.

---

## Jornada

- progresso;
- objetivos;
- eventos;
- habilidades.

---

## Hábitos

- frequência;
- sequência;
- constância.

---

## Economia

- moedas obtidas;
- moedas gastas;
- recompensas resgatadas.

---

## Coleções

- adesivos;
- medalhas;
- troféus.

---

# Configuração das Jornadas

Os responsáveis podem configurar:

- missões;
- objetivos;
- recompensas;
- eventos;
- validações;
- dificuldade;
- permissões.

Cada jornada pode possuir configurações independentes.

---

# Configuração Geral

Exemplos:

- idioma;
- sons;
- notificações;
- animações;
- modo confiança;
- permissões.

---

# Permissões

Cada funcionalidade pode definir seu nível de acesso.

Exemplos:

- apenas pais;
- criança;
- compartilhado.

---

# Notificações

O Parent Companion recebe eventos gerados pelos demais sistemas.

Exemplos:

- recompensa entregue;
- objetivo concluído;
- novo adesivo;
- pedido de resgate;
- nova mensagem;
- sequência interrompida;
- evento próximo.

A estratégia de entrega (Inbox, push, e-mail etc.) será definida futuramente.

---

# MVP

O MVP contempla:

- Dashboard;
- Inbox;
- Validação;
- Modo Confiança;
- CRUD de Recompensas da Família;
- Pedidos de Resgate;
- Mensagens;
- Relatórios básicos.

---

# Backlog

Possíveis evoluções:

- fotos;
- vídeos;
- áudio;
- mensagens por voz;
- calendário;
- lembretes automáticos;
- múltiplos responsáveis;
- avós e familiares;
- compartilhamento de conquistas;
- integração com agenda;
- sugestões por IA;
- desafios familiares;
- metas compartilhadas;
- notificações push;
- widgets;
- aprovação remota.

---

# Princípios

O Parent Companion deve sempre:

- aproximar pais e filhos;
- reduzir burocracia;
- preservar memórias;
- incentivar conversas;
- apoiar a jornada da criança.

Ele nunca deve transformar os pais apenas em fiscalizadores da plataforma.