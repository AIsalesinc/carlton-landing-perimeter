# Carlton Landing Digital Perimeter

Static landing page for the Carlton Landing Digital Perimeter (RevFirma).

## Structure
- index.html  — the page
- assets/     — logos (SVG) and the perimeter video
- vercel.json — clean URLs + cache headers

## Deploy to Vercel

### Drag & drop
1. Go to https://vercel.com/new
2. Choose Import then Browse and drop this folder (or upload this zip)
3. Vercel detects a static site, no build step needed
4. Click Deploy

### Vercel CLI
    npm i -g vercel
    cd path/to/this/folder
    vercel
Follow the prompts. For production: vercel --prod

## Local preview
Open index.html directly, or run a static server:
    npx serve .
