# Journey World
## Art Bible

**Versão:** 1.0 (Draft)

**Status:** Aguardando Definição

**Autor:** Gabriel Chaves

---

# Status

🔲 Aguardando definição.

---

# O que precisa ser definido

- Paleta de cores (alinhada aos princípios: sem cores agressivas — ver [Product_Principles.md](product/Principles.md))
- Estilo do personagem kawaii
- Iconografia (missões, estrelas, moedas, conquistas)
- Estilo visual da casa e do Reino do Piano
- Estilo dos adesivos/medalhas (Bronze, Prata, Ouro, Brilhante, Arco-íris)
- Tipografia

---

# Restrições Técnicas (já definidas)

Independentemente da direção de arte escolhida, a implementação deve seguir:

- SVG para elementos de interface
- PNG para ilustrações
- Animações via CSS
- Poucos assets, baixo consumo de memória

---

# Padrão de Sprites (Personagem, Pets, Acessórios)

Regra criada após um bug de proporção causado por assets com fundo/glow residual e margem interna inconsistente.

## Transparência

- O arquivo final deve ter canal alpha real (não só um fundo que "parece" transparente).
- Antes de aceitar um asset novo, validar o alpha pixel a pixel (não confiar só na pré-visualização — alguns visualizadores ignoram o canal alpha e mostram a cor de fundo "crua").

## Crop

- Nenhuma margem/vinheta sobrando ao redor do conteúdo. O corte deve ser justo ao contorno real (glow/halo de fundo com alpha baixo não conta como conteúdo).
- Margem de respiro pequena e proposital (não acidental): ~2–4% do lado, mais um pouco no topo se for personagem/pet de corpo inteiro (espaço para acessório de cabeça).
- Pé/base do sprite deve ficar rente à borda inferior do canvas — o layout usa `object-position:bottom center`, então qualquer margem inferior "sobe" o personagem visualmente.

## Personagem / Pets (corpo inteiro)

- Proporção alvo do canvas: ~0,42 (largura/altura) — referência atual: 408×968px (`char-base.webp`).
- Todas as poses de um mesmo personagem/pet (parado, piscando, comemorando etc.) devem ser geradas a partir do mesmo enquadramento/câmera, para não "pular" ao trocar de camada.

## Acessórios (laços, roupas, chapéus, itens de pet)

- Crop justo ao próprio objeto, sem sobra — o tamanho visual em jogo é controlado só por CSS (`width` em %), então padding interno no PNG/WebP muda a escala sem avisar.
- Posicionamento (`top`/`left`) é calculado em cima da proporção do personagem-base; ao trocar o personagem-base, reconferir o encaixe de todos os acessórios.

---

# Próximo Passo

Assim que a direção de arte for fornecida (referências visuais, paleta, moodboard), este documento deve ser atualizado antes de qualquer implementação visual definitiva.
