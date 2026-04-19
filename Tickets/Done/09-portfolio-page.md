# 09 - Portfolio Page

## Description
Create a new Portfolio page to showcase personal projects. This page does not exist on the current WordPress site.

## Tasks
- Build a portfolio page layout using Bootstrap cards or a grid
- Set up a structure that is easy to extend with new projects later

## Implementation Steps

### Step 1 — Create the file and copy the page skeleton

Create a new file `pages/portfolio.html`. Copy the full structure from an existing page like `about.html` — the `<!DOCTYPE>`, `<head>`, nav, footer, and Bootstrap script tag. This gives you the same boilerplate every page shares.

Change these parts to make it yours:
- `<title>` → `Portfolio - Nouk Geelen`
- In the nav, move the `active` class to the Portfolio link:
  ```html
  <a class="nav-link active" href="portfolio.html">Portfolio</a>
  ```
  And remove `active` from the About Me link.

### Step 2 — Replace the `<main>` content

Delete everything inside `<main>...</main>` that you copied and paste this:

```html
<!-- Main content -->
<main class="container my-5">
    <h1 class="display-5 fw-bold mb-2">Portfolio</h1>
    <p class="lead mb-5">A collection of projects I have worked on.</p>

    <div class="row g-4">

        <!-- NoukGeelen.nl -->
        <div class="col-md-6 col-lg-4">
            <div class="card h-100">
                <div class="card-body d-flex flex-column">
                    <h2 class="card-title h5">NoukGeelen.nl</h2>
                    <p class="card-text">
                        My personal portfolio website, hand-built with plain HTML, CSS
                        and Bootstrap 5 to learn front-end web development from scratch.
                    </p>

                    <!-- TODO: describe your thought process / methodology -->
                    <!-- For example: why you chose plain HTML over a framework,
                         what you learned about responsive design, how you
                         structured the project with tickets, etc. -->

                    <div class="mt-auto">
                        <span class="badge bg-secondary me-1 mb-1">HTML</span>
                        <span class="badge bg-secondary me-1 mb-1">CSS</span>
                        <span class="badge bg-secondary me-1 mb-1">Bootstrap 5</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- InventoryTracker -->
        <div class="col-md-6 col-lg-4">
            <div class="card h-100">
                <div class="card-body d-flex flex-column">
                    <h2 class="card-title h5">Inventory Tracker</h2>
                    <p class="card-text">
                        A desktop application for tracking tube locations across
                        drawers by program. Features live search, bulk move
                        operations, barcode scanner support, and a configurable
                        drawer grid layout.
                    </p>

                    <!-- TODO: describe your thought process / methodology -->
                    <!-- For example: why you chose a desktop app over a web app,
                         how you designed the data model with CSV storage,
                         challenges you solved, etc. -->

                    <div class="mt-auto">
                        <span class="badge bg-secondary me-1 mb-1">Python</span>
                        <span class="badge bg-secondary me-1 mb-1">CustomTkinter</span>
                        <span class="badge bg-secondary me-1 mb-1">CSV</span>
                        <span class="badge bg-secondary me-1 mb-1">PyInstaller</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- TableFootballScoreTracker -->
        <div class="col-md-6 col-lg-4">
            <div class="card h-100">
                <div class="card-body d-flex flex-column">
                    <h2 class="card-title h5">Table Football Score Tracker</h2>
                    <p class="card-text">
                        A web application for tracking table football scores with
                        ELO ratings, multi-office support, statistics dashboards
                        and shareable QR-code invites.
                    </p>

                    <!-- TODO: describe your thought process / methodology -->
                    <!-- For example: how you designed the ELO system, why you
                         picked Express + PostgreSQL, what you learned about
                         full-stack development, etc. -->

                    <div class="mt-auto mb-2">
                        <a href="https://tablefootballscoretracker.onrender.com" target="_blank" rel="noopener"
                           class="btn btn-sm btn-outline-primary me-2">
                            Go to app <i class="bi bi-box-arrow-up-right"></i>
                        </a>
                        <a href="https://github.com/RubberDuckyNouk/TableFootballScoreTracker" target="_blank" rel="noopener"
                           class="btn btn-sm btn-outline-secondary">
                            <i class="bi bi-github"></i> GitHub
                        </a>
                    </div>
                    <div>
                        <span class="badge bg-secondary me-1 mb-1">JavaScript</span>
                        <span class="badge bg-secondary me-1 mb-1">Node.js</span>
                        <span class="badge bg-secondary me-1 mb-1">Express</span>
                        <span class="badge bg-secondary me-1 mb-1">PostgreSQL</span>
                        <span class="badge bg-secondary me-1 mb-1">Bootstrap 5</span>
                        <span class="badge bg-secondary me-1 mb-1">Chart.js</span>
                    </div>
                </div>
            </div>
        </div>

    </div>
</main>
```

**Key classes explained:**
- `row g-4` — flex row with `1.5rem` gutters between cards.
- `col-md-6 col-lg-4` — 1 column on mobile, 2 on medium, 3 on large screens.
- `card h-100` — `h-100` makes all cards in a row equal height.
- `d-flex flex-column` + `mt-auto` — pushes the tech badges to the bottom of each card so they align across cards with different amounts of text.

Each card has a `<!-- TODO -->` comment where you can fill in your thought process and methodology. You can turn those into a `<p>` or a `<ul>` — whatever feels right.

### Step 3 — Test your page

Open `pages/portfolio.html` in your browser (or via live-server) and verify:
- The nav highlights "Portfolio" as active
- Cards display side-by-side on wider screens and stack on mobile
- All cards are the same height (the `h-100` class)
- The footer sticks to the bottom of the page

Try resizing your browser window to see the responsive breakpoints in action.

## Done when
- Portfolio page exists with a clean, extensible layout ready for project content
