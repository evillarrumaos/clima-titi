# Cómo publicar "Consulta del Clima by titi" (PWA gratis con https)

Esta carpeta ya es una **app web instalable (PWA)** lista para subir a un hosting estático
gratuito con **https**. Una vez publicada, la abrís en el celular desde cualquier lado,
funciona el **GPS** y se puede **instalar como app** con su ícono.

La página es estática y no tiene datos sensibles (solo consulta clima), por eso publicarla
es seguro.

## Archivos de la carpeta (subir TODOS juntos)
- `index.html` — la app
- `manifest.webmanifest` — datos de la app (nombre, íconos)
- `sw.js` — service worker (permite instalar / abrir sin conexión)
- `icon-192.png`, `icon-512.png`, `icon-maskable.png`, `apple-touch-icon.png` — íconos

---

## Opción A — Netlify Drop (lo más rápido, sin cuenta obligatoria)
1. Entrá a: https://app.netlify.com/drop
2. Arrastrá **toda la carpeta `clima-app`** a la ventana.
3. En segundos te da una URL https (ej. `https://algo-random.netlify.app`).
4. Abrí esa URL en el celular. Listo.
   - (Opcional) Creando una cuenta gratis podés renombrar la URL y que quede fija.

## Opción B — Cloudflare Pages (URL fija, cuenta gratis)
1. Creá cuenta gratis en https://pages.cloudflare.com
2. "Create a project" → "Direct Upload" → arrastrá la carpeta `clima-app`.
3. Te da una URL https fija (ej. `https://clima-titi.pages.dev`).

## Opción C — GitHub Pages (si ya usás GitHub)
1. Creá un repo, subí el contenido de `clima-app`.
2. Settings → Pages → Branch: main → carpeta raíz.
3. Te da `https://usuario.github.io/repo/`.

---

## Instalar como app en el celular

### iPhone (Safari)
1. Abrí la URL en **Safari**.
2. Tocá el botón **Compartir** (cuadrado con flecha).
3. **"Agregar a inicio"** → Agregar.
4. Queda el ícono ☀️☁️ en la pantalla. Se abre a pantalla completa.

### Android (Chrome)
1. Abrí la URL en **Chrome**.
2. Menú (⋮) → **"Instalar aplicación"** / "Agregar a pantalla principal".
3. Queda el ícono como app.

---

## GPS ("Mi ubicación")
- Con la app servida por **https**, el navegador va a **pedir permiso de ubicación**
  la primera vez. Aceptá y el GPS te ubica de verdad.
- Nota: el botón "Mi ubicación" se sacó de esta versión; si querés reactivarlo ahora
  que hay https, avisá y lo vuelvo a poner (esta vez sí funcionaría con GPS real).

## Actualizar la app más adelante
Si cambiás algo, volvé a subir la carpeta al mismo hosting. Además, subí el número de
versión en `sw.js` (línea `const CACHE = 'clima-titi-v1'` → `v2`, etc.) para que los
celulares tomen la versión nueva.
