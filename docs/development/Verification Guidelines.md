# Journey World
# Development - Verification Guidelines

**Versão:** 1.0
**Status:** Ativo

---

# Objetivo

Este documento registra aprendizados técnicos sobre como verificar o `index.html` (aplicação de arquivo único, sem build) de forma confiável, para não perder tempo redescobrindo o mesmo problema em uma futura sessão.

Documento técnico — mantido pelo Claude Code (`CLAUDE.md`), não pelo Product Owner.

---

# 1. Screenshot em branco no Chromium headless (Playwright)

**O problema:** ao tirar um screenshot de página inteira (`page.screenshot()`) da tela da Casa em Chromium headless, a imagem pode vir inteiramente em branco — sem o quarto, o personagem ou a árvore — mesmo com o DOM, o CSS computado e o `getBoundingClientRect()` de todos os elementos corretos. Screenshots com `clip` de uma sub-região da mesma área renderizam corretamente, o que descarta erro de layout.

**Causa:** artefato de compositing do Chromium headless em páginas com animação CSS `infinite` rodando havia muito tempo antes do screenshot (no caso, a respiração contínua do personagem, `.char-figure { animation: breathe ... infinite }`). Não é um bug da aplicação.

**Solução:** chamar `page.emulateMedia({ reducedMotion: 'reduce' })` antes de navegar/tirar o screenshot. Isso também aciona o `@media (prefers-reduced-motion: reduce)` que a própria aplicação já implementa (congelando as animações), então tem o benefício colateral de tornar os screenshots determinísticos.

```js
const page = await browser.newPage({ viewport: { width: 420, height: 860 } });
await page.emulateMedia({ reducedMotion: 'reduce' });
```

**Ao investigar um screenshot suspeito no futuro:** antes de assumir regressão visual, testar com `reducedMotion: 'reduce'`. Se o problema desaparecer, é este artefato de captura, não um bug real.

---

# 2. Como verificar este projeto (sem build, sem servidor)

Por ser um arquivo único (`index.html`, HTML/CSS/JS puro, `CLAUDE.md`), a verificação não precisa de build nem de servidor local — basta abrir o arquivo direto via `file://` (Playwright ou navegador comum).

```js
const FILE_URL = 'file:///' + path.resolve('C:/Users/jgabr/myJourneyWorld/index.html').replace(/\\/g, '/');
await page.goto(FILE_URL);
```

Sempre verificar via clique real na interface (nav, cards, botões) — não chamar funções JS diretamente. O estado (`journeyWorld_v1` no LocalStorage) persiste entre `page.reload()` na mesma `page`/contexto, o que permite testar persistência sem reabrir o navegador.

---

# 3. Modal de adesivo pode abrir com atraso (~950ms) após concluir missão

**Observação:** `checkAchievements()` pode disparar o modal de adesivo desbloqueado através de um `setTimeout` de ~950ms após a Conclusão da missão. Um script de verificação que assume que "nenhum modal aberto" é o estado final logo após clicar em concluir pode ser interrompido por esse modal aparecendo depois, bloqueando o próximo clique (`pointer-events` do overlay).

**Como lidar na verificação:** usar um loop de poll com prazo (~3s) em vez de um número fixo de tentativas de dispensar modais, e aguardar pelo menos ~1s extra antes de concluir que nenhum modal está aberto.

**Nota de produto (não é bug, apenas registrado aqui como observação de UX):** esse atraso significa que, na prática, o adesivo pode aparecer para a criança já depois de ela ter navegado para outra tela. Repassar ao Product Owner caso vire relevante para o polimento da experiência.
