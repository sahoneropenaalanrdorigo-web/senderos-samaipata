# Laboratorio 14 — ¡Publicado en internet! Git, GitHub y GitHub Pages

Al terminar este laboratorio tu sitio tendrá una dirección pública, por ejemplo:
`https://TU-USUARIO.github.io/senderos-samaipata/`, que podrás mandar por WhatsApp a quien quieras.

## Antes de empezar
- Cuenta en github.com (con tu correo institucional puedes pedir GitHub Education, gratis).
- Git instalado: en la terminal de VS Code, `git --version`.
- Configura tu identidad (una sola vez):
  ```
  git config --global user.name "Tu Nombre"
  git config --global user.email "tu-correo@ejemplo.com"
  ```

## Paso 1 — Preparar la carpeta
1. Completa `.gitignore` (¡la carpeta `img/originales/` pesa 12 MB y NO se publica!).
2. Agrega `.gitattributes` con `* text=auto eol=lf` (evita las advertencias LF/CRLF de Windows).
3. Crea un archivo vacío llamado `.nojekyll` (GitHub Pages publicará tus archivos tal como están).
4. Completa `README.md` con tu usuario y tu nombre.

## Paso 2 — Tu primer repositorio
```
git init -b main
git add .
git status          ← revisa: ¿aparece img/originales? (no debería)
git commit -m "Primera versión del sitio de Senderos Samaipata"
```

## Paso 3 — Subir a GitHub
Crea en github.com un repositorio **público** llamado `senderos-samaipata` (sin README) y sigue las instrucciones
"…or push an existing repository":
```
git remote add origin https://github.com/TU-USUARIO/senderos-samaipata.git
git push -u origin main
```

## Paso 4 — Encender GitHub Pages
En el repositorio: **Settings > Pages > Build and deployment > Source: Deploy from a branch > main / (root) > Save**.
Espera 1-2 minutos y abre `https://TU-USUARIO.github.io/senderos-samaipata/`.

## Paso 5 — Poner la dirección real en el sitio (segundo commit)
Reemplaza `https://senderossamaipata.bo/` por tu URL de GitHub Pages en: `canonical` de las 6 páginas, `sitemap.xml`,
`robots.txt`, las metas Open Graph y el JSON-LD. En `404.html` agrega `<base href="/senderos-samaipata/">`.
```
git add .
git commit -m "Usar la URL publicada en canonical, sitemap y Open Graph"
git push
```

## Paso 6 — Probar en el mundo real
- Abre el sitio en tu celular con datos móviles y compártelo por WhatsApp (¿aparece la tarjeta con la foto?).
- Abre `https://TU-USUARIO.github.io/senderos-samaipata/no-existe.html`: debe verse TU página 404 con estilos.
- PageSpeed Insights (pagespeed.web.dev) con tu URL: compara con tu informe de la clase 13.

## Alternativa: Netlify
netlify.com > Add new site > Deploy manually > arrastra la carpeta. En segundos tienes `algo.netlify.app`.
Bonus Netlify: con el atributo `data-netlify="true"` en el formulario de reserva y `method="post"`, las reservas
llegan de verdad a tu panel de Netlify (sin programar un servidor).
