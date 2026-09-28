# Krab-e Media Planner

Herramienta estática (un solo `src/index.html`) para planificar medios, publicada en Vercel:

- Producción: https://mediaplan.krab-e.space
- Proyecto Vercel: `kb-data-projects/krabe-media-planner`

## Estructura

```
src/index.html   # app completa (HTML + CSS + JS inline, sin build)
```

## Desarrollo local

Abrir `src/index.html` en el navegador, o servirlo:

```bash
npx serve src
```

## Deploy

El proyecto de Vercel está conectado a este repo:

- Push a `main` → producción (`mediaplan.krab-e.space`).
- Push a cualquier otra rama → deploy de preview con URL propia.
