# Character

Versão: 1.1

Status: Ativo — descreve o que já está implementado no slice do MVP

---

## Objetivo

O Personagem representa a criança dentro do Journey World. Não é um avatar genérico e customizável — é um companheiro visual fixo que reage à dedicação real da criança, reforçando a filosofia de "crescimento visível" do `Manifesto.md`.

---

## Experiência do usuário

A criança vê o Personagem parado na Casa, respirando suavemente. Ao completar uma missão, ele comemora com uma pequena animação de pulo e brilhos. Não há tela dedicada ao Personagem — ele vive dentro da cena da Casa.

---

## Fluxo

Não há fluxo de navegação próprio. O Personagem é renderizado como parte da view Casa e reage a eventos disparados por outras telas (conclusão de missão).

---

## Funcionalidades

- Ilustração parada (`char-base`) com animação contínua de respiração (leve movimento vertical).
- Piscar automático e periódico (a cada ~4,2s), trocando para a arte `char-blink`.
- Comemoração (`char-cheer`) ao concluir uma missão: pulo com brilhos ao redor, ~0,9s.
- Acessório de laço (`char-bow`) com cor customizável pela Loja (item cosmético, ver `Reward System.md`/`Economy.md`).

---

## Regras de negócio

- O Personagem nunca é customizável em forma, apenas em pequenos acessórios cosméticos (ex.: cor do laço) — vendidos exclusivamente por Moedas, nunca alteram a identidade do Personagem.
- A comemoração é disparada exclusivamente por uma conquista real (missão concluída), nunca por interação ociosa — consistente com "toda recompensa virtual nasce de uma conquista real" (`Manifesto.md`).

---

## Estados

| Estado | Quando ocorre |
|---|---|
| Parado (base) | Estado padrão |
| Piscando | A cada ~4,2s, por ~160ms |
| Comemorando | Ao concluir uma missão, por ~0,9s |

---

## Casos extremos

- Se duas missões forem concluídas em sequência rápida, a animação de comemoração reinicia do zero em vez de acumular.
- Piscar é suspenso automaticamente durante a comemoração.

---

## Configurações

Nenhuma configuração pelos pais. `prefers-reduced-motion` do sistema operacional reduz a duração de todas as animações (ver regra global em `docs/UI/Design System.md`).

---

## MVP

- Ilustração parada + respiração + piscar.
- Comemoração ao concluir missão.
- Acessório cosmético (laço) equipável via Loja.

---

## Pós-MVP

Customização visual mais ampla (roupas, penteados, expressões) é Visão de longo prazo — ver `docs/product/Vision.md` ("O Personagem"). Não implementar sem aprovação do Product Owner.

---

## Backlog específico

Nenhum item aprovado no momento.
