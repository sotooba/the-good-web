# The Good Web

### 🌐 [Explore the Live Directory](https://the-good-web.vercel.app/)

A hand-compiled, minimalist digital directory of genuinely free lists of lists, and incredibly useful web resources that require no money, credit cards, or hidden paywalls.

## 🧭 Overview
This project is a 100% static frontend directory built with **Eleventy (11ty)** and **Bootstrap 5**. It is designed to act as a quiet corner of the internet helping users discover thoughtful tools without tracking or subscription fatigue.

The live application is hosted completely for free via automatic deployments on **Vercel**.

## 💻 Development & Workspace

This project is optimized to run in the cloud using **GitHub Codespaces**, meaning you do not need to install Node.js, npm, or heavy modules on your local machine.

### Local/Cloud Preview
To spin up the built-in development engine and launch the live-refreshing browser preview panel, execute this script inside your workspace terminal:

```bash
npm start
```

Once the terminal outputs that the server is live, look for the Codespaces pop-up alert and click **Open in Browser** to view the live dashboard.

### Production Build
To test the hard-compiled static distribution architecture locally before pushing updates:

```bash
npx @11ty/eleventy
```

## 🤝 Contributing & Curation
You can help expand this digital library by verifying free tools and adding entries directly to the database file. 

To open a pull request, follow these exact structure guidelines:

1. Open the data layer file located at: `src/_data/websites.json`.
2. Locate or create the correct category block node.
3. Append your new link entry ensuring properties follow the strict structural hierarchy order:

```json
{
  "name": "Website Name",
  "url": "https://example.com",
  "icon": "matching-vector-keyword",
  "tags": ["tag1", "tag2"],
  "requires_signup": false,
  "desc": "A brief description of what the tool accomplishes cleanly."
}
```

### Core Curation Rules
Before submitting your pull request, you must verify that the suggested asset meets our strict community baseline requirements:
* **True Zero Cost**: The link must carry no hidden tier limits, trial expiration dates, mandatory paywalls, or forced credit card inputs.
* **Strict Parameter Sorting**: The object dictionary **MUST** place the `"name"` and `"url"` variables at the very top, and position the `"desc"` string at the absolute bottom.
* **Theme Compliant Icons**: Use a relevant keyword string for the `"icon"` field (`video`, `film`, `tv`, `music`, `audio`, `download`, `palette`, `sparkles`, `book`, `code`, `type`) so our inline Nunjucks loop system can hook and generate the correct vector graphic boundaries seamlessly.

4. Save your changes, run your local test server loop to verify that the grid scales cleanly, commit your branch, and submit your pull request!
