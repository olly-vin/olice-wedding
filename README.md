# 💍 wedding-tings

> The official website for our wedding — built with HTML, CSS & JS, hosted via GitHub Pages.

[![Live Site](https://img.shields.io/badge/Live%20Site-Visit-navy?style=for-the-badge)](https://olly-vin.github.io/wedding-tings)
[![GitHub Pages](https://img.shields.io/badge/Hosted%20on-GitHub%20Pages-teal?style=for-the-badge&logo=github)](https://pages.github.com/)
[![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=for-the-badge)]()

---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Live Site](#live-site)
- [Project Structure](#project-structure)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Branching Strategy](#branching-strategy)
- [Daily Workflow](#daily-workflow)
- [Commit Message Standards](#commit-message-standards)
- [Contributing](#contributing)
- [Deployment](#deployment)

---

## About the Project

This repository contains the source code for our wedding website. It covers all the details guests need — venue information, schedule, RSVP, and more.

The site is built entirely with vanilla HTML, CSS, and JavaScript — no frameworks, no build tools, no complexity. What you see in this repo is exactly what gets served to guests.

---

## Live Site

🌐 **[https://olly-vin.github.io/wedding-tings](https://olly-vin.github.io/wedding-tings)**

The live site updates automatically within 60–90 seconds of any merge to the `main` branch. There is no manual deployment step.

---

## Project Structure

```
wedding-tings/
├── index.html          # Home / landing page
├── rsvp.html           # RSVP form page
├── details.html        # Venue, date & schedule (planned)
├── our-story.html      # Our story page (planned)
├── gallery.html        # Photo gallery (planned)
├── styles.css          # Global stylesheet
├── images/             # All image assets
│   └── ...
├── js/
│   └── main.js         # Shared JavaScript (planned)
├── .vscode/
│   └── settings.json   # Shared editor config — do not modify
├── .gitignore          # Files excluded from version control
└── README.md           # This file
```

---

## Tech Stack

| Layer | Technology | Why |
|---|---|---|
| Markup | HTML5 | Semantic, accessible structure |
| Styling | CSS3 | Custom properties, flexbox, grid |
| Behaviour | Vanilla JavaScript | No dependencies, fast load |
| Hosting | GitHub Pages | Free, auto-deploys from `main` |
| Version Control | Git + GitHub | Full history, branch-based workflow |
| Editor | Visual Studio Code | Shared settings via `.vscode/` |
| Git GUI | GitHub Desktop | Visual branch and commit management |

---

## Getting Started

### Prerequisites

- [GitHub Desktop](https://desktop.github.com/) — for branch and commit management
- [Visual Studio Code](https://code.visualstudio.com/) — for editing
- A free [GitHub account](https://github.com/) with access to this repo

### Setup (< 10 minutes)

**1. Clone the repository**

In GitHub Desktop: `File → Clone Repository → URL tab`

Paste:
```
https://github.com/olly-vin/wedding-tings.git
```

Choose your local path (e.g. `Documents/GitHub/wedding-tings`) and click **Clone**.

**2. Install VS Code Extensions**

Open VS Code and press `Ctrl+Shift+X`. Install the following:

| Extension | Purpose |
|---|---|
| Live Server *(Ritwick Dey)* | Auto-refreshes browser on save |
| Prettier – Code Formatter | Consistent formatting on save |
| GitLens | Inline Git history and blame |
| HTML CSS Support | Class name autocomplete |
| Spell Checker *(Street Side)* | Catches typos in copy |

**3. Open the project**

In GitHub Desktop: `Repository → Open in Visual Studio Code`

**4. Preview locally**

Right-click `index.html` in the VS Code file tree → **Open with Live Server**

The site opens at `http://localhost:5500` and auto-refreshes on every save.

---

## Branching Strategy

This project uses a **three-level branching structure** to keep the live site protected while allowing free experimentation during development.

```
main ──────────────────────────────────────────────── [LIVE SITE]
  └─ feature/homepage ──────────────────── PR → merge
        └─ batch/homepage-hero            (local commits)
        └─ batch/homepage-nav             (local commits)
  └─ feature/rsvp-page ─────────────────── PR → merge
        └─ batch/rsvp-form-fields         (local commits)
        └─ batch/rsvp-validation          (local commits)
  └─ feature/gallery ──────────────── (in progress)
        └─ batch/gallery-layout           (local commits)
```

### Branch Types

| Branch | Naming Convention | Purpose |
|---|---|---|
| `main` | `main` | Protected. Powers the live site. Merge via PR only. |
| Feature | `feature/<section-name>` | One per site section. Long-lived. |
| Batch | `batch/<short-description>` | Focused chunk of work within a feature. |

> ⚠️ **Never commit directly to `main`.** All changes arrive via pull request from a feature branch.

---

## Daily Workflow

Every coding session follows this loop:

```
Fetch → Branch → Code → Commit → Push → PR (when ready)
```

### Step by Step

1. **Fetch & Pull** — GitHub Desktop → `Fetch origin` → `Pull origin`
2. **Switch/Create branch** — Use the branch switcher in GitHub Desktop. Work on a `batch/*` branch.
3. **Open in VS Code** — `Repository → Open in Visual Studio Code`
4. **Write & preview** — Edit files. Live Server updates the browser automatically.
5. **Commit** — GitHub Desktop: tick changed files → write commit message → `Commit to batch/...`
6. **Push** — Click `Push origin` at the end of every session (backs up your work)
7. **Merge batch → feature** — When batch is complete: switch to feature branch → `Branch → Merge into current branch` → select your batch branch
8. **Open Pull Request** — When feature is complete: open on GitHub.com → `Compare & pull request` → merge into `main`

---

## Commit Message Standards

Use this format for every commit:

```
<type>(<scope>): <short description>
```

### Types

| Type | Use When |
|---|---|
| `feat` | Adding a new section, page, or visible feature |
| `fix` | Correcting a bug, broken layout, or broken link |
| `style` | CSS-only changes with no functional impact |
| `content` | Text, image, or copy updates only |
| `chore` | Maintenance — file cleanup, image compression |
| `docs` | README or documentation changes |

### Examples

```
feat(homepage): add hero banner with background image
fix(rsvp): correct validation for empty name field
style(nav): adjust mobile menu spacing
content(details): update venue address and parking info
chore(images): compress hero images for faster load time
docs(readme): update getting started instructions
```

> **Rule:** If you can't summarise the change in one line, split it into two commits.

---

## Contributing

Full workflow documentation is available in [`docs/workflow-framework.docx`](docs/workflow-framework.docx) — this covers tool setup, branching strategy, VS Code configuration, and onboarding in detail.

### Quick Checklist Before Every Commit

- [ ] I am on the correct `batch/*` branch (check GitHub Desktop header)
- [ ] My commit message follows the `type(scope): description` format
- [ ] I have saved all files in VS Code (`Ctrl+Shift+S`)
- [ ] The site previews correctly in Live Server with no visible errors
- [ ] I have not committed any personal data, passwords, or guest information

### What NOT to Include in Commits

The `.gitignore` already handles most of this, but as a reminder — never commit:

- Guest RSVP responses or personal data
- API keys or secret tokens
- System files (`Thumbs.db`, `.DS_Store`)
- Large uncompressed images (compress first using [Squoosh](https://squoosh.app))

---

## Deployment

This site is deployed automatically via **GitHub Pages**.

| Trigger | Result |
|---|---|
| Merge to `main` | GitHub Pages rebuilds the live site |
| Build time | ~60–90 seconds |
| Live URL | https://olly-vin.github.io/wedding-tings |
| Custom domain | Configurable via `Settings → Pages → Custom domain` |

### Enabling / Re-enabling GitHub Pages

1. Go to the repo on GitHub.com
2. `Settings → Pages` (left sidebar)
3. Under **Source**: `Deploy from a branch → main → / (root)`
4. Click **Save**

The live URL appears at the top of the Pages settings screen once the first build completes.

---

## Page Status

| Page | File | Status |
|---|---|---|
| Home | `index.html` | ✅ In progress |
| RSVP | `rsvp.html` | ✅ In progress |
| Details | `details.html` | 📋 Planned |
| Our Story | `our-story.html` | 📋 Planned |
| Gallery | `gallery.html` | 📋 Planned |

---

*Built with love — and Git.*