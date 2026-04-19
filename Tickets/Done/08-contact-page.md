# 08 - Contact Page

## Description
Create the Contact page with content migrated from the current WordPress site.

## Tasks
- Migrate contact details from noukgeelen.nl/contact
- Display contact information clearly (email, LinkedIn, etc.)

## Done when
- All contact information is accessible and clearly displayed

---

## Implementation Steps

### Step 1: Create `pages/contact.html`

Copy an existing subpage as your starting point, then change:
1. The `<title>` to "Contact - Nouk Geelen"
2. Move the `active` class to the Contact nav link
3. Replace the `<main>` content with the code below

Replace the entire `<main>...</main>` block with:

```html
    <!-- Main content -->
    <main class="container my-5">
        <h1 class="display-5 fw-bold mb-2">Get in Touch</h1>
        <p class="lead mb-5">Feel free to reach out through any of the channels below.</p>

        <div class="d-flex flex-column flex-sm-row gap-3">
            <a href="https://www.linkedin.com/in/nouk-g-1718b9170/" target="_blank" rel="noopener"
               class="btn btn-primary btn-lg">
                LinkedIn
            </a>
            <a href="https://github.com/RubberDuckyNouk" target="_blank" rel="noopener"
               class="btn btn-dark btn-lg">
                GitHub
            </a>
        </div>
    </main>
```

**New concepts used here:**

**Button classes:**
- `btn` — base Bootstrap button class, turns any element (including `<a>` links) into a styled button
- `btn-primary` — uses the primary colour (blue) for LinkedIn
- `btn-dark` — dark/black button for GitHub
- `btn-lg` — larger button size for better visibility

**Layout:**
- `d-flex` — flexbox container for the buttons
- `flex-column` — stacks buttons vertically by default (small screens)
- `flex-sm-row` — switches to side by side on small screens and up
- `gap-3` — adds spacing between the buttons without needing margin classes on each one
- `target="_blank"` — opens the link in a new browser tab
- `rel="noopener"` — security attribute you should always pair with `target="_blank"`, prevents the new page from accessing your page via JavaScript

### Step 2: Add icon links to the footer on all pages

First, add the Bootstrap Icons CDN link in the `<head>` of **every page** (`index.html` and all pages in `pages/`), after the Bootstrap CSS link:

```html
    <!-- Bootstrap Icons -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.min.css">
```

Then, on **every page**, replace the `<footer>...</footer>` block with:

```html
    <!-- Footer -->
    <footer class="bg-dark text-white text-center py-4 mt-auto">
        <div class="container">
            <p class="mb-1">Nouk Geelen</p>
            <div class="mb-2">
                <a href="https://www.linkedin.com/in/nouk-g-1718b9170/" target="_blank" rel="noopener"
                   class="text-white me-3 fs-5">
                    <i class="bi bi-linkedin"></i>
                </a>
                <a href="https://github.com/RubberDuckyNouk" target="_blank" rel="noopener"
                   class="text-white fs-5">
                    <i class="bi bi-github"></i>
                </a>
            </div>
            <small>Subtitle placeholder text.</small>
        </div>
    </footer>
```

**Bootstrap Icons concepts:**
- Loaded via CDN in the `<head>`, just like Bootstrap itself
- `<i class="bi bi-linkedin">` — inserts the LinkedIn icon. `bi` is the base class, `bi-linkedin` picks the specific icon
- `bi-github` — the GitHub icon
- You can browse all available icons at https://icons.getbootstrap.com

**Styling on the icon links:**
- `text-white` — makes the icon white to match the dark footer
- `fs-5` — font-size class, makes the icons slightly larger than default text so they're easy to tap/click
- `me-3` — margin-end (right margin) to add spacing between the two icons

**Important:** Remember to update the footer on **all** existing pages — `index.html`, `education.html`, `experience.html`, `skills.html`, and `about.html`. The footer is duplicated in each file, so each one needs the same change.

### Step 3: Verify

1. Open `pages/contact.html` — you should see two text **buttons** (blue LinkedIn, dark GitHub)
2. Scroll to the footer — you should see **LinkedIn and GitHub icons** between your name and the subtitle
3. Click the icons — they should open in a **new tab**
4. Check the footer on **another page** (e.g. `index.html`) to make sure the icons appear there too
