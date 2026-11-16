# Presentaciones — sitio estático público

Cada carpeta es una presentación. Se publica con `publicar <carpeta>` y queda en:

    https://jennas-tech.github.io/presentaciones/<carpeta>/

## Reglas

- **Vitrina curada, no espejo.** Esto NO es `~/workspace`. Solo entra lo que se decide publicar.
- Un `index.html` por carpeta. Sin build, sin dependencias externas: si el navegador no lo
  puede abrir solo, no va.
- **Sin video.** Texto, imágenes, diagramas, audio corto. El video pesa y el tope de cortesía
  de GitHub es 1 GB por repo.
- Las carpetas que empiezan con `_` o `.` no se publican ni aparecen en el índice.
  Para armar una nueva, copiar `demo/` como punto de partida: ya trae el CSS, la navegación
  con flechas y la vista de impresión resueltas.

## Uso

    publicar --lista              # qué está publicado y con qué link
    publicar hidraulica           # publica ~/publicar/hidraulica/
    publicar --revisado hidraulica # se salta el guardián (solo tras revisar a mano)

## Guardián

Antes de cada `git push` se escanea la carpeta buscando rutas del equipo (`/home/tavo`),
correos, tokens (`ghp_`, `sk-`, `AKIA`), `chat_id`, IPs de la LAN y archivos `*.env`,
`*.key`, `*.pem`, `*.gpg`. Si encuentra algo, **aborta**.

Motivo: `publicar` es la única acción irreversible de todo el sistema. Un archivo publicado
queda cacheado y copiado; no hay "deshacer" que valga.

## Privacidad

Las páginas llevan `<meta name="robots" content="noindex">` y el repo es público (GitHub Pages
gratis lo exige). O sea: **la URL es oscura, no secreta.** Cualquiera con el link entra, y
quien tenga el link puede pasarlo. Adecuado para material de trabajo; no para datos personales.

## Si algún día se quiere dominio propio

`presentaciones.economico.cl` con Cloudflare Pages (subida directa, sin repo, sin tope de
banda ancha). Se eligió GitHub Pages primero porque no exige cuenta nueva.
