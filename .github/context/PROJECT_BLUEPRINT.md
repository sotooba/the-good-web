# Project Blueprint: The Good Web

## 1. Overview & Philosophy
"The Good Web" is a hand-compiled, minimalist digital directory of genuinely free, incredibly useful web resources. 
* **Zero AI Slop Vibe**: The site must feel warm, human, intentional, and high-effort. Avoid pitch-black backgrounds, neon purple gradients, or sterile geometric landing layouts.
* **No Backend**: This is a 100% static frontend website with no server-side handling or dynamic databases.
* **Open Disclosure**: We openly credit our curation roots. The site features a dedicated "Credits & Disclosures" sheet detailing our inspiration from community archivers.

## 2. Technical Stack
* **Data Layer**: A local `websites.json` file containing all categories and curated links.
* **Templating Engine**: Eleventy (11ty) using Nunjucks syntax to loop through data into a static output.
* **CSS Framework**: Bootstrap 5 (loaded via CDN) for layout utilities.
* **Hosting & Deployment**: Vercel (connected to GitHub for automatic production builds).

## 3. Directory Folder Architecture
The project files must be created and categorized exactly as follows:

```text
the-good-web/
├── .github/
│   └── context/
│       ├── PROJECT_BLUEPRINT.md
│       ├── UI_AND_STYLING.md
│       └── DATA_STRUCTURE.md
├── src/
│   ├── _data/
│   │   └── websites.json
│   ├── _includes/
│   │   └── layout.njk
│   ├── css/
│   │   └── style.css
│   └── index.njk
├── .eleventy.js
├── .gitignore
├── LICENSE
├── package.json
└── README.md
```



## 4. Engineering Core Requirements
* **Automated Environment**: The agent must automatically initialize npm (`npm init -y`) and install Eleventy (`npm install @11ty/eleventy --save-dev`) into the cloud workspace.
* Content must be isolated from presentation. No hardcoded individual site items in the templates.
* Keep HTML markup modular. Move explicit styles into the external stylesheet (`src/css/style.css`).
* Keep JavaScript light and native. Do not install heavy npm frameworks.