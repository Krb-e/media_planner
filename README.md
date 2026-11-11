# Krab-e Media Planner

Herramienta estática (un solo `index.html`) para armar media plans de Paid Media y Email Marketing, publicada en Vercel:

- Producción: https://mediaplan.krab-e.space
- Proyecto Vercel: `kb-data-projects/krabe-media-planner`

Dos vistas en la misma app (pestañas de la barra superior):

- **Media plan mensual**: proyección de inversión por ACOS objetivo, por canal y por campaña
  (inversión, clics, sesiones, ventas, facturación), email marketing y branding fuera de ACOS.
- **Media plan para eventos**: eventos de pocos días (Cyber Monday, Hot Sale, Black Friday, Navidad u otro).
  Fecha de inicio y de finalización manuales, días fuertes opcionales, ponderación de inversión por día,
  media plan por campaña y día, sesiones y órdenes proyectadas, resto del mes y AdMedia fuera de ACOS.

## Planes guardados (7 días)

- **Guardar** deja el plan disponible 7 días desde el último guardado; después se borra solo.
- **Planes guardados** lista los planes vigentes para abrirlos o eliminarlos.
- Con el **código del equipo** los planes se guardan en Supabase (`krab-e-datawarehouse`, tabla `media_plans`)
  y los ve cualquier analista. Sin código o sin conexión quedan en el navegador (`localStorage`) con la misma vigencia.
- La tabla no tiene acceso directo para `anon`: solo se usa por las funciones `mp_list`, `mp_get`, `mp_save`
  y `mp_delete`, que validan el código (en la base se guarda solo su hash, en `mp_check`).
  Los planes vencidos se purgan en cada `mp_list`.
- El borrador en pantalla se sigue autoguardando en el navegador, como antes.

## Identidad visual

Sigue la skill `krab-e-branding`: fondo oscuro con grano, hero glass, naranja dosificado como único acento,
General Sans para datos y Bitroad para títulos. Los colores semánticos se usan solo para estado.
El exportado es un PDF A4 apaisado a sangre (botón **Exportar PDF** → imprimir del navegador, con
"Gráficos de fondo" activado).

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
