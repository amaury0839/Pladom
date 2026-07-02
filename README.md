# PLADOM — Sitio web (HTML estático)

Landing de Servicios PLADOM SRL. Sitio estático de un solo archivo (`public/index.html`)
más la carpeta `public/assets/` con el logo y el favicon. Listo para desplegar en
**Cloudflare Pages**.

## Estructura

```
pladom/
├── public/                 ← carpeta que se publica (build output)
│   ├── index.html          ← la página
│   ├── _headers            ← cabeceras de seguridad y caché (Cloudflare)
│   └── assets/             ← logo y favicon
│       ├── pladom-logo.png
│       ├── pladom-logo-white.png
│       └── favicon.png
├── wrangler.toml           ← configuración de Cloudflare Pages
├── .gitignore
└── README.md
```

No hay paso de build: Cloudflare sirve directamente el contenido de `public/`.

## Desplegar en Cloudflare Pages

### Opción A — Conectando el repositorio de GitHub (recomendada)

1. Entra en el [panel de Cloudflare](https://dash.cloudflare.com/) → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
2. Autoriza y elige este repositorio.
3. Configura el build así:
   - **Framework preset:** `None`
   - **Build command:** *(déjalo vacío)*
   - **Build output directory:** `public`
4. Pulsa **Save and Deploy**. En ~1 minuto tendrás una URL `https://pladom-web.pages.dev`.
5. Cada `git push` a la rama de producción vuelve a desplegar automáticamente.

### Opción B — Desde la terminal con Wrangler

```bash
# 1. Instala Wrangler (solo la primera vez)
npm install -g wrangler

# 2. Inicia sesión en Cloudflare
wrangler login

# 3. Despliega (usa public/ definido en wrangler.toml)
wrangler pages deploy
```

## Conectar tu dominio pladom.com.do

1. En el proyecto de Pages: **Custom domains** → **Set up a domain** → escribe `pladom.com.do`
   (y repite para `www.pladom.com.do`).
2. Si el dominio ya está en Cloudflare, los registros DNS se crean solos.
   Si no, mueve el DNS del dominio a Cloudflare o crea un **CNAME** apuntando a
   `pladom-web.pages.dev`.
3. Cloudflare gestiona el certificado HTTPS automáticamente.

> Ojo: apuntar el dominio a Cloudflare lo desconecta de Wix. Hazlo solo cuando estés seguro.

## Pendientes antes de publicar en serio

- Reemplazar las fotos de stock (hero y "Nosotros" usan imágenes de Unsplash) por fotos reales de tu equipo.
- Confirmar el modelo del 32' (Genie 3246 vs 3232).
- Agregar precios/tarifas si quieres filtrar curiosos.
- Poner el RNC en el pie de página (está como `[agregar RNC]`).
