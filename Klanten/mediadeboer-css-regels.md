# Mediadeboer — CSS Architectuurregels
## Conflictvrije CSS voor Elementor, Canvas & Custom Tools

**Geldt voor:** Elementor Pro (Canvas & normale templates), HTML widgets, custom marketing tools (Keyword Mixer, Funnel Tool, Reports, etc.)

---

## 1. Unieke wrapper (namespace)

Elke tool krijgt exact **één unieke root-ID**.

```css
/* Correct */
#mdb-tool-keyword-mixer .mdb-btn { ... }

/* Fout — onscoped */
.mdb-btn { ... }
```

Voorbeelden: `#mdb-tool-keyword-mixer`, `#mdb-tool-funnel`, `#mdb-report-widget`

## 2. Geen globale selectors

Verboden (tenzij bewust site-breed): `*`, `html`, `body`, `a`, `img`, `button`, `.container`, `.header`, `.card`, `.btn`

```css
/* Correct */
#mdb-tool-keyword-mixer a { ... }
```

## 3. Prefix op alle classnamen

Vermijd generieke namen die Elementor/thema's gebruiken (`.container`, `.row`, `.col`, `.header`, `.nav`, `.card`, `.badge`, `.btn`, `.title`).

Gebruik altijd: `.mdb-container`, `.mdb-card`, `.mdb-btn`, `.mdb-title`

## 4. Scoped reset — alleen box-sizing

```css
#tool-id,
#tool-id *,
#tool-id *::before,
#tool-id *::after {
  box-sizing: border-box;
}
```

Geen globale margin/padding/typography resets.

## 5. CSS-variabelen per tool

```css
#tool-id {
  --mdb-bg: #0f172a;
  --mdb-text: #ffffff;
  --mdb-accent: #e67e22;
  background: var(--mdb-bg);
  color: var(--mdb-text);
}
```

## 6. `!important` is verboden

Uitzondering: alleen om Elementor inline styles te overrulen, altijd scoped.

```css
#tool-id .element { margin: 0 !important; }
```

## 7. Viewport-gedrag

- **Inline tools** (in content): geen `100vh`, `position: fixed`, `overflow: hidden`, `scroll-behavior`
- **Canvas-tools**: toegestaan, maar scoped: `#tool-id { min-height: 100vh; }`

## 8. Elementor classes nooit targeten

Nooit CSS schrijven voor: `.elementor-*`, `.e-*`, `.wp-*`, `.woocommerce-*`

## 9. Interactie-states scoped

```css
#tool-id .mdb-btn:hover { ... }
#tool-id input:focus { ... }
```

`outline: none` alleen met visueel alternatief.

## 10. Eén tool = één CSS-blok

Geen gedeelde styles tenzij bewust design system. Voor shared styles → één `MDB Tools Base CSS`, tools gebruiken variabelen + overrides.

---

## Checklist (per tool)

- [ ] Unieke wrapper-ID aanwezig?
- [ ] Alle selectors scoped onder wrapper?
- [ ] Geen `body`/`html`/`*` selectors?
- [ ] Geen generieke classnamen zonder `mdb-` prefix?
- [ ] Alleen box-sizing reset?
- [ ] Geen viewport-dwang tenzij Canvas?
- [ ] Geen onnodige `!important`?

**Kernprincipe:** Elke tool is een geïsoleerde applicatie, geen site-brede stijlbron.
