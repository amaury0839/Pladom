# PLADOM — Sitio web (HTML estático)

Landing de Servicios PLADOM SRL. Un solo archivo (`index.html`) + carpeta `assets/` con el logo. Listo para GitHub Pages.

## Estructura
```
pladom-web/
├── index.html          ← la página
├── assets/             ← logo y favicon
│   ├── pladom-logo.png
│   ├── pladom-logo-white.png
│   └── favicon.png
└── README.md
```

## Desplegar en GitHub Pages (paso a paso)

1. Crea un repositorio nuevo en https://github.com/new (ej. `pladom-web`), público.
2. Sube **el contenido** de esta carpeta (que `index.html` quede en la raíz del repo, no dentro de otra carpeta). Puedes arrastrar los archivos en "Add file → Upload files".
3. En el repo: **Settings → Pages**.
4. En "Source" elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guarda.
5. Espera 1–2 minutos. Tu sitio quedará en `https://TU-USUARIO.github.io/pladom-web/`.

### Alternativa por terminal (si tienes git instalado)
```bash
cd pladom-web
git init
git add .
git commit -m "PLADOM landing"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/pladom-web.git
git push -u origin main
# luego activa Pages en Settings → Pages
```

## Conectar tu dominio pladom.com.do (opcional, después)
1. En **Settings → Pages → Custom domain** escribe `www.pladom.com.do` y guarda (esto crea un archivo `CNAME` en el repo).
2. En tu proveedor de DNS agrega un registro **CNAME**: `www` → `TU-USUARIO.github.io`.
3. Para el dominio raíz (`pladom.com.do`) agrega los registros **A** de GitHub Pages:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
4. Marca **Enforce HTTPS** cuando GitHub lo permita.
> Ojo: apuntar el dominio a GitHub lo desconecta de Wix. Hazlo solo cuando estés seguro.

## Pendientes antes de publicar en serio
- Reemplazar las fotos de stock (hero y "Nosotros" usan imágenes de Unsplash) por fotos reales de tu equipo.
- Confirmar el modelo del 32' (Genie 3246 vs 3232).
- Agregar precios/tarifas si quieres filtrar curiosos.
- Poner el RNC en el pie de página (está como `[agregar RNC]`).
