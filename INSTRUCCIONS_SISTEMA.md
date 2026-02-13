# INSTRUCCIONS - Generador de Landings Adds Nubulus

## Objectiu

Generar automàticament landings HTML+CSS a partir de markdown estructurat, mantenint estil visual consistent de Nubulus.

---

## 1. ESTRUCTURA DEL MARKDOWN D'ENTRADA

```markdown
# Títol Principal Landing

## Subtítol (tagline)

Paragraf introductori.
Podem ser varis.

[CTA Text](#contacte)

---

## Seccio 1

Contingut amb listes o text.

- Item 1
- Item 2

---

## Seccio 2

Més contingut...
```

### Regles de format:

- `# Títol` = Inici del HERO o seccio principal
- `## Subtítol` = Tagline del hero o títol de seccio
- `---` = Separador (nova seccio visual)
- `### Subseccio` = Subtítol dins seccio
- `[Text](#ancla)` = CTA/enllaç
- `- Item` = Llista amb viñetes
- `1. Item` = Llista numerada
- Paragraf = Text normal

---

## 2. COMPONENTS OBLIGATORIS

### Hero Section (primera seccio)

```html
<section class="hero">
  <div class="container">
    <h2>Subtítol del markdown</h2>
    <p>Paragraf introductori</p>
    <a class="contact-btn" href="#contacte">CTA</a>
  </div>
</section>
```

⚠️ NO generar `<h1>` (ja ve del CMS)

### Seccions Intermedies (segons tipus)

- **Text simple**: Para seccions només text
- **Text-img**: Seccio 2 columnes (text + imatge)
- **Grid-3/4**: 3-4 items similars amb títol
- **Styled-list**: Llistes estilitzades

### Formulari de Contacte (al final)

```html
<section class="form-service">
  <div class="container">
    <div class="custom-adds-box" id="service-form">
      <h2>Contacta amb nosaltres</h2>
      <form
        action="/ca/forms/service/"
        data-id="[UUID-UNIC]"
        id="c"
        method="post"
      >
        <!-- Camps ocults -->
        <input name="FullName" type="hidden" />
        <input name="Email" type="hidden" />
        <input
          name="Item_Origen_del_formulario"
          type="hidden"
          value="[NOM-LANDING]"
        />

        <!-- Camps visibles -->
        <div class="form-group">
          <label for="Item_Nom">Nom</label>
          <input
            class="form-control"
            id="Item_Nom"
            name="Item_Nom"
            required
            type="text"
          />
        </div>

        <div class="form-group">
          <label for="Item_Email">Email</label>
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
            rows="4"
          ></textarea>
        </div>

        <div class="form-group">
          <input
            id="fmr_acceptinfo"
            name="fmr_acceptinfo"
            type="checkbox"
            required
          />
          <label for="fmr_acceptinfo">Accepto la política de privacitat</label>
        </div>

        <button class="btn-enviar" type="submit">Enviar</button>

        <div class="loader hide">
          <img
            src="https://panel.nubulus.es/Webs/nubulus.cat/Files/image/loaders/nubulus-loader.svg"
          />
        </div>

        <div class="alert alert-success hide">
          <h2>Formulari enviat correctament!</h2>
        </div>

        <div class="alert alert-danger hide">
          <h2>Error enviant el formulari</h2>
        </div>
      </form>
    </div>
  </div>
</section>
```

---

## 3. ESTRUCTURA FINAL DE LA LANDING

```html
<div class="adds-landing">
  <!-- Hero -->
  <!-- Seccions intermedies -->
  <!-- Formulari -->
</div>
```

⚠️ **IMPORTANT**:

- NO incluir `<!DOCTYPE>`, `<html>`, `<head>`, `<body>`
- HTML llist per copiar en CMS

---

## 4. ESTILS CSS

### Classes obligatorios de Nubulus

- `.adds-landing` = Contenidor principal
- `.container` = Contenidor interior
- `.hero` = Seccio hero
- `.text` = Seccio text simple
- `.text-img` = Seccio text + imatge (2 columnes)
- `.grid-3` = Grid 3 items
- `.grid-4` = Grid 4 items
- `.gris` = Fons gris (alternar cada 2-3 seccions)
- `.contact-btn` = Botó CTA
- `.form-adds` = Seccio formulari

### Convencions CSS

- Prefixar sempre: `.adds-landing .classe-especifica`
- No IDs per a CSS (només per a anchors i formularis)
- Variables de `root.css`: `--blau-p`, `--blau-s`, `--blanc`, etc.
- Estils globals de tota la web de Nubulus en `global.css`, estils específics de landings en `adds-landing.css`
- Estils que canvien elements pares generats per CMS de la pagina en arxiu `page.css`
- Mobile-first: `clamp()` per a tipografia fluida
- Responsivitat: `@media (max-width: 768px)`
- Border-radius per defecte: 5px en imatges

### Generar CSS específic NOMÉS si:

- Hi ha elements únics no coberts per `adds-landing.css`
- Es necessiten colors o estils especials específics
- Casos excepcionals (la majoría no necessita CSS custom)
- Al menos que el usuari especiqui algo que no esta en `adds-landing.css`

---

## 5. PROCÉS DETALLAT EN 5 PASSOS

### PAS 1: ANALITZAR MARKDOWN COMPLETAMENT

Quant rebis markdown:

1. **Identifica seccions** (separades per `---`)
2. **Determina tipus de cada seccio:**
   - **Hero**: Primera seccio amb `#`
   - **Text**: Només paragraf i spans
   - **Text-img**: Contingut que demana imatge
   - **Grid-3/4**: 3-4 items similars
   - **Numbered-list**: Llista numerada
   - **Styled-list**: Llista amb viñetes

3. **Identifica elements especials:**
   - CTAs: `[text](#ancla)`
   - Llistes: `- item` o `1. item`
   - Énfasi: `**text**`
   - Imatges: `![alt](url)`

### PAS 2: DECISIONS DE DISSENY

**Alternancia de fons:**

- Hero: sense fons (blanc)
- Seccions alternen: blanc→gris→blanc→gris
- Cada 2-3 seccions afegeix classe `.gris`

**Imatges:**

- Si markdown te URL: `<img src="[URL]" />`
- Si no: `<img src="" />` (placeholder)
- Alt text sempre descriptiu

**Layouts segons quantitat d'items:**

- 3-4 items similars → `.grid-3` o `.grid-4`
- Text + imatge → `.text-img`
- Només text → `.text`

### PAS 3: GENERAR HTML

**Estructura obligatoria:**

```html
<div class="adds-landing">
  <!-- 1. HERO (primera secció) -->
  <section class="hero">
    <div class="container">
      <h2>Subtítol del markdown</h2>
      <p>Paragrafes introductoris...</p>
      <a class="contact-btn" href="#service-form">CTA Principal</a>
    </div>
  </section>

  <!-- 2. SECCIONS INTERMITGES (segons anàlisis) -->

  <!-- Exemple secció text -->
  <section class="text gris">
    <div class="container">
      <h2>Títol secció</h2>
      <p>Paragrafes...</p>
    </div>
  </section>

  <!-- Exemple secció grid-3 -->
  <section class="grid-3">
    <div class="container">
      <h2>Títol secció</h2>
      <div class="grid-items">
        <article>
          <h3>Item 1</h3>
          <p>Contingut...</p>
        </article>
        <article>
          <h3>Item 2</h3>
          <p>Contenido...</p>
        </article>
        <article>
          <h3>Item 3</h3>
          <p>Contenido...</p>
        </article>
      </div>
    </div>
  </section>

  <!-- Exemple secció text-img -->
  <section class="text-img gris">
    <div class="container">
      <div class="content">
        <h2>Títol</h2>
        <p>Paragrafes...</p>
      </div>
      <div class="image">
        <img alt="Descripció" src="" />
      </div>
    </div>
  </section>

  <!-- 3. FORMULARI AL FINAL -->
  <section class="form-service">
    <div class="container">
      <div class="custom-adds-box" id="service-form">
        <h2>Contacta amb nosaltres</h2>
        <form
          action="/ca/forms/service/"
          data-id="[UUID-ÚNIC]"
          id="c"
          method="post"
        >
          <!-- Camps ocults -->
          <input name="FullName" type="hidden" />
          <input name="Email" type="hidden" />
          <input
            name="Item_Origen_del_formulario"
            type="hidden"
            value="Landing-[NOM]"
          />

          <!-- Camps visibles -->
          <div class="form-group">
            <label for="Item_Nom">Nom</label>
            <input
              class="form-control"
              id="Item_Nom"
              name="Item_Nom"
              required
              type="text"
            />
          </div>

          <div class="form-group">
            <label for="Item_Email">Email</label>
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
              rows="4"
            ></textarea>
          </div>

          <div class="form-group">
            <input
              id="fmr_acceptinfo"
              name="fmr_acceptinfo"
              type="checkbox"
              required
            />
            <label for="fmr_acceptinfo"
              >Accepto la política de privacitat</label
            >
          </div>

          <button class="btn-enviar" type="submit">Enviar</button>

          <div class="loader hide">
            <img
              src="https://panel.nubulus.es/Webs/nubulus.cat/Files/image/loaders/nubulus-loader.svg"
            />
          </div>

          <div class="alert alert-success hide">
            <h2>Formulari enviat correctament!</h2>
          </div>

          <div class="alert alert-danger hide">
            <h2>Error enviant el formulari</h2>
          </div>
        </form>
      </div>
    </div>
  </section>
</div>
```

**Regles HTML:**

- ✅ Comença amb `<div class="adds-landing">`
- ✅ NO incloure `<!DOCTYPE>`, `<html>`, `<head>`, `<body>`
- ✅ Comentaris per identificar seccions
- ✅ HTML llest per copiar en CMS

### PAS 4: CONVERSIÓ MARKDOWN → HTML

| Markdown         | HTML                                            |
| ---------------- | ----------------------------------------------- |
| `# Títol`        | No generar (solo hero)                          |
| `## Subtítol`    | `<h2>Subtítol</h2>`                             |
| `### Subsecció`  | `<h3>Subsecció</h3>`                            |
| `[Text](#ancla)` | `<a class="contact-btn" href="#ancla">Text</a>` |
| `- Item`         | `<ul><li>Item</li></ul>`                        |
| `1. Item`        | `<ol><li>Item</li></ol>`                        |
| `**Text**`       | `<strong>Text</strong>`                         |
| `![Alt](url)`    | `<img alt="Alt" src="url" />`                   |
| Paràgraf         | `<p>Paràgraf</p>`                               |

### PAS 5: GENERAR CSS (NOMÉS SI NECESSARI)

**Generar CSS adicional NOMÉS si:**

- Elements únics no en `adds-landing.css`
- Colors especials fora de la paleta base
- Layouts excepcionals

**Format CSS:**

```css
/* ==========================================================================
   LANDING: [Nom]
   Estils específics
   ========================================================================== */

.adds-landing .seccion-especial {
  /* Només estils que NO estan en adds-landing.css */
}

@media (max-width: 768px) {
  .adds-landing .seccion-especial {
    /* Responsiu */
  }
}
```

**Si NO necessita CSS específic:**

```
## 🎨 ARXIU CSS
⚠️ Aquesta landing NO necessita CSS específic.
Usa només estils de adds-landing.css
```

---

## 6. PROCÉS DE GENERACIÓ

1. **Analitzar markdown** → Estructura, tipus seccions, elements especials
2. **Decidir disseny** → Components, alternancia color, posició imatges
3. **Generar HTML** → HTML5 semàntic, classes Nubulus, estructura correcta
4. **Generar CSS** → NOMÉS si necessari, específic d'aquesta landing
5. **Verificar** → HTML vàlid, formulari complet, checklist final

---

## 7. CHECKLIST FINAL ANTES DE ENTREGAR

✅ **ESTRUCTURA:**

- [ ] Contenidor `.adds-landing` correcte
- [ ] Hero section amb h2 + contingut + CTA
- [ ] Totes les seccions dins `<section>`
- [ ] Totes els continguts dins `.container`
- [ ] Alternancia gris/blanc correcta

✅ **FORMULARI:**

- [ ] `id="c"` i `data-id` únic
- [ ] `action="/ca/forms/service/"` correcte (idioma)
- [ ] Tots els camps ocults (FullName, Email, Item_Origen_del_formulario)
- [ ] Tots els camps visibles (Nom, Email, Missatge mínima)
- [ ] Checkbox privacitat amb `required`
- [ ] Botó `.btn-enviar`
- [ ] Loader, alert-success, alert-danger presents

✅ **ESTILOS:**

- [ ] No styles inline
- [ ] No IDs per a CSS
- [ ] Variables de root.css usades
- [ ] Responsivitat correcta

✅ **ACCESIBILITAT:**

- [ ] HTML semàntic
- [ ] Alt i title en imatges
- [ ] Font-weight contrastos correctes
- [ ] Labels associats a inputs

---

## 8. RESTRICCIONS

❌ NO usar localStorage/sessionStorage
❌ NO usar frameworks CSS externs
❌ NO usar estilos inline en HTML
❌ NO usar IDs per estils (només anchors/forms)
❌ NO generar JavaScript complex
❌ NO omitir formulari
❌ NO crear JabaScript per el formulari, el CMS ja el gestiona.

---

## 9. OUTPUT FINAL

**2 ARXIUS per landing:**

1. `landing-[nom].html`
   - HTML complet (sense DOCTYPE/head/body)
   - JavaScript incluido
   - Llist per copiar en CMS

2. `landing-[nom].css` (OPCIONAL)
   - Només si necessita estilos específics
   - Si no necessita, avisa: "Usa només adds-landing.css"

**+ NOTES:**

- Llist imatges pendents
- Configuració formulari (UUID, origin)
- Si el UUID del formulari no es valid no funcionara correctament, no es necesari generar un UUID per cada landing es pot fer servir el mateix per totes, pero ha de ser un UUID valid (ex: `123e4567-e89b-12d3-a456-426614174000`)
- Instruccions especials per CMS perque el formulari funcioni correctament a la part de JS del CMS cal afegir una crida a la funcio de `FormHome();`.
- Arxius CSS necessaris en ordre
- Instruccions integració CMS

---

## 10. FILOSOFIA NUBULUS

1. **Simplicitat visual** → Diseño net, sense excés
2. **Mobile-first** → Responsivitat desde mobile
3. **Conversio orientada** → CTAs clars, formulari prominent
4. **Accesibilidad** → Semantica HTML, contrasts
5. **Modularitat** → Components reutilizables
6. **Consistència** → Mateixa paleta color, tipografia

---

## ⚠️ PER A CLAUDE (LLEGIR SEMPRE)

Quant rebis una sol·licitud per generar una landing:

1. **Llegeix COMPLETAMENT aquesta guia (INSTRUCCIONS_SISTEMA.md)**
2. **Segueix EXACTAMENT l'estructura de 5 passos (Secció 5)**
3. **Usa NOMÉS les classes Nubulus definides (Secció 4)**
4. **Verifica el CHECKLIST abans de lliurar (Secció 7)**
5. **Genera 2 arxius: HTML + CSS (opcional)**

### El teu flux de treball:

```
Usuari proporciona MARKDOWN
    ↓
✅ Llegeixo INSTRUCCIONS_SISTEMA.md
    ↓
PAS 1: Analitzar markdown → tipus de seccions
PAS 2: Decidir disseny → alternancia gris/blanc, layouts
PAS 3: Generar HTML → estructura obligatoria completa
PAS 4: Conversió MD→HTML → taula d'equivalències
PAS 5: Generar CSS → NOMÉS si necessari
    ↓
Verifico CHECKLIST
    ↓
Lliuro: HTML + CSS (si aplica) + NOTES
```

### Restriccions crítiques:

- ❌ NO localStorage/sessionStorage
- ❌ NO frameworks CSS externs
- ❌ NO estils inline
- ❌ NO IDs per a CSS
- ❌ NO omitir formulari MAI

### Output esperat:

```
# LANDING GENERADA: [Nom]

## 📄 ARXIU HTML
[HTML complet des de <div class="adds-landing"> fins </div>]

## 🎨 ARXIU CSS
[CSS específic O avís de no necessari]

## 📋 NOTES
[Imatges pendents, configuració, instruccions]
```

---

**Aquesta guia és la teva font de veritat. Sempre que no sapigues algo, consulta aquí.**
