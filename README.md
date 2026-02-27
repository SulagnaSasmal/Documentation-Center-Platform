# DocForge — Docs-as-Code Platform

> A production-grade, interactive demonstration of an end-to-end Docs-as-Code workflow. Built as a single-file application showcasing modern documentation engineering principles.

![License](https://img.shields.io/badge/license-MIT-blue)
![Version](https://img.shields.io/badge/version-1.0.0-brightgreen)
![Status](https://img.shields.io/badge/status-production--ready-success)

## What This Project Demonstrates

DocForge is a fully interactive prototype of a **Docs-as-Code platform** — the kind of documentation infrastructure used by companies like Stripe, Vercel, and Cloudflare. It demonstrates the complete lifecycle of treating documentation as source code:

```
Markdown Source → Git Version Control → CI/CD Pipeline → Multi-Format Output → CDN Deploy
```

### Live Features (All Working)

| View | What It Shows |
|------|--------------|
| **Dashboard** | Pipeline visualization, build history, project structure, content metrics |
| **Editor** | Live Markdown editor with real-time rendered preview, YAML frontmatter |
| **Content Map** | DITA-based topic taxonomy (Concept, Task, Reference, Tutorial, Troubleshoot) |
| **Style Linter** | Automated quality checks against Microsoft Style Guide with scoring |
| **Build Outputs** | Multi-format output previews (HTML, PDF, OpenAPI, JSON, Postman, Changelog) |
| **Configuration** | Full `docforge.config.yml` with toggleable build/lint/deploy settings |

## Architecture & Principles

This project embodies several key documentation engineering principles:

### Content as Source Code
- Markdown files are the **single source of truth**
- YAML frontmatter provides structured metadata (topic type, audience, tags)
- All outputs (HTML, PDF, JSON) are **regenerable artifacts** from the source

### Topic-Based Authoring (DITA-Informed)
- **Concept** topics explain *what* something is
- **Task** topics explain *how* to do something (goal-first structure)
- **Reference** topics provide lookup information (API specs, parameters)
- **Tutorial** topics provide end-to-end guided learning
- **Troubleshooting** topics follow Problem → Cause → Solution patterns

### Quality Automation
- **Vale-based linting** enforces Microsoft Writing Style Guide rules
- Custom rules enforce task-first structure, progressive disclosure, and terminology consistency
- Readability scoring (Flesch-Kincaid) targets developer-friendly grade levels
- Automated link validation catches broken references

### CI/CD Pipeline
```
📝 Markdown → 🔀 Git/PR → ◉ Lint → ⚙ Build → 📦 Multi-Format → 🚀 Deploy
```

## Tech Stack

- **Frontend**: Vanilla HTML/CSS/JS (zero dependencies, single file)
- **Fonts**: Source Serif 4 (headings), Outfit (body), JetBrains Mono (code)
- **Design System**: Custom dark theme with warm amber accent
- **Markdown Renderer**: Custom lightweight parser (live preview)

## Quick Start

### Option 1: Open Directly
Just open `index.html` in any modern browser. No build step, no server, no dependencies.

### Option 2: GitHub Pages
1. Fork this repository
2. Go to **Settings → Pages → Deploy from main branch**
3. Your docs platform is live at `your-username.github.io/docforge-platform`

### Option 3: Local Server
```bash
# Python
python3 -m http.server 8000

# Node.js
npx serve .
```

## Project Structure

```
docforge-platform/
├── index.html          # Complete application (single file)
├── README.md           # This file
└── LICENSE             # MIT License
```

## Who This Is For

- **Technical Writers** demonstrating docs-as-code expertise
- **Documentation Teams** evaluating modern doc tooling approaches
- **Hiring Managers** looking at documentation engineering portfolios
- **Developers** exploring structured documentation practices

## Customization

The platform uses CSS custom properties for theming. Override any variable in `:root`:

```css
:root {
  --accent: #E8A84C;      /* Primary accent color */
  --bg-deep: #08090C;     /* Deepest background */
  --bg-base: #0E1015;     /* Base surface */
}
```

## License

MIT — Free for personal and commercial use.

---

*Built with care for the documentation engineering community.*
