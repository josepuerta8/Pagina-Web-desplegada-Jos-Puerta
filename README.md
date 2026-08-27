# Despliegue en Vercel — Perfil profesional de José Puerta

## Qué hay en esta carpeta

- `index.html` — tu página (con SEO ya integrado: título, meta description, Open Graph, Twitter Card y datos estructurados JSON-LD tipo Person).
- `og-image.jpg` — imagen que se muestra al compartir el enlace en WhatsApp, LinkedIn, Twitter/X, etc.
- `favicon-32.png`, `favicon-16.png`, `apple-touch-icon.png`, `icon-192.png`, `icon-512.png` — íconos de pestaña/dispositivo.
- `robots.txt` y `sitemap.xml` — para que Google pueda rastrear e indexar la página.
- `vercel.json` — cabeceras de caché y seguridad.

No necesitas build ni instalar nada: es un sitio 100% estático.

---

## Paso 1 — Subir esta carpeta a un repositorio de GitHub

1. Entra a [github.com/new](https://github.com/new) y crea un repositorio nuevo (por ejemplo `jose-puerta`), público o privado, sin plantilla (no marques "Add a README").
2. En tu computador, dentro de esta carpeta, ejecuta:

   ```bash
   git init
   git add .
   git commit -m "Perfil profesional de José Puerta"
   git branch -M main
   git remote add origin https://github.com/TU_USUARIO/jose-puerta.git
   git push -u origin main
   ```

   (Si prefieres no usar la terminal, también puedes arrastrar todos los archivos directamente en la página del repo en GitHub, en "uploading an existing file".)

## Paso 2 — Conectar el repo a Vercel

1. Entra a [vercel.com/new](https://vercel.com/new) con tu cuenta ya existente.
2. Elige **"Import Git Repository"** y selecciona el repo `jose-puerta` que acabas de crear (autoriza a Vercel a acceder a tu GitHub si es la primera vez).
3. En "Configure Project": Framework Preset = **Other** (sitio estático, sin build command ni output directory que definir).
4. Click **Deploy**. En menos de un minuto tendrás una URL tipo `https://jose-puerta.vercel.app` (o `jose-puerta-tuusuario.vercel.app` si el nombre corto ya está tomado).

Con el repo conectado, cada vez que hagas `git push` a `main`, Vercel vuelve a desplegar automáticamente.

## Paso 3 — Ajustar la URL real en los archivos SEO (importante)

Los archivos usan como marcador de posición `https://jose-puerta.vercel.app`. En cuanto Vercel te confirme tu URL final:

1. Abre `index.html` y reemplaza **todas** las apariciones de `https://jose-puerta.vercel.app` por tu dominio real (son ~10 apariciones: canonical, Open Graph, Twitter Card, JSON-LD, y el bloque de respaldo al final del archivo).
2. Haz lo mismo en `sitemap.xml` y `robots.txt`.
3. `git add . && git commit -m "Actualizar dominio" && git push` — Vercel redepliega solo.

*(Si prefieres, dime cuál quedó como tu URL final y te devuelvo los archivos ya actualizados.)*

## Paso 4 — Verificar que el SEO quedó bien

- **Google Search Console** ([search.google.com/search-console](https://search.google.com/search-console)): agrega tu dominio como propiedad, verifica (por meta tag o DNS), y en "Sitemaps" envía `https://tu-dominio/sitemap.xml`. Esto acelera que Google indexe la página.
- **Facebook Sharing Debugger** ([developers.facebook.com/tools/debug](https://developers.facebook.com/tools/debug/)) y **LinkedIn Post Inspector** ([linkedin.com/post-inspector](https://www.linkedin.com/post-inspector/)): pega tu URL para confirmar que la tarjeta (imagen + título + descripción) se ve bien al compartir.
- Prueba abrir la URL final en modo incógnito y revisa que todo cargue sin errores en la consola.

## Paso 5 (opcional) — Dominio propio

Si más adelante compras un dominio (ej. `josepuerta.com`), en Vercel: Project → Settings → Domains → Add, y sigue las instrucciones de DNS. Recuerda repetir el Paso 3 con el nuevo dominio.

---

### Sobre el SEO ya incluido

- **Título y meta description** optimizados para búsquedas como "José Puerta Director de Operaciones", "cadena de suministro Venezuela", etc.
- **Open Graph / Twitter Card** con imagen dedicada (`og-image.jpg`) para que el enlace se vea bien al compartirlo.
- **JSON-LD (schema.org/Person)** con cargo, empresa (Farmatodo Venezuela), ubicación (Caracas) y formación (Universidad de Carabobo) — ayuda a Google a entender que la página es tu perfil profesional.
- Pendiente: agregar tu **LinkedIn** al campo `sameAs` de los datos estructurados en cuanto me pases la URL — refuerza la señal de que ambos perfiles son la misma persona.
