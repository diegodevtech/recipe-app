<div align="center">

# 🧁 Recipe App

*A beautiful, responsive & accessible recipe page built with modern HTML & CSS*

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)

STARRING: *Cupcake de café com chantilly — the perfect treat for your daily coffee* ☕

</div>

---

## 📋 Table of Contents

- [✨ Quick Start](#-quick-start)
- [🛠 Tech Stack](#-tech-stack)
- [📐 HTML Concepts](#-html-concepts)
- [🎨 CSS Concepts](#-css-concepts)
- [♿ Accessibility](#-accessibility)
- [📁 Project Structure](#-project-structure)

---

## ✨ Quick Start

### Clone & Run Locally

```bash
# Clone the repository
git clone https://github.com/diegodevtech/recipe-app.git

# Navigate into the project
cd recipe-app

# Add the recipe image (required for full experience)
# Place your cupcake image at: assets/main-image.jpg

# Open in your browser
# Option 1: Double-click index.html (simple)
# Option 2: Use a local server (recommended for CORS/fonts)
# Live Server extension is a great suggestion (runs at localhost:5500)

# Using Python 3
python3 -m http.server 8000

# Using Node.js (npx)
npx serve .

# Using PHP
php -S localhost:8000
```

Then visit **http://localhost:8000** in your browser! 🚀

> 💡 **Tip:** Using a local server avoids potential issues with `file://` protocol (e.g. font loading, CORS). Any static file server works.

---

## 🛠 Tech Stack

| Layer | Technology |
|-------|------------|
| **Markup** | HTML5 — Semantic, accessible |
| **Styling** | CSS3 — Variables, Grid, Flexbox, fluid typography |
| **Fonts** | [Google Fonts — Alice](https://fonts.google.com/specimen/Alice) |
| **Runtime** | Static — no build step required |

---

## 📐 HTML Concepts

### 🔹 Core Concepts

| Concept | Implementation | Purpose |
|---------|----------------|---------|
| **Semantic structure** | `<article>`, `<header>`, `<section>`, `<main>`, `<footer>` | Meaningful landmarks for screen readers & SEO |
| **Heading hierarchy** | Single `<h1>`, proper `<h2>` for sections | Logical document outline & accessibility |
| **Definition lists** | `<dl>`, `<dt>`, `<dd>` for time, portions, difficulty | Semantically correct key-value pairs |
| **`lang` attribute** | `lang="pt-BR"` on `<html>` | Correct language for assistive tech & hyphenation |
| **Meta description** | `<meta name="description">` | SEO & social sharing preview |

### 🔹 Advanced Concepts

| Concept | Implementation | Purpose |
|---------|----------------|---------|
| **Skip link** | `<a href="#main-content" class="skip-link">` | Keyboard users skip navigation — WCAG 2.4.1 |
| **ARIA landmarks** | `aria-labelledby`, `aria-label` | Explicit section labels for screen readers |
| **Focus target** | `id="main-content" tabindex="-1"` | Programmatic focus after skip link activation |
| **Image optimization** | `loading="eager"`, `decoding="async"` | Control loading behavior for above-the-fold hero |
| **Resource hints** | `rel="preconnect"` for Google Fonts | Faster font delivery by early connection |

### HTML Snippet — Semantic Recipe Structure

```html
<main id="main-content" tabindex="-1">
  <article>
    <header>
      <h1>Cupcake de café com chantilly</h1>
      <dl aria-label="Informações da receita">
        <div class="recipe-detail">
          <dt>Tempo</dt>
          <dd>1h10</dd>
        </div>
        <!-- ... -->
      </dl>
    </header>
    <section id="ingredients" aria-labelledby="ingredients-heading">
      <h2 id="ingredients-heading">Ingredientes</h2>
      <ul class="ingredients-list">...</ul>
    </section>
  </article>
</main>
```

---

## 🎨 CSS Concepts

### 🔹 Core Concepts

| Concept | Implementation | Purpose |
|---------|----------------|---------|
| **CSS Custom Properties** | `:root { --color-text: #573a37; }` | Centralized design tokens, easy theming |
| **Box model** | `box-sizing: border-box` on `*` | Predictable sizing (padding inside width) |
| **Flexbox** | `display: flex; flex-direction: column; gap` | Vertical layouts, content-driven spacing |
| **CSS Grid** | `grid-template-columns: repeat(auto-fit, minmax(...))` | Responsive recipe-details columns |
| **Pseudo-elements** | `body::before` for blurred background | Layered visual effect without extra HTML |

### 🔹 Advanced Concepts

| Concept | Implementation | Purpose |
|---------|----------------|---------|
| **Fluid typography** | `clamp(1.75rem, 1.5rem + 1vw, 2.5rem)` | Text scales smoothly across viewports |
| **Fluid spacing** | `clamp(1rem, 4vw, 1.5rem)` for padding | Layout adapts to screen size |
| **Logical properties** | `padding-inline-start`, `margin-block` | RTL-ready, flow-independent layout |
| **`inset` shorthand** | `inset: -20px` on pseudo-element | One-line positioning (top/right/bottom/left) |
| **`calc()` in variables** | `calc(-1 * (var(--focus-offset) + 2.5rem))` | Dynamic skip-link positioning |

### 🔹 Responsive & Accessibility

| Concept | Implementation | Purpose |
|---------|----------------|---------|
| **Media queries** | `@media (min-width: 48rem)` | Breakpoint-based layout adjustments |
| **`prefers-reduced-motion`** | `@media (prefers-reduced-motion: reduce)` | Respects user motion sensitivity |
| **`:focus-visible`** | Visible focus ring only for keyboard | Better UX than `:focus` (no mouse focus) |
| **Print styles** | `@media print` | Clean, paper-friendly output |

### CSS Snippet — Fluid Typography & Tokens

```css
:root {
  --text-heading-1: clamp(1.75rem, 1.5rem + 1vw, 2.5rem);
  --space-lg: clamp(1rem, 2vw, 1.5rem);
  --body-padding: clamp(0.75rem, 4vw, 2rem);
}

h1 {
  font-size: var(--text-heading-1);
}
```

---

## ♿ Accessibility

| Feature | How it helps |
|---------|--------------|
| **Skip to content** | Screen reader & keyboard users bypass repeated content |
| **Semantic HTML** | Screen readers announce structure (article, sections, lists) |
| **ARIA labels** | Extra context where semantics aren't obvious |
| **Focus visible** | Keyboard users see where focus is (WCAG 2.4.7) |
| **Reduced motion** | Users with vestibular disorders get minimal animation |
| **Color contrast** | Text meets WCAG AA (4.5:1) on background |

---

## 📁 Project Structure

```
recipe-app/
├── index.html          # Single-page recipe
├── style.css           # All styles (tokens, layout, responsive, print)
├── assets/
│   └── main-image.jpg  # Hero image (add yours here)
└── README.md           # You are here
```

---

<div align="center">

**Feito com ♥ por [diegodevtech](https://github.com/diegodevtech)**

*Built with semantic HTML, modern CSS, and accessibility in mind.*

</div>
