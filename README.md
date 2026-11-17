# Site do Dr. Ygor Dantas

Site estático (HTML, CSS e JS num único `index.html`), sem build. Movimento com GSAP 3.12.5 + ScrollTrigger e Lenis 1.1.13, servidos de `/vendor`.

## Rodar localmente

Na pasta do projeto:

```
npx serve .
```

ou, com Python:

```
python -m http.server 8080
```

e abra http://localhost:8080 (os caminhos começam com `/`, então abra por um servidor, não clicando duas vezes no arquivo).

## Estrutura

- `index.html`: página inteira, com CSS e JS embutidos
- `img/`: fotos em webp (800 e 1600px; recorte do Sobre em 700 e 1200px) e a logo em PNG com transparência
- `fonts/`: Archivo e IBM Plex Sans (Google Fonts, servidas localmente)
- `vendor/`: GSAP, ScrollTrigger e Lenis em versões fixas
- `favicon.svg`, `apple-touch-icon.png`, `og-image.jpg`
- `vercel.json`: cleanUrls e cache longo para img, fonts e vendor

## Trocar uma foto

Substitua o arquivo em `img/` mantendo o mesmo nome (por exemplo `01-hero-COM-FUNDO-1600.webp`). Se a proporção mudar, atualize `width` e `height` na tag `<img>`.

## Publicar

Cada push na branch `main` publica sozinho na Vercel (projeto importado do GitHub, Framework Preset: Other, Build Command vazio, Output Directory `./`).

Ao trocar de domínio, atualize `canonical`, `og:url`, `og:image`, `twitter:image` e a URL do JSON-LD no `<head>`.
