# Nexovant — Estúdio Digital

> Não criamos apenas sites. Criamos presença digital.

Site institucional one-page nível Awwwards com **Glass Folder Cards** interativo, hero com widget `site.tsx` e cursor custom desktop.

**Live:** `https://seuuser.github.io/nexovant`  
**WhatsApp:** (27) 99974-6333 → [wa.me/5527999746333](https://wa.me/5527999746333)

---

## ✨ Features

- **Hero anterior restaurado** — título cinético, widget code editor com syntax highlight, badges `build ok • LCP 0.9s • Lighthouse 100/100`
- **Glass Folder Cards** — pastas de vidro com frosted glass real (`backdrop-filter: blur(22px) saturate(1.5)`), 3 camadas: back panel com arte generativa, arquivos no meio, front panel em vidro
  - Hover inclina vidro na dobradiça inferior (`--gf-hinge`)
  - Click abre com fan das telas
  - Arte generativa via Canvas: `hexToRgb`, `rng`, `makeFbm`, `createArtJob` com presets `aurora / ember / dusk / glacier / verdant`
- **Portfolio com 12 telas reais:**
  - RSR Contábil — 4 telas (sem localização, remoto)
  - Nexovant Estúdio Digital — 4 telas (dark premium)
  - Suprema Contábil / Alex Moraes — 4 telas (Cariacica-ES)
- **Lightbox fullscreen** — overlay #040814 blur 20px, navegação ← →, contador 01/12, ESC, swipe mobile
- **Custom Cursor Desktop** — dot 6px #38BDF8 + anel 32px com lerp suave, só em `(min-width: 1024px) and (pointer: fine)`, label ABRIR / VER
- **Interativo** — widget tilt 3D que segue mouse, botões magnéticos, título com gradiente animado, scroll reveal

---

## 🎨 Stack & Identidade

- **Frontend:** React + Tailwind + TypeScript + Framer Motion-like CSS
- **Cores:** fundo #040814, cartões #0A1224/#0F1C36, texto #F8FAFC/#94A3B8, acentos #2563EB e #38BDF8
- **Tipografia:** Outfit (títulos), Plus Jakarta Sans (corpo), Fira Code (etiquetas `[ 03 — Portfolio ]`)
- **Logo:** NEXOVANT (NEXO branco + VANT ciano #38BDF8)
- **Estrutura:** Navbar glass, Hero, Marquee editorial, Serviços (3 forças), Processo, Portfolio Glass Folders, Contato, Rodapé, WhatsApp flutuante

---

## 📁 Arquivos

Este repositório pode ser de dois tipos:

### Opção A — Single File (recomendado para GitHub Pages)
Apenas `index.html` com tudo embutido (imagens base64, CSS, JS, glass component, cursor):
- `index.html` — 940KB, zero dependências, funciona offline

### Opção B — Projeto Next.js + shadcn
```
/app
  layout.tsx
  page.tsx
  globals.css
/components/ui
  glass-folder-cards.tsx  # componente completo 900 linhas com arte generativa
/lib
  utils.ts
/public/portfolio  # suas 12 screenshots
package.json
tailwind.config.ts
components.json
```

---

## 🚀 Hospedar no GitHub Pages (30s)

### Single File
1. Crie repositório `nexovant` no GitHub
2. Faça upload do `index.html` na raiz, branch `main`
3. Settings → Pages → Source: **Deploy from a branch** → Branch: `main` / root → Save
4. Aguarde 1 min → site em `https://seuuser.github.io/nexovant/`

```bash
# via CLI
git init
git add index.html
git commit -m "feat: nexovant glass portfolio single file"
git branch -M main
git remote add origin https://github.com/SEUUSER/nexovant.git
git push -u origin main
```

---

## ▲ Hospedar na Vercel

### Drag & Drop (mais rápido)
1. https://vercel.com/new → Browse → arraste `index.html` → Deploy

### Via GitHub
1. Importe repositório `nexovant` em https://vercel.com/new
2. Framework Preset: **Next.js** (se for projeto) ou **Other** (se for single file)
3. Build Command: `npm run build` (só para projeto Next.js)
4. Deploy

---

## 📦 Rodar local (projeto Next.js)

```bash
npm install
npm run dev
# http://localhost:3000
```

Setup shadcn se for começar do zero:
```bash
npx shadcn@latest init
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Copie `glass-folder-cards.tsx` para `components/ui/` — ele já é self-contained: React é o único import, sem CSS externo, sem imagens, sem fonts.

---

## 🧩 Glass Folder Cards — Como usar

```tsx
import GlassFolder from "@/components/ui/glass-folder-cards"

<GlassFolder
  label="RSR Contábil"
  meta="4 telas"
  art="aurora"
  seed={3}
  tone="light"
  files={[
    { name: "Hero - Contabilidade descomplicada", meta: "Hero • dark", image: "/portfolio/rsr-hero.png" },
    { name: "Sobre Rayne + Serviços", meta: "Sobre • 480 clientes", image: "/portfolio/rsr-sobre.png" },
  ]}
  action="more"
  labelPlacement="bottom-left"
/>
```

Props: `label`, `meta`, `tone light/dark`, `art preset/recipe`, `seed`, `image`, `files`, `action add/more/none`, `labelPlacement`, `width`, `appear`, `appearDelay`

Arte generativa: `createArtJob(width, height, recipe, seed)` com field domain-warped duas vezes, normalização por percentis, iluminação difusa + especular.

---

## 📱 WhatsApp & Contato

Todo link usa novo número:
- Display: **(27) 99974-6333**
- Link: `https://wa.me/5527999746333?text=Ol%C3%A1%2C%20vim%20pelo%20site%20da%20Nexovant`
- Locais: botão flutuante verde, CTA Hero "Falar com a Nexovant", seção [04 — Contato], navbar "Começar projeto"

E-mail: `contatonexovant@gmail.com`

---

## 🎯 Ajustes recentes

- [x] Localização Serra-ES removida — portfolio sem localização
- [x] Prazo "14 dias" → "no máximo 5 dias"
- [x] Hero anterior restaurado igual print `image_c4a8c7.png`
- [x] Custom cursor só desktop com dot + anel
- [x] Portfolio com glass folders e 12 telas reais dentro das páginas
- [x] Single file com base64 para GitHub Pages

---

## 📄 Licença

Proprietário — Nexovant Estúdio Digital. Componente glass-folder-cards inspirado em design editorial com arte generativa própria.

---

Feito com 💙 em Cariacica-ES • #040814 • #2563EB → #38BDF8
