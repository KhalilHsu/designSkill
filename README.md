# Design Skills for AI Agents

This repository contains a collection of specialized "Skills" designed to augment AI Agents (like Gemini CLI or other LLM-based assistants) with professional-grade design, typography, and layout capabilities. 

By utilizing these skills, AI agents can transcend basic text output and generate high-quality, aesthetically pleasing, and structurally sound HTML/CSS documents, presentations, and web interfaces.

## 🌟 Available Skills

### 1. 🎨 Web Design Skill (`web-design-skill/`)
Empowers the agent to create high-quality, modern web pages, landing pages, and web app screens.
- **Capabilities:** Responsive design, component-driven architecture, CSS design tokens, modern layout compositions (CSS Grid/Flexbox), and accessible HTML.
- **Workflow:** Enforces a structured process: establishing visual direction -> defining tokens -> planning layout -> building components -> adding interactions.

### 2. 📊 Presentation Deck Skill (`presentation-deck-skill/`)
Enables the agent to generate polished, structured presentation slides (HTML/CSS based) suitable for pitches, reports, or portfolio reviews.
- **Capabilities:** Narrative structuring, slide composition, typography hierarchy (kicker, title, body), and integration of visual assets/charts.
- **Key Feature:** Treats slides as visual stories rather than just bulleted lists.

### 3. 📄 Document & Report Skill (`document-report-skill/`)
Guides the agent in crafting readable, professional long-form documents, specs, and reports.
- **Capabilities:** Typographic readability (line length, line height), layout grids, data figure/table formatting, and logical document structure.
- **Use Case:** Perfect for generating PRDs, technical specifications, or research reports with high visual fidelity.

## 📂 Repository Structure

```text
├── web-design-skill/         # Web page design capabilities and references
├── presentation-deck-skill/  # Slide and presentation generation
└── document-report-skill/    # Long-form document formatting
```

## 🧠 How it Works

Each skill is composed of:
1. **`SKILL.md`**: The core instruction set that the AI agent reads to adopt the persona and workflow of a professional designer.
2. **`references/`**: A library of Markdown files containing specific design principles, implementation patterns, quality rubrics, and token definitions. The agent references these when making design decisions.

## 🛡️ Safety & Privacy
This repository has been audited and contains **no** API keys, personal credentials, or internal company telemetry. It is completely safe for public use.

---
*Generated and maintained as a public resource for the AI Engineering community.*