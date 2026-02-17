# INSTRUCCIONS - Generador de Landings Adds Nubulus

## Objectiu

Generar automàticament landings HTML+CSS a partir de markdown estructurat, mantenint estil visual consistent de Nubulus amb els nous components moderns.

---

## 1. ESTRUCTURA DEL MARKDOWN D'ENTRADA

El markdown d'entrada segueix aquesta estructura bàsica:

- `# Títol` = Inici del HERO o secció principal
- `## Subtítol` = Tagline del hero o títol de secció
- `---` = Separador (nova secció visual)
- `### Subsecció` = Subtítol dins secció
- `[Text](#ancla)` = CTA/enllaç
- `- Item` = Llista amb viñetes
- `1. Item` = Llista numerada
- Paràgraf = Text normal

---

## 2. COMPONENTS DISPONIBLES

### 2.1 HERO SECTIONS

**Hero Gradient (NOU - RECOMANAT)**

Usa aquest per defecte per landings modernes.

Estructura HTML:

- `<section class="hero-gradient">`
  - `<div class="hero-overlay"></div>`
  - `<div class="container">`
    - `<div class="hero-content">`
      - `<span class="hero-tag">` - Tag opcional
      - `<h1 class="hero-title">` - Títol principal
      - `<h2 class="hero-subtitle">` - Subtítol
      - `<p class="hero-text">` - Text introductori
      - `<div class="hero-features">` - Llista de característiques
        - `<div class="hero-feature-item">` - Cada característica
      - `<a class="cta-primary" href="#service-form">` - CTA principal

Quan usar-lo:

- Landings de serveis professionals
- Quan vols destacar múltiples beneficis
- Quan necessites un hero impactant

**Hero Simple (Compatible)**

Mantingut per compatibilitat amb landings antigues.

Estructura HTML:

- `<section class="hero">`
  - `<div class="container">`
    - `<h2>` - Subtítol
    - `<p>` - Text
    - `<a class="contact-btn">` - CTA

---

### 2.2 SECTION HEADER (NOU)

Component per iniciar seccions amb tag + títol + intro.

Estructura HTML:

- `<div class="section-header">`
  - `<span class="section-tag">` - Tag de categoria
  - `<h2>` - Títol de la secció
  - `<p class="section-intro">` - Introducció opcional

Variants:

- `.section-header` (centrat, per defecte)
- `.section-header.left` (alineat a l'esquerra)

Quan usar-lo:

- Inici de cada secció important
- Quan vols estructurar visualment el contingut

---

### 2.3 RESULTATS CARDS (NOU)

Grid de cards per mostrar resultats, estadístiques o casos d'èxit.

Estructura HTML:

- `<section class="resultats-section">`
  - `<div class="container">`
    - `<div class="section-header">`
    - `<div class="resultats-grid">`
      - `<div class="resultat-card">`
        - `<div class="resultat-icon">` - Emoji o icona
        - `<div class="resultat-number">` - Número destacat
        - `<div class="resultat-text">` - Descripció

Quan usar-lo:

- Mostrar resultats numèrics
- Cases d'èxit
- Estadístiques impactants
- 2-4 resultats destacats

---

### 2.4 SERVEIS ASIMÈTRICS (NOU)

Layout alternat amb imatge i contingut, ideal per explicar serveis o processos.

Estructura HTML:

- `<section class="serveis-section">`
  - `<div class="container-fluid">`
    - `<div class="serveis-wrapper">`
      - `<div class="servei-block servei-left">` - Imatge a la dreta
        - `<div class="servei-content">`
          - `<span class="servei-number">01</span>`
          - `<h3>` - Títol
          - `<p>` - Descripció
          - `<ul class="servei-list">` - Llista d'items
          - `<p class="servei-highlight">` - Text destacat
        - `<div class="servei-image">`
          - `<img>` - Imatge
      - `<div class="servei-block servei-right">` - Imatge a l'esquerra
        - Mateix estructura però invertit

Components addicionals:

- `.plataformes-grid` - Grid 3 columnes per plataformes
  - `.plataforma-item` amb `.plataforma-icon`
- `.segmentacio-box` - Caixa amb tags
  - `.segmentacio-tags` amb `.tag`

Quan usar-lo:

- Explicar 2-4 serveis principals
- Mostrar processos alternats
- Quan tens imatges representatives

---

### 2.5 POTENCIEM CARDS (NOU)

Grid de 2 cards amb imatge superior i contingut inferior.

Estructura HTML:

- `<section class="potenciem-section">`
  - `<div class="container">`
    - `<div class="section-header centered">`
    - `<div class="potenciem-grid">`
      - `<div class="potenciem-card">`
        - `<div class="potenciem-visual">`
          - `<img>`
          - `<div class="visual-badge">` - Badge tipus "360°" o "AI"
        - `<div class="potenciem-info">`
          - `<h3>` - Títol
          - `<p>` - Descripció
          - Elements opcionals:
            - `<div class="benefits-list">` - Llista de beneficis
            - `<ul class="ia-list">` - Llista amb fletxes
            - `<div class="ia-cta-box">` - Caixa destacada

Quan usar-lo:

- Mostrar 2 valors diferencials
- Destacar tecnologies o eines
- Quan tens imatges impactants

---

### 2.6 TIMELINE (NOU)

Procés visual amb línia temporal i markers numerats.

Estructura HTML:

- `<section class="timeline-section">` o `.enfocament-section`
  - `<div class="container">`
    - `<div class="section-header">`
    - `<div class="timeline">`
      - `<div class="timeline-item">`
        - `<div class="timeline-marker">1</div>`
        - `<div class="timeline-content">`
          - `<h4>` - Títol del pas
          - `<p>` - Descripció

Quan usar-lo:

- Explicar processos de 3-7 passos
- Metodologies
- Fases d'un projecte
- Onboarding

---

### 2.7 FAQ ACCORDION (NOU)

Preguntes freqüents amb estil accordion modern.

Estructura HTML:

- `<section class="faq-section">`
  - `<div class="container">`
    - `<div class="section-header">`
    - `<div class="faq-accordion">`
      - `<div class="faq-item">`
        - `<div class="faq-question">`
          - `<span>` - Pregunta
          - `<span class="faq-icon">+</span>`
        - `<div class="faq-answer">`
          - `<p>` - Resposta

Quan usar-lo:

- Preguntes freqüents (3-5 preguntes)
- Dubtes comuns
- Aclariments sobre el servei

---

### 2.8 CTA FINAL (NOU)

Secció destacada amb crida a l'acció final abans del formulari.

Estructura HTML:

- `<section class="cta-final-section">`
  - `<div class="container">`
    - `<div class="cta-final-box">`
      - `<h2>` - Pregunta o títol
      - `<p>` - Text descriptiu
      - `<p class="cta-promise">` - Promesa destacada
      - `<div class="cta-buttons">`
        - `<a class="cta-primary">` - CTA principal
        - `<a class="cta-secondary">` - CTA secundari

Quan usar-lo:

- Abans del formulari
- Reforçar la crida a l'acció
- Quan vols múltiples opcions de contacte

---

### 2.9 FORMULARI (ACTUALITZAT)

**Versió nova (split layout):**

Estructura HTML:

- `<section class="form-service-immobiliari">` o `.form-service`
  - `<div class="container">`
    - `<div class="form-wrapper">`
      - `<div class="form-info">` - Columna esquerra amb info
        - `<h2>` - Títol
        - `<p>` - Descripció
        - `<div class="form-benefits">` - Beneficis
          - `<div class="form-benefit">`
            - `<span class="benefit-check">✓</span>`
            - `<span>` - Text benefici
      - `<div class="form-box">` - Columna dreta amb formulari
        - `<form>`
          - Camps del formulari (veure apartat 3)

**Versió antiga (compatible):**

Estructura HTML:

- `<section class="form-service">`
  - `<div class="container">`
    - `<div class="custom-adds-box">`
      - `<h2>` - Títol
      - `<p>` - Descripció
      - `<form>` - Formulari

---

### 2.10 COMPONENTS COMPATIBLES (ANTICS)

Mantinguts per compatibilitat amb landings existents:

**Text Simple:**

- `<section class="text">`

**Text + Imatge:**

- `<section class="text-img">`
  - `.grid` o `.grid.reverse`

**Grid 3/4:**

- `<section class="grid-3">` o `<section class="grid-4">`
  - `.grid` amb `.grid-item`

**Llistes:**

- `.numbered-list` - Llista numerada amb circles
- `.styled-list` - Llista amb checkmarks

---

## 3. FORMULARI DE CONTACTE (OBLIGATORI)

Tots els formularis han de seguir aquesta estructura:

### Camps ocults obligatoris:

```html
<input name="FullName" type="hidden" />
<input name="Email" type="hidden" />
<input name="Item_Origen_del_formulario" type="hidden" value="Landing-[NOM]" />
```

### Camps visibles mínims:

```html
<div class="form-group">
  <label for="Item_Nom">Nom *</label>
  <input
    class="form-control"
    id="Item_Nom"
    name="Item_Nom"
    required
    type="text"
  />
</div>

<div class="form-group">
  <label for="Item_Email">Email *</label>
  <input
    class="form-control"
    id="Item_Email"
    name="Item_Email"
    required
    type="email"
  />
</div>

<div class="form-group">
  <label for="Item_Message">Missatge</label>
  <textarea
    class="form-control"
    id="Item_Message"
    name="Item_Message"
    rows="5"
  ></textarea>
</div>

<div class="form-group form-checkbox">
  <input id="fmr_acceptinfo" name="fmr_acceptinfo" type="checkbox" required />
  <label for="fmr_acceptinfo">Accepto la política de privacitat *</label>
</div>

<button class="btn-submit" type="submit">Enviar</button>
```

### Elements de feedback:

```html
<div class="loader hide">
  <img
    src="https://panel.nubulus.es/Webs/nubulus.cat/Files/image/loaders/nubulus-loader.svg"
  />
</div>

<div class="alert alert-success hide">
  <h2>✓ Formulari enviat correctament!</h2>
  <p>Ens posarem en contacte amb tu en menys de 24 hores.</p>
</div>

<div class="alert alert-danger hide">
  <h2>✗ Error enviant el formulari</h2>
  <p>Si us plau, torna-ho a intentar o contacta'ns directament.</p>
</div>
```

### Atributs obligatoris del form:

- `action="/ca/forms/service/"` (canviar idioma si cal: `/es/`, `/en/`)
- `data-id="[UUID-VÀLID]"` (UUID únic per landing)
- `id="c"`
- `method="post"`

### Layout de 2 columnes (opcional):

```html
<div class="form-row">
  <div class="form-group">
    <!-- Camp 1 -->
  </div>
  <div class="form-group">
    <!-- Camp 2 -->
  </div>
</div>
```

---

## 4. BOTONS CTA

### Botons disponibles:

**CTA Primary (NOU - RECOMANAT):**

```html
<a class="cta-primary" href="#service-form">Text del botó</a>
```

- Fons blanc en hero gradient
- Fons gradient en seccions normals
- Hover amb elevació

**CTA Secondary (NOU):**

```html
<a class="cta-secondary" href="tel:+34XXX">Text del botó</a>
```

- Fons transparent amb border
- Hover amb fons sòlid

**Contact Button (Compatible):**

```html
<a class="contact-btn" href="#contacte">Text del botó</a>
```

- Estil anterior mantingut per compatibilitat

---

## 5. ESTILS CSS

### Classes obligatòries de Nubulus

**Contenidors:**

- `.adds-landing` - Contenidor principal (sempre)
- `.container` - Contenidor interior (amplada màxima 1200px)
- `.container-fluid` - Contenidor sense límit d'amplada

**Seccions:**

- `.gris` - Fons gris (alternar cada 2-3 seccions)
- `.blau` - Fons blau amb text blanc

**Utilitats:**

- `.text-left`, `.text-center`, `.text-right` - Alineació text
- `.mt-0` a `.mt-5` - Margins superiors (0 a 5rem)
- `.mb-0` a `.mb-5` - Margins inferiors (0 a 5rem)
- `.hide` - Ocultar element

### Variables CSS disponibles

De `root.css`:

- `--blau-p` - Blau principal (#2b4246)
- `--blau-s` - Blau secundari (#7fb9c6)
- `--blanc` - Blanc (#FFF)
- `--gris-fondo` - Gris de fons (#fafafa)
- `--gris-1` - Gris text (rgba(87, 87, 86, 1))

De `adds_landing.css`:

- `--gradient-primary` - Gradient blau principal
- `--gradient-secondary` - Gradient blau secundari
- `--shadow-sm` - Ombra petita
- `--shadow-md` - Ombra mitjana
- `--shadow-lg` - Ombra gran

### Convencions CSS

- Prefixar sempre: `.adds-landing .classe-especifica`
- No usar IDs per a CSS (només per anchors i formularis)
- Mobile-first: `clamp()` per tipografia fluida
- Responsivitat: `@media (max-width: 768px)` i `@media (max-width: 1024px)`
- Border-radius per defecte: 5px en imatges, variable segons component

### Generar CSS específic NOMÉS si:

- Hi ha elements únics no coberts per `adds-landing.css`
- Es necessiten colors o estils especials específics
- Casos excepcionals (la majoria NO necessita CSS custom)
- L'usuari especifica algo que no està en `adds-landing.css`

---

## 6. PROCÉS DETALLAT EN 5 PASSOS

### PAS 1: ANALITZAR MARKDOWN COMPLETAMENT

Quan rebis markdown:

1. **Identifica seccions** (separades per `---`)
2. **Determina tipus de cada secció:**
   - **Hero**: Primera secció amb `#` → Usar `.hero-gradient` (nou estil)
   - **Resultats numèrics**: 2-4 items amb números → Usar `.resultats-grid`
   - **Serveis/Processos**: 2-4 blocs amb descripcions → Usar `.servei-block`
   - **2 valors destacats**: Amb imatges → Usar `.potenciem-card`
   - **Procés/Timeline**: 3-7 passos → Usar `.timeline`
   - **FAQ**: Preguntes/respostes → Usar `.faq-accordion`
   - **Text simple**: Només text → Usar `.text` (compatible)
   - **Text + imatge**: Contingut amb imatge → Usar `.text-img` (compatible)

3. **Identifica elements especials:**
   - CTAs: `[text](#ancla)` → Usar `.cta-primary` o `.cta-secondary`
   - Llistes: `- item` → Usar `.styled-list` o integrar en component
   - Llistes numerades: `1. item` → Usar `.timeline` o `.numbered-list`
   - Èmfasi: `**text**` → `<strong>`
   - Imatges: `![alt](url)` → Integrar en components

### PAS 2: DECISIONS DE DISSENY

**Estructura general recomanada:**

1. Hero gradient (sempre)
2. Resultats o casos d'èxit (si aplica)
3. Serveis asimètrics (2-4 blocs)
4. Components específics (potenciem, timeline, etc.)
5. FAQ accordion
6. CTA final
7. Formulari (sempre)

**Alternància de fons:**

- Hero: gradient (no cal afegir classe)
- Seccions: alternar blanc → gris → blanc → gris
- Cada 2-3 seccions afegeix classe `.gris`
- CTA final: gradient (ja integrat)
- Formulari: gris (ja integrat)

**Imatges:**

- Si markdown té URL: `<img src="[URL]" alt="[ALT]" title="[TITLE]" loading="lazy" />`
- Si no: `<img src="" alt="[DESCRIPCIÓ]" />` (placeholder)
- Alt text sempre descriptiu amb paraules clau
- Title attribute amb paraules clau SEO
- Loading lazy per totes excepte primera visible

**Quan usar cada component:**

| Contingut                 | Component Recomanat      |
| ------------------------- | ------------------------ |
| 2-4 resultats amb números | `.resultats-grid`        |
| 2-4 serveis detallats     | `.servei-block`          |
| 2 valors amb imatge       | `.potenciem-grid`        |
| 3-7 passos d'un procés    | `.timeline`              |
| 3-5 preguntes freqüents   | `.faq-accordion`         |
| Text + explicació simple  | `.text` (compatible)     |
| Text + imatge alternats   | `.text-img` (compatible) |

### PAS 3: GENERAR HTML

**Estructura obligatòria:**

```html
<div class="adds-landing">
  <!-- 1. HERO GRADIENT -->
  <section class="hero-gradient">
    <div class="hero-overlay"></div>
    <div class="container">
      <div class="hero-content">
        <span class="hero-tag">Tag opcional</span>
        <h1 class="hero-title">Títol del markdown (primer #)</h1>
        <h2 class="hero-subtitle">Subtítol (primer ##)</h2>
        <p class="hero-text">Paràgrafs introductoris...</p>
        <div class="hero-features">
          <!-- Si hi ha llista de beneficis inicial -->
          <div class="hero-feature-item">
            <span class="feature-icon">✓</span>
            <span>Benefici</span>
          </div>
        </div>
        <a class="cta-primary" href="#service-form">CTA del markdown</a>
      </div>
    </div>
  </section>

  <!-- 2. SECCIONS INTERMITGES (segons anàlisi del PAS 1) -->

  <!-- Exemple: Resultats -->
  <section class="resultats-section">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">Tag opcional</span>
        <h2>Títol de la secció</h2>
        <p class="section-intro">Intro opcional</p>
      </div>
      <div class="resultats-grid">
        <!-- Cards de resultats -->
      </div>
    </div>
  </section>

  <!-- Exemple: Serveis -->
  <section class="serveis-section">
    <div class="container-fluid">
      <div class="serveis-wrapper">
        <!-- Blocs de servei alternats -->
      </div>
    </div>
  </section>

  <!-- Exemple: Timeline -->
  <section class="timeline-section">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">Procés</span>
        <h2>Com treballem</h2>
      </div>
      <div class="timeline">
        <!-- Items de timeline -->
      </div>
    </div>
  </section>

  <!-- 3. FAQ -->
  <section class="faq-section">
    <div class="container">
      <div class="section-header">
        <span class="section-tag">Dubtes</span>
        <h2>Preguntes freqüents</h2>
      </div>
      <div class="faq-accordion">
        <!-- Items FAQ -->
      </div>
    </div>
  </section>

  <!-- 4. CTA FINAL -->
  <section class="cta-final-section">
    <div class="container">
      <div class="cta-final-box">
        <h2>Pregunta o crida final</h2>
        <p>Text motivador</p>
        <p class="cta-promise"><strong>Promesa destacada</strong></p>
        <div class="cta-buttons">
          <a class="cta-primary" href="#service-form">CTA principal</a>
          <a class="cta-secondary" href="tel:+34XXX">CTA secundari</a>
        </div>
      </div>
    </div>
  </section>

  <!-- 5. FORMULARI (OBLIGATORI) -->
  <section class="form-service-immobiliari" id="service-form">
    <div class="container">
      <div class="form-wrapper">
        <div class="form-info">
          <h2>Contacta amb nosaltres</h2>
          <p>Descripció del formulari</p>
          <div class="form-benefits">
            <div class="form-benefit">
              <span class="benefit-check">✓</span>
              <span>Benefici 1</span>
            </div>
            <!-- Més beneficis -->
          </div>
        </div>

        <div class="form-box">
          <form
            action="/ca/forms/service/"
            data-id="[UUID]"
            id="c"
            method="post"
          >
            <!-- ESTRUCTURA COMPLETA DEL FORMULARI (veure apartat 3) -->
          </form>
        </div>
      </div>
    </div>
  </section>
</div>
```

**Regles HTML:**

- ✅ Comença amb `<div class="adds-landing">`
- ✅ NO incloure `<!DOCTYPE>`, `<html>`, `<head>`, `<body>`
- ✅ Comentaris HTML per identificar seccions
- ✅ HTML llest per copiar en CMS
- ✅ Tots els `<img>` amb `alt`, `title` i `loading="lazy"`
- ✅ Tots els enllaços amb text descriptiu

### PAS 4: CONVERSIÓ MARKDOWN → HTML

| Markdown               | HTML Component                                           |
| ---------------------- | -------------------------------------------------------- |
| `# Títol`              | `<h1 class="hero-title">` dins hero                      |
| `## Subtítol` (hero)   | `<h2 class="hero-subtitle">` dins hero                   |
| `## Subtítol` (secció) | `<h2>` dins `.section-header`                            |
| `### Subsecció`        | `<h3>` dins component                                    |
| `[Text](#ancla)`       | `<a class="cta-primary" href="#ancla">`                  |
| `- Item`               | Integrar en component o `<ul class="styled-list">`       |
| `1. Item`              | Usar `.timeline` o `.numbered-list`                      |
| `**Text**`             | `<strong>Text</strong>`                                  |
| `![Alt](url)`          | `<img src="url" alt="Alt" title="..." loading="lazy" />` |
| Paràgraf               | `<p>Paràgraf</p>` o `.hero-text` segons context          |

### PAS 5: GENERAR CSS (NOMÉS SI NECESSARI)

**La majoria de landings NO necessiten CSS específic.**

`adds_landing.css` ja conté tots els components nous.

**Generar CSS addicional NOMÉS si:**

- Elements únics no en `adds_landing.css`
- Colors especials fora de la paleta base
- Layouts excepcionals específics d'aquesta landing
- L'usuari demana explícitament algo no estàndard

**Format CSS (si necessari):**

```css
/* ==========================================================================
   LANDING: [Nom]
   Estils específics
   ========================================================================== */

.adds-landing .component-especific {
  /* Només estils que NO estan en adds_landing.css */
}

@media (max-width: 1024px) {
  .adds-landing .component-especific {
    /* Responsive tablet */
  }
}

@media (max-width: 768px) {
  .adds-landing .component-especific {
    /* Responsive mòbil */
  }
}
```

**Si NO necessita CSS específic:**

```
## 🎨 ARXIU CSS
⚠️ Aquesta landing NO necessita CSS específic.
Usa només estils de adds_landing.css
```

---

## 7. CHECKLIST FINAL ABANS DE LLIURAR

### ✅ ESTRUCTURA:

- [ ] Contenidor `.adds-landing` correcte
- [ ] Hero gradient amb `.hero-gradient` (nou estil)
- [ ] Totes les seccions dins `<section>` amb classe apropiada
- [ ] Tots els continguts dins `.container` o `.container-fluid`
- [ ] Alternància gris/blanc correcta (`.gris` cada 2-3 seccions)
- [ ] Section headers amb `.section-header` on sigui apropiat
- [ ] Components nous usats correctament segons tipus de contingut

### ✅ FORMULARI:

- [ ] `id="c"` present
- [ ] `data-id="[UUID]"` únic i vàlid
- [ ] `action="/ca/forms/service/"` correcte (idioma adaptat)
- [ ] Tots els camps ocults (FullName, Email, Item_Origen_del_formulario)
- [ ] Camps visibles mínims (Nom, Email, Missatge)
- [ ] Checkbox privacitat amb `required`
- [ ] Botó `.btn-submit` o `.btn-enviar`
- [ ] Loader, alert-success, alert-danger presents amb classe `.hide`
- [ ] Form wrapper amb `.form-info` i `.form-box` (nou estil)

### ✅ IMATGES:

- [ ] Totes les imatges tenen `alt` descriptiu
- [ ] Totes les imatges tenen `title` amb paraules clau
- [ ] `loading="lazy"` en totes les imatges excepte hero
- [ ] URLs completes i correctes
- [ ] Noms d'arxiu SEO-friendly (si són placeholders)

### ✅ BOTONS CTA:

- [ ] Usar `.cta-primary` per CTA principals (nou estil)
- [ ] Usar `.cta-secondary` per CTA secundaris (nou estil)
- [ ] Tots els CTAs apunten a `#service-form`
- [ ] Text dels botons és acció clara

### ✅ ESTILS:

- [ ] No styles inline en HTML
- [ ] No IDs per a CSS (només anchors/forms)
- [ ] Variables de root.css i adds_landing.css usades
- [ ] Responsivitat integrada en components
- [ ] CSS específic NOMÉS si realment necessari

### ✅ ACCESSIBILITAT:

- [ ] HTML5 semàntic (section, article, header, etc.)
- [ ] Alt text descriptiu en totes les imatges
- [ ] Title attributes en imatges i enllaços
- [ ] Labels associats a tots els inputs
- [ ] Contrast de colors adequat
- [ ] Font-weights correctes per jerarquia

### ✅ SEO:

- [ ] Alt texts amb paraules clau
- [ ] Titles amb paraules clau
- [ ] Noms d'imatge SEO-friendly
- [ ] Estructura H1 > H2 > H3 correcta
- [ ] Contingut rellevant i ben estructurat

---

## 8. RESTRICCIONS CRÍTIQUES

### ❌ NO fer MAI:

- ❌ NO usar `localStorage` / `sessionStorage` (no suportat)
- ❌ NO usar frameworks CSS externs (Bootstrap, Tailwind, etc.)
- ❌ NO usar styles inline en HTML
- ❌ NO usar IDs per estils CSS (només anchors i formularis)
- ❌ NO generar JavaScript complex (el CMS gestiona el form)
- ❌ NO ometre el formulari (sempre obligatori)
- ❌ NO crear JavaScript per el formulari (CMS ja ho fa)
- ❌ NO usar `<h1>` fora del hero (només un H1 per pàgina)
- ❌ NO generar `<!DOCTYPE>`, `<html>`, `<head>`, `<body>`

### ✅ Fer SEMPRE:

- ✅ Usar components de `adds_landing.css`
- ✅ HTML llest per copiar directament al CMS
- ✅ Formulari complet amb tots els camps
- ✅ Imatges amb alt, title i loading
- ✅ Estructura semàntica HTML5
- ✅ Mobile-first i responsive
- ✅ Validar UUID del formulari

---

## 9. OUTPUT FINAL

### Format de lliurament:

```
# LANDING GENERADA: [Nom del Servei]

## 📄 ARXIU HTML

[HTML complet des de <div class="adds-landing"> fins </div>]

## 🎨 ARXIU CSS

[CSS específic O avís de no necessari]

## 📋 NOTES

### ✅ Imatges pendents:
1. [nom-imatge-1.webp] - Descripció
2. [nom-imatge-2.webp] - Descripció

### ⚙️ Configuració del formulari:
- UUID: [UUID-del-formulari]
- Origen: Landing-[Nom]
- Action: /ca/forms/service/

### 🔧 Instruccions d'integració al CMS:
1. Copiar HTML complet
2. Afegir imatges als placeholders
3. IMPORTANT: Afegir crida a FormHome(); al JavaScript del CMS
4. Ordre dels CSS:
   - root.css
   - global.css
   - page.css
   - adds_landing.css
   - [landing-especific.css] (si cal)

### 📊 Components utilitzats:
- [Llistat de components nous usats]

### 🎯 Paraules clau principals:
- [Paraula clau 1]
- [Paraula clau 2]
```

---

## 10. FILOSOFIA NUBULUS

Principis de disseny a seguir:

1. **Modernitat visual** → Gradients, shadows, efectes hover
2. **Simplicitat estructural** → Components clars i reutilitzables
3. **Mobile-first** → Responsivitat des de mòbil
4. **Conversió orientada** → CTAs clars, formulari prominent
5. **Accessibilitat** → Semàntica HTML, contrastos, alt texts
6. **Modularitat** → Components independents combinables
7. **Consistència** → Mateixa paleta, tipografia, spacing
8. **Performance** → Lazy loading, CSS optimitzat
9. **SEO-friendly** → Alt texts, titles, estructura H
10. **User experience** → Hover effects, feedback visual

---

## ⚠️ PER A CLAUDE (LLEGIR SEMPRE)

Quan rebis una sol·licitud per generar una landing:

### 1. PREPARACIÓ

✅ Llegeix COMPLETAMENT aquesta guia actualitzada
✅ Identifica l'idioma (Català/Espanyol/Anglès)
✅ Verifica que tens el markdown complet

### 2. ANÀLISI

✅ Segueix EXACTAMENT els 5 passos (Apartat 6)
✅ Determina quins components nous usar
✅ Planifica l'estructura abans de generar

### 3. GENERACIÓ

✅ Usa components de `adds_landing.css` (nous i actualitzats)
✅ Hero gradient per defecte (no hero simple)
✅ Section headers amb tags
✅ Components moderns segons contingut
✅ Formulari amb layout nou (form-wrapper)
✅ CTAs amb `.cta-primary` / `.cta-secondary`

### 4. VERIFICACIÓ

✅ Revisa CHECKLIST complet (Apartat 7)
✅ Tots els components tenen les classes correctes
✅ Formulari complet amb UUID vàlid
✅ Imatges amb alt, title i loading

### 5. LLIURAMENT

✅ HTML + CSS (només si necessari) + NOTES
✅ Format de l'apartat 9
✅ Instruccions clares per integració

### El teu flux de treball:

```
Usuari proporciona MARKDOWN + IDIOMA + SERVEI
    ↓
✅ Llegeixo INSTRUCCIONS_SISTEMA.md actualitzades
    ↓
PAS 1: Analitzar markdown → identificar seccions i tipus
PAS 2: Decidir components → hero gradient + nous components
PAS 3: Generar HTML → estructura amb components nous
PAS 4: Conversió MD→HTML → taula d'equivalències
PAS 5: CSS → NOMÉS si absolutament necessari
    ↓
Verifico CHECKLIST (tots els punts)
    ↓
Lliuro: HTML + CSS (si cal) + NOTES detallades
```

### Prioritat de components:

**SEMPRE usar (nous):**

1. `.hero-gradient` (no `.hero`)
2. `.section-header` amb `.section-tag`
3. `.cta-primary` / `.cta-secondary` (no `.contact-btn`)
4. `.form-wrapper` amb split layout

**Usar segons contingut:**

- `.resultats-grid` → Resultats numèrics
- `.servei-block` → Serveis detallats
- `.potenciem-card` → 2 valors amb imatge
- `.timeline` → Processos
- `.faq-accordion` → Preguntes freqüents
- `.cta-final-section` → Abans del form

**Usar només si necessari (compatibles):**

- `.hero` → Només si usuari ho demana explícitament
- `.text`, `.text-img` → Si no encaixen components nous
- `.grid-3`, `.grid-4` → Si no encaixen components nous
- `.contact-btn` → Només per compatibilitat

### Restriccions crítiques a recordar:

- ❌ NO localStorage/sessionStorage MAI
- ❌ NO frameworks CSS externs
- ❌ NO styles inline
- ❌ NO IDs per a CSS
- ❌ NO ometre formulari
- ❌ NO generar DOCTYPE/html/head/body
- ✅ SÍ usar components nous per defecte
- ✅ SÍ hero gradient sempre
- ✅ SÍ section headers amb tags
- ✅ SÍ formulari amb form-wrapper

### Checklist ràpid abans de lliurar:

1. ✅ Hero gradient usat?
2. ✅ Components nous usats apropiadament?
3. ✅ Formulari complet amb UUID vàlid?
4. ✅ Imatges amb alt + title + loading?
5. ✅ CTAs amb classes noves?
6. ✅ CSS només si necessari?
7. ✅ NOTES amb instruccions completes?

---

**Aquesta guia actualitzada és la teva font de veritat. Sempre que no sàpigues algo, consulta aquí.**

**Versió:** 2.0 - Amb components moderns integrats
**Darrera actualització:** Components nous de hero-gradient, resultats-cards, serveis-asimètrics, potenciem-cards, timeline, FAQ accordion, CTA final i formulari split layout.
