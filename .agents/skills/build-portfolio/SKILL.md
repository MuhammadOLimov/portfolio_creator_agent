---
name: build-portfolio
description: >-
  Step-by-step workflow for architecting, designing, generating, and previewing
  a high-impact, aesthetic, and fully responsive personal portfolio website.
---

# Build Portfolio Skill

Use this skill when you have gathered user information (via `get-info` or user prompt) and are ready to generate or customize the portfolio website.

---

## 🎯 Objective
Generate a production-ready, visually stunning, mobile-responsive portfolio website adhering to modern web design standards (glassmorphism, micro-animations, curated color palettes, accessible semantics, and zero external dependency bloat).

---

## 🛠 Recommended Tech Stack & Architecture
Unless explicitly requested otherwise:
- **Structure**: Vanilla HTML5 (`index.html`) with semantic elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`).
- **Styling**: Vanilla CSS3 (`style.css` or modular CSS) with CSS custom properties (tokens) for:
  - Color palette (accents, surface, background, text, borders)
  - Typography (Google Fonts: *Inter*, *Outfit*, *Plus Jakarta Sans*, or *Fira Code*)
  - Transitions and glassmorphism backdrops (`backdrop-filter: blur(...)`)
- **Interactivity**: Vanilla ES6+ (`main.js`):
  - Theme toggler (Light/Dark mode with `localStorage` persistence)
  - Smooth anchor scrolling & active nav section tracking (IntersectionObserver)
  - Project category filtering or modal view
  - Copy-to-clipboard for email/contact details
  - Mobile hamburger menu drawer with smooth transitions

---

## 🏗 Directory Structure Template

```text
├── index.html           # Main semantic markup with SEO meta tags
├── css/
│   ├── style.css        # Main stylesheet with CSS variables & layout
│   └── animations.css   # Keyframes, fade-ins, hover states (optional)
├── js/
│   └── main.js          # Interactive features (theme, filter, mobile menu)
└── assets/
    ├── images/          # Project screenshots, avatars, icons
    └── resume.pdf       # User resume / CV (placeholder or real)
```

---

## 🚀 Execution Workflow

### Step 1: Read & Verify Data (`data/portfolio-data.json`)
1. Read user data directly from `data/portfolio-data.json` (created by `get-info`):
   - Personal info: Name, title, tagline, location, contacts & socials.
   - Preferences: Theme (dark/light), accent color, typography.
   - Skills & Tech Stack: Languages, frontend, backend, tools.
   - Projects: Title, description, tags, URLs.
   - Experience & Education: Timeline, milestones.
2. If `data/portfolio-data.json` does not exist or has missing fields, run `get-info` or populate sensible placeholders while preserving valid user fields.
3. Use the JSON data directly to inject content into `index.html` (and optionally make `js/main.js` render dynamic components or read from `data/portfolio-data.json` via fetch if hosted).

### Step 2: Establish the Design System (`css/style.css`)
- Define CSS custom properties:
  ```css
  :root {
    --bg-primary: #0a0c10;
    --bg-secondary: #12161f;
    --bg-card: rgba(22, 27, 38, 0.7);
    --border-color: rgba(255, 255, 255, 0.08);
    --text-primary: #f0f4f8;
    --text-secondary: #94a3b8;
    --accent: #6366f1; /* or user chosen accent */
    --accent-glow: rgba(99, 102, 241, 0.25);
    --font-heading: 'Outfit', sans-serif;
    --font-body: 'Inter', sans-serif;
  }
  ```
- Configure typography via Google Fonts `@import` or `<link>`.
- Implement responsive utility styles and accessible focus states.

### Step 3: Build Semantic HTML (`index.html`)
Include standard sections:
1. **Header & Navigation**: Logo/Name, navigation links, theme switcher button, mobile toggle.
2. **Hero Section**: Eyebrow badge (e.g., "Available for work"), bold headline, punchy bio, primary CTA ("View Projects") and secondary CTA ("Contact Me").
3. **About Section**: Professional summary, key highlights, quick stats.
4. **Skills & Tech Stack**: Categorized skill pills or icon cards with subtle hover glow.
5. **Featured Projects**: Card grid with tag pills, preview screenshot/mockup, descriptions, and action links (GitHub, Live Demo).
6. **Experience / Timeline**: Career milestones, roles, and dates.
7. **Contact / Footer**: Direct email link, social icons, copyright notice.

### Step 4: Add Interactivity (`js/main.js`)
- Implement dark/light theme toggle.
- Add Intersection Observer for scroll-triggered fade-in animations.
- Implement mobile navigation drawer open/close logic.
- Add interactive project filters if there are >4 projects.

### Step 5: Validation & Preview
- Check for responsive layout on small and large viewports.
- Ensure all external font links and icons load properly (e.g. Feather Icons, Lucide CDN, or inline SVGs).
- Verify color contrast for readability.
