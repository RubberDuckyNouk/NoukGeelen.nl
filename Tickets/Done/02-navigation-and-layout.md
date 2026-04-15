# 02 - Navigation & Shared Layout

## Description
Build the shared header with navigation bar and footer that will be consistent across all pages.

## Pages to link
- Home
- Education
- Experience
- Skills
- About Me
- Portfolio
- Contact

## Tasks
- Create a responsive Bootstrap navbar with links to all pages
- Create a simple footer
- Apply a clean, consistent color scheme

## Done when
- Navigation is responsive (collapses on mobile)
- All page links are in place
- Footer is present on all pages

---

## Implementation Steps

### Step 1: Replace the `<nav>` in `index.html`

Find the placeholder `<nav>` block (lines 19-24) and replace it with:

```html
  <!-- Navigation -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container">
      <a class="navbar-brand" href="index.html">Nouk Geelen</a>

      <!-- Hamburger button (shows on small screens) -->
      <button class="navbar-toggler" type="button"
              data-bs-toggle="collapse" data-bs-target="#mainNav"
              aria-controls="mainNav" aria-expanded="false"
              aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <!-- Links (collapse into hamburger on small screens) -->
      <div class="collapse navbar-collapse" id="mainNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link active" href="index.html">Home</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="pages/education.html">Education</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="pages/experience.html">Experience</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="pages/skills.html">Skills</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="pages/about.html">About Me</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="pages/portfolio.html">Portfolio</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="pages/contact.html">Contact</a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
```

**What's happening here:**
- `navbar-expand-lg` — links show normally on large screens, collapse into a hamburger on smaller ones
- `navbar-dark bg-dark` — dark background with white text
- `data-bs-toggle="collapse"` + `data-bs-target="#mainNav"` — tells Bootstrap the button toggles the menu
- `ms-auto` on the `<ul>` — pushes nav links to the right
- `active` on the Home link — highlights the current page (move this class to the correct link on each page)

### Step 2: Replace the `<footer>` in `index.html`

Find the placeholder `<footer>` block (lines 32-37) and replace it with:

```html
  <!-- Footer -->
  <footer class="bg-dark text-white text-center py-4 mt-auto">
    <div class="container">
      <p class="mb-1">Nouk Geelen</p>
      <small>&copy; 2026 Nouk Geelen. All rights reserved.</small>
    </div>
  </footer>
```

**What's happening here:**
- `bg-dark text-white` — matches the navbar for consistency
- `py-4` — vertical padding for spacing
- `mt-auto` — pushes the footer to the bottom if page content is short
- `mb-1` — small bottom margin on the name

### Step 3: Update `css/style.css` — sticky footer layout

Merge these properties into the existing `body` rule and add a `main` rule below it. The body block should become:

```css
body {
  color: var(--color-text);
  background-color: var(--color-bg);
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

main {
  flex: 1;
}
```

**What's happening here:**
- `display: flex` + `flex-direction: column` — stacks nav, main, footer vertically
- `min-height: 100vh` — body fills at least the full screen height
- `flex: 1` on `main` — main content stretches to fill available space, pushing footer down

### Step 4: Verify

1. Open `index.html` in your browser
2. You should see a **dark navbar** at the top with all 7 links
3. Resize the browser narrow — links should collapse into a **hamburger icon**. Click it to toggle the menu
4. The **footer** should sit at the bottom of the page
5. The nav links (Education, Experience, etc.) won't work yet — those pages don't exist. That's expected!
