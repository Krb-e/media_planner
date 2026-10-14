# Krab-e Media Planner

Herramienta estática (un solo `index.html`) para planificar medios, publicada en Vercel:

- Producción: https://mediaplan.krab-e.space
- Proyecto Vercel: `kb-data-projects/krabe-media-planner`

Dos vistas en la misma app (se eligen con las pestañas de arriba):

- **Plan mensual**: proyección de inversión por ACOS objetivo.
- **Plan de evento (Cyber / Hot Sale / Black Friday)**: ventana por fases
  (Pre-Cyber · Cyber Monday · Cyber Week), ponderación de inversión por día,
  media plan por campaña y día, resto del mes y AdMedia fuera de ACOS.

## Estructura

```
index.html   # app completa (HTML + CSS + JS inline, sin build)
```

> `index.html` está en la raíz del repo y es el archivo que Vercel publica en `/`.

## Desarrollo local

Abrir `index.html` en el navegador, o servirlo:

```bash
npx serve .
```

## Deploy

El proyecto de Vercel está conectado a este repo:

- Push a `main` → producción (`mediaplan.krab-e.space`).
- Push a cualquier otra rama → deploy de preview con URL propia.
