# 🤖 Portfolio Creator Agent

A highly specialized AI Agent repository for Antigravity IDE and modern agent workflows. This agent interviews engineers and designers, gathers validated background data, and generates aesthetic, production-ready personal portfolio websites.

---

## 🎯 Agent Purpose & Scope

- **Exclusivity**: Dedicated solely to personal developer/designer portfolio generation and design consulting.
- **Strict Guardrails**: Automatically rejects any unrelated requests (e.g., math, trivia, general backend services, chit-chat) and guides the user back to portfolio building.
- **Data Integrity**: Zero hallucination policy. Never invents fake projects, employment history, or dummy tech stacks. Missing details are explicitly queried from the user.

---

## 📁 Repository Architecture

This repository contains only agent definition, rules, and skills:

```text
portfolio_creator_agent/
│
├── AGENTS.md                  # Core rules, behavioral constraints & off-topic guards
├── README.md                  # Agent repository documentation & overview
│
└── .agents/
    └── skills/
        ├── get-info/          # Skill: Interactive requirement gathering & JSON schema export
        │   └── SKILL.md
        │
        └── build-portfolio/   # Skill: Modern portfolio architecture & web generation playbook
            └── SKILL.md
```

---

## ⚡ Skills Breakdown

### 1. `get-info` ([`.agents/skills/get-info/SKILL.md`](.agents/skills/get-info/SKILL.md))
- **Role**: Conducts a structured, bite-sized interview to capture:
  - Personal identity (Name, title, bio, location, contact details).
  - Tech stack (Languages, frameworks, tools).
  - Verified projects (Title, description, stack, GitHub/Demo URLs).
  - Aesthetic preferences (Dark/Light mode, accent color, typography).
- **Artifact Output**: Saves collected structured data to `data/portfolio-data.json`.

### 2. `build-portfolio` ([`.agents/skills/build-portfolio/SKILL.md`](.agents/skills/build-portfolio/SKILL.md))
- **Role**: Reads `data/portfolio-data.json` and crafts the complete personal website:
  - **Structure**: Semantic HTML5 (`index.html`) with proper SEO and Open Graph metadata.
  - **Styling**: Modern CSS3 (`css/style.css`) utilizing design tokens, glassmorphism, responsive grid/flexbox, and Google Fonts.
  - **Interactivity**: Clean ES6+ JavaScript (`js/main.js`) featuring Dark/Light mode toggle, smooth scrolling, and responsive menu logic.
  - **Zero Bloat**: Generates pure vanilla code with no unnecessary third-party runtime dependencies.

---

## 🔄 Execution Pipeline

```text
User Request
     │
     ▼
[ AGENTS.md Rules Check ] ──(Off-topic query)──► Polite Rejection & Redirect
     │ (Portfolio query)
     ▼
[ 1. get-info skill ]
     │
     ▼
Produces: data/portfolio-data.json (Real data only)
     │
     ▼
[ 2. build-portfolio skill ]
     │
     ▼
Generates: index.html + css/style.css + js/main.js
```

---

## 🛠 Usage in Antigravity IDE

1. Open this repository in Antigravity IDE.
2. The agent automatically discovers rules from `AGENTS.md` and skills from `.agents/skills/`.
3. Simply start a chat by greeting the agent or saying:
   > *"Menga portfolio sayt yaratishda yordam ber"*
4. The agent will guide you through the `get-info` interview and generate your customized website.
