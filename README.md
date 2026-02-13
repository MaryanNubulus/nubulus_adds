# Generador de Landings Adds Nubulus

Sistema per generar automàticament landings HTML+CSS a partir de markdown estructurat, mantenint l'estil visual consistent de Nubulus.

## Descripció

Aquest projecte conté els estils i les instruccions per crear landings de serveis per a Nubulus de manera automatitzada. Les landings es generen a partir d'un format markdown estructurat i es converteixen en HTML+CSS llest per integrar al CMS.

## Estructura del Projecte

```
nubulus_adds/
├── css/
│   ├── root.css           # Variables CSS globals
│   ├── global.css         # Estils globals de la web
│   ├── page.css          # Estils específics de pàgina
│   └── adds_landing.css  # Estils específics per landings
├── INSTRUCCIONS_SISTEMA.md  # Guia completa de generació
├── PROMPT_COMPLETO.md       # Prompt per a l'assistant
└── README.md
```

## Components

### Arxius CSS

- **root.css**: Variables de color, tipografia i altres valors globals
- **global.css**: Estils globals que s'apliquen a tota la web Nubulus
- **page.css**: Estils que modifiquen elements pares generats pel CMS
- **adds_landing.css**: Estils específics per a les landings de serveis

### Documentació

- **INSTRUCCIONS_SISTEMA.md**: Guia completa pas a pas per generar landings
- **PROMPT_COMPLETO.md**: Prompt optimitzat per a assistents AI

## Funcionament

1. Es proporciona un markdown estructurat amb el contingut
2. El sistema analitza l'estructura i identifica els components
3. Es genera HTML semàntic amb les classes de Nubulus
4. Es crea CSS específic només si és necessari
5. S'integra al CMS de Nubulus

## Components de les Landings

Cada landing conté:

- **Hero Section**: Títol principal, subtítol i CTA
- **Seccions Intermitges**: Text, text+imatge, grids, llistes
- **Formulari de Contacte**: Formulari integrat amb el sistema Nubulus

## Característiques

- Mobile-first i completament responsiu
- HTML semàntic i accessible
- Integració directa amb el CMS Nubulus
- Sistema modular de components reutilitzables
- Alternància automàtica de fons gris/blanc
- Formularis amb validació integrada

## Ús

Consulta el fitxer [INSTRUCCIONS_SISTEMA.md](INSTRUCCIONS_SISTEMA.md) per a la guia completa de com generar landings.

## Filosofia Nubulus

1. **Simplicitat visual**: Disseny net sense excés
2. **Mobile-first**: Responsivitat des de mobile
3. **Orientat a conversió**: CTAs clars i formulari prominent
4. **Accessibilitat**: Semàntica HTML i bons contrastos
5. **Modularitat**: Components reutilitzables
6. **Consistència**: Paleta de color i tipografia uniforme

## Integració CMS

Les landings generades són fragments HTML que s'integren directament al CMS de Nubulus sense necessitat de `<!DOCTYPE>`, `<html>`, `<head>` o `<body>`.

## Notes Tècniques

- No s'utilitza localStorage/sessionStorage
- No s'utilitzen frameworks CSS externs
- No s'utilitzen estils inline
- Els IDs només s'usen per anchors i formularis, no per CSS
- El formulari s'integra amb el sistema de forms de Nubulus

## Autor

NUBULUS
