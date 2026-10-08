# 🚀 Portfolio Creator Agent

A specialized, AI-powered pair programmer and agent designed to interview developers, designers, and tech professionals, collect their verified personal details, and generate modern, high-performance personal portfolio websites with **zero external dependencies**.

---

## 🌟 Key Features

- **🎯 Specialized Scope**: Exclusively focused on personal portfolio creation. Automatically declines and redirects off-topic queries.
- **🛡️ Zero Hallucination Guarantee**: Strictly uses verified information provided by the user. No fabricated fake projects or dummy work experience.
- **💾 JSON-Driven Pipeline**: Gathers requirements systematically into a clean `data/portfolio-data.json` structure before generating code.
- **💎 Premium Design & Aesthetics**:
  - Dark mode by default with light mode toggle.
  - Smooth glassmorphism (`backdrop-filter`), ambient glows, and card hover micro-interactions.
  - Modern typography powered by Google Fonts (*Outfit* and *Inter*).
  - 100% mobile-friendly responsive layout.
- **⚡ Pure Vanilla Web Stack**: Fast and lightweight HTML5, modern CSS3 (custom properties/tokens), and ES6+ JavaScript.

---

## 📁 Project Structure

```text
portfolio_creator_agent/
│
├── AGENTS.md                  # Core guidelines, rules, and scope boundaries for the agent
├── README.md                  # Project overview and documentation
│
├── .agents/
│   └── skills/
│       ├── get-info/          # Skill: Interactive user interview & JSON data generation
│       │   └── SKILL.md
│       └── build-portfolio/   # Skill: Architecture, CSS system & portfolio site generation
│           └── SKILL.md
│
├── data/
│   └── portfolio-data.json    # Real user details (identity, skills, projects, contact)
│
├── css/
│   └── style.css              # Design tokens, themes, layout & animations
│
├── js/
│   └── main.js                # Theme switcher (dark/light) & smooth navigation
│
└── index.html                 # Semantic HTML5 portfolio landing page
```

---

## 🔄 How It Works (Pipeline)

1. **Step 1 — Interview & Requirement Gathering (`skills/get-info`)**:
   The agent collects the user's name, professional role, skills, real projects, and contact info, then saves it to `data/portfolio-data.json`.
2. **Step 2 — Building the Portfolio (`skills/build-portfolio`)**:
   The agent reads `data/portfolio-data.json` and crafts:
   - `index.html`: Semantic markup with SEO and Open Graph metadata.
   - `css/style.css`: Clean design system with CSS custom properties.
   - `js/main.js`: Dark/Light theme toggle and smooth scrolling.
3. **Step 3 — Preview & Deployment**:
   Open `index.html` directly in any web browser or deploy to GitHub Pages, Vercel, or Netlify with zero build step required.

---

## 🚀 Quick Start / Local Preview

No package managers or build tools required!

Simply open `index.html` in your favorite browser:

```bash
# Example with python's built-in HTTP server:
python3 -m http.server 3000
```

Then visit `http://localhost:3000` in your browser.

---

## 📄 License
MIT License. Feel free to use and customize for your own personal portfolio!
