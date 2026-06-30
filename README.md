# Anu — Portfolio Website

A Quarto-based personal portfolio for a policy strategist and program manager.  
Built with a pastel blue palette, DM Serif Display + DM Sans typography, and a clean editorial aesthetic.

---

## 📁 File structure

```
quarto-portfolio/
├── _quarto.yml          # Site config, navbar, footer, theme
├── custom.scss          # Full SCSS theme (pastel blue palette)
├── styles.css           # Supplemental CSS (grid, blog, recognition)
├── index.qmd            # Homepage (hero, stats, projects, blog, awards)
├── about.qmd            # About (bio, skills, timeline, education)
├── awards.qmd           # Awards (trophy shelf, recognition list, media)
├── projects/
│   ├── index.qmd        # Projects listing (Quarto listing)
│   ├── stata3.qmd       # Assignment: Sampling theory + power analysis
│   └── stata8.qmd       # Assignment: Fuzzy matching + spatial analysis
├── blog/
│   ├── index.qmd        # Blog listing (Quarto listing)
│   └── posts/
│       └── evaluation-failure.qmd   # Sample post
└── assets/              # Images, CV PDF, favicon
    ├── cv.pdf
    └── favicon.ico
```

---

## 🚀 Quick start

### 1. Install Quarto
Download from [quarto.org](https://quarto.org/docs/get-started/)

### 2. Install the cosmo theme dependency
The theme extends Quarto's built-in `cosmo` Bootstrap theme — no extra install needed.

### 3. Preview locally
```bash
cd quarto-portfolio
quarto preview
```

### 4. Build for production
```bash
quarto render
```
Output goes to `_site/` — deploy this folder to GitHub Pages, Netlify, or any static host.

---

## 🎨 Colour palette

All colours are defined as SCSS variables in `custom.scss`:

| Variable | Hex | Usage |
|---|---|---|
| `$blue-50` | `#F0F7FF` | Page background |
| `$blue-100` | `#DAEEFF` | Card fills, stat blocks |
| `$blue-200` | `#B8D8F8` | Borders, light accents |
| `$blue-300` | `#8BBFE8` | Mid accent, timeline dots |
| `$blue-500` | `#2E7DBF` | Primary brand, eyebrows |
| `$blue-700` | `#1A3A5C` | Headings, navbar, footer |
| `$teal-100` | `#D6F5F2` | Supporting stat cards |
| `$teal-300` | `#6ECDC5` | Supporting accent |

---

## ✏️ Personalise

1. **Name/title:** Find and replace `Anurita Sharma` across all `.qmd` files
2. **Stats:** Edit the hero stat cards in `index.qmd`
3. **Experience timeline:** Update `about.qmd`
4. **Projects:** Edit existing `.qmd` files in `projects/` or add new ones — the listing auto-discovers them
5. **Blog:** Add `.qmd` files to `blog/posts/` — the listing auto-discovers them
6. **Awards:** Update `awards.qmd`
7. **Affiliations:** Edit the chips at the bottom of `index.qmd`
8. **CV:** Replace `assets/cv.pdf` with your actual CV
9. **Links:** Update GitHub/LinkedIn/email links in `_quarto.yml` footer and `index.qmd`

---

## 🌐 Deploy to GitHub Pages

1. Push this folder to a GitHub repo
2. In repo Settings → Pages → Source: GitHub Actions
3. Create `.github/workflows/publish.yml`:

```yaml
name: Publish to GitHub Pages
on:
  push:
    branches: [main]
jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: quarto-dev/quarto-actions/setup@v2
      - uses: quarto-dev/quarto-actions/publish@v2
        with:
          target: gh-pages
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

---

## 📦 Dependencies

- [Quarto](https://quarto.org) ≥ 1.4
- [DM Serif Display + DM Sans](https://fonts.google.com) — loaded via Google Fonts CDN
- Bootstrap cosmo theme — bundled with Quarto
