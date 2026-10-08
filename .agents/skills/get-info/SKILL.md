---
name: get-info
description: >-
  Interactive skill to gather necessary personal, professional, and design details
  from the user to build a tailored, high-converting portfolio website.
---

# Get Info Skill - Portfolio Requirements Gathering

Use this skill when initiating the portfolio creation process or when key details about the user's background, projects, design taste, or goals are missing.

---

## 🎯 Objective
Collect all structured information needed to build a personalized, complete, and stunning portfolio without asking overwhelming or disorganized questions.

---

## 📋 Information Checklist

Gather information systematically across the following categories:

### 1. 👤 Personal & Professional Identity
- **Full Name** & Title/Role (e.g., *Frontend Engineer*, *Full-stack Developer*, *AI Researcher*, *UI/UX Designer*)
- **Short Bio / Tagline** (1-2 punchy sentences summarizing their focus, passion, or value proposition)
- **Location & Availability** (e.g., *Tashkent, Uzbekistan / Open to remote roles & freelance*)
- **Contact Details & Social Links**:
  - Email, GitHub, LinkedIn, Telegram, Twitter/X, LeetCode, etc.

### 2. 💻 Technical Skills & Tech Stack
- **Primary Languages**: (e.g., JavaScript, TypeScript, Python, Go)
- **Frameworks & Libraries**: (e.g., React, Next.js, Vue, FastAPI, Node.js)
- **Tools & Platforms**: (e.g., Docker, Git, AWS, Figma, PostgreSQL, Supabase)
- **Core Competencies / Domains**: (e.g., Web Performance, Mobile Apps, REST & GraphQL APIs, Agentic AI)

### 3. 🚀 Featured Projects (3 to 5 projects recommended)
For each project:
- **Title & One-liner**
- **Problem solved / Description**
- **Tech stack used**
- **Links** (Live Demo URL, GitHub Repo URL)
- **Key achievements or metrics** (e.g., *1k+ active users*, *improved load time by 40%*)

### 4. 💼 Experience & Education (Optional but recommended)
- **Work Experience**: Role, Company name, Dates, Key accomplishments
- **Education / Certifications**: Degree, University/Institution, Year

### 5. 🎨 Design & Aesthetic Preferences
- **Theme Style**: Dark theme (default), Light theme, or Dark/Light toggle
- **Color Palette / Accent Color**: (e.g., Cyberpunk Neon, Minimal Monochrome, Deep Indigo & Violet, Emerald Tech)
- **Vibe / Typography**: Minimalist, Creative/Playful, Corporate/Enterprise, or Terminal/Hacker style
- **Desired Sections**:
  - Hero / Introduction
  - About Me
  - Tech Stack / Skills
  - Featured Projects
  - Work Experience / Timeline
  - Testimonials / Recommendations
  - Contact Form / Social links
  - Resume / CV Download button

---

## 💾 Output Requirement: `data/portfolio-data.json`

Once user details are gathered or confirmed, the agent **MUST** save them directly into `data/portfolio-data.json` with the following clean JSON schema:

```json
{
  "personal": {
    "name": "Alex Mercer",
    "title": "Senior Frontend Engineer & Creative Developer",
    "tagline": "Crafting polished, high-performance web experiences with modern architecture.",
    "location": "Tashkent, Uzbekistan",
    "availability": "Open to remote roles & freelance",
    "email": "alex@example.com",
    "socials": {
      "github": "https://github.com/example",
      "linkedin": "https://linkedin.com/in/example",
      "telegram": "https://t.me/example",
      "twitter": "https://x.com/example"
    }
  },
  "preferences": {
    "theme": "dark",
    "accentColor": "#6366f1",
    "typography": "Outfit, Inter",
    "vibe": "modern-minimal"
  },
  "skills": {
    "languages": ["TypeScript", "JavaScript", "Python"],
    "frontend": ["React", "Next.js", "Vue 3", "CSS3 / Sass"],
    "backend": ["Node.js", "FastAPI", "PostgreSQL"],
    "tools": ["Docker", "Git", "Figma", "Vercel"]
  },
  "projects": [
    {
      "id": "project-1",
      "title": "AI Canvas Studio",
      "description": "Interactive collaborative canvas powered by generative AI and web workers.",
      "tags": ["TypeScript", "React", "Canvas API", "FastAPI"],
      "demoUrl": "https://demo.example.com",
      "githubUrl": "https://github.com/example/ai-canvas",
      "featured": true
    }
  ],
  "experience": [
    {
      "role": "Lead Frontend Engineer",
      "company": "TechCorp Global",
      "period": "2023 - Present",
      "highlights": [
        "Architected enterprise dashboard reducing initial page load time by 45%.",
        "Mentored a team of 6 engineers across front-end best practices."
      ]
    }
  ],
  "education": [
    {
      "degree": "B.S. in Computer Science",
      "institution": "Tashkent University of Information Technologies",
      "period": "2019 - 2023"
    }
  ]
}
```

---

## 💬 Interview Strategy & Guidelines

1. **Don't overwhelm the user**: Ask questions in logical batches (2-3 questions at a time) or offer sensible defaults that the user can confirm with a single reply.
2. **Offer quick-start options**: Provide an option to paste a resume, LinkedIn profile text, or GitHub username for automatic parsing.
3. **Save to JSON & Hand-off**: Automatically save the gathered data to `data/portfolio-data.json`. Then invoke the `build-portfolio` skill to generate the site.
