# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static personal portfolio website for Nouk Geelen, being migrated from WordPress (noukgeelen.nl) to plain HTML/CSS with Bootstrap 5. There is no build step, bundler, or JavaScript framework — just open `index.html` in a browser.

## Tech Stack

- **HTML5** + **CSS3** (no templating engine)
- **Bootstrap 5.3** via CDN (CSS + JS bundle)
- **Custom CSS** in `css/style.css` using CSS custom properties (`:root` variables)
- No build tools, no package manager, no server-side code

## Architecture

- `index.html` — home page (root level)
- `pages/*.html` — subpages (education, experience, skills, etc.)
- `css/style.css` — all custom styles; Bootstrap handles the heavy lifting
- `images/` — static image assets
- Each page is a standalone HTML file that duplicates the full nav/footer (no includes or templating)
- Nav links from subpages use `../index.html` to reach home; from root use `pages/xyz.html`

## Ticket Workflow

Work is tracked via markdown files in `Tickets/`:
- `Tickets/ToDo/` — upcoming work
- `Tickets/Done/` — completed tickets
- Active ticket lives at `Tickets/` root (e.g. `Tickets/04-education-page.md`)
- Each ticket branch is named after the ticket number (e.g. `04-education-page`)
- Completed tickets include an **Implementation Steps** section with step-by-step instructions and code snippets that explain *what to do* and *why* (Bootstrap classes, CSS properties). This is a learning project — the instructions teach HTML/CSS/Bootstrap concepts.

## Important: Hands-Off Coding

The user writes all code themselves to learn. Claude's role is to **add implementation instructions and code snippets to the ticket markdown files** — never edit the HTML, CSS, or JS source files directly. Only modify ticket `.md` files when asked.

## Git Conventions

- Branch per ticket: `XX-feature-name` (e.g. `04-education-page`)
- Remote is named `GitHub`
- PRs merge into `main`
