# 04 - Education Page

## Description
Create the Education page with content migrated from the current WordPress site.

## Tasks
- Migrate all education content from noukgeelen.nl/education
- Structure using Bootstrap components (cards, timeline, or list groups)

## Done when
- All education information is present and clearly structured

---

## Implementation Steps

### Step 1: Create `pages/education.html`

This is the first subpage you're creating. It follows the same structure as `index.html` (nav + main + footer), but the paths to CSS, images, and other pages are adjusted because this file lives one folder deeper (`pages/`).

Create a new file `pages/education.html` with this content:

```html
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Education - Nouk Geelen</title>

    <!-- Bootstrap 5 CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
          rel="stylesheet">

    <!-- Custom stylesheet -->
    <link rel="stylesheet" href="../css/style.css">
</head>
<body>

    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
        <div class="container">
            <a class="navbar-brand" href="../index.html">Nouk Geelen</a>

            <button class="navbar-toggler" type="button"
                    data-bs-toggle="collapse" data-bs-target="#mainNav"
                    aria-controls="mainNav" aria-expanded="false"
                    aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="mainNav">
                <ul class="navbar-nav ms-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="../index.html">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link active" href="education.html">Education</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="experience.html">Experience</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="skills.html">Skills</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="interests.html">Professional Interests</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="about.html">About Me</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="portfolio.html">Portfolio</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="contact.html">Contact</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Main content -->
    <main class="container my-5">
        <h1 class="display-5 fw-bold mb-4">Education</h1>

        <!-- Degree card -->
        <div class="card mb-4">
            <div class="card-body">
                <h2 class="card-title h5">HBO Bachelor Applied Biology</h2>
                <h3 class="card-subtitle mb-3 text-muted h6">Aeres University of Applied Sciences Almere</h3>

                <p><strong>Major:</strong> Applied Biology</p>
                <p><strong>Specialization:</strong> Plant</p>
                <p><strong>Minor:</strong> Plant Breeding</p>

                <h4 class="h6 fw-bold mt-4">Final Thesis</h4>
                <p>Fungal resistance in petunia &ndash; Syngenta Flowers</p>

                <h4 class="h6 fw-bold mt-4">Internships</h4>
                <ul>
                    <li>City ecology &ndash; Gemeente Lelystad</li>
                    <li>Plant breeding &ndash; Park Amaryllis</li>
                    <li>Phytopathology &ndash; Syngenta Flowers</li>
                </ul>
            </div>
        </div>

        <!-- Training & Courses card -->
        <div class="card mb-4">
            <div class="card-body">
                <h2 class="card-title h5">Training &amp; Courses</h2>
                <ul>
                    <li>KWS Breeding Course: Innovating Together! (experimental design and data analyses)</li>
                    <li>Effectief communiceren (communicating effectively) &ndash; YEARTH academy</li>
                </ul>
            </div>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-dark text-white text-center py-4 mt-auto">
        <div class="container">
            <p class="mb-1">Nouk Geelen</p>
            <small>Subtitle placeholder text.</small>
        </div>
    </footer>

    <!-- Bootstrap 5 JS bundle -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

**Key differences from `index.html`:**
- All paths go **one level up** with `../` — the CSS link is `../css/style.css`, the home link is `../index.html`
- The `active` class has moved from Home to **Education** in the nav
- Links to sibling pages (experience, skills, etc.) are just the filename (e.g. `experience.html`) since they're in the same `pages/` folder

**What the Bootstrap classes do:**
- `card` — a bordered box with padding, good for grouping related content
- `card-body` — the padded inner area of the card
- `card-title` — styles the main heading inside a card
- `card-subtitle` — a lighter secondary heading, used here for the minor
- `text-muted` — grey text to visually de-emphasise the subtitle
- `h5`, `h6` — Bootstrap sizing classes that control heading size without changing the HTML heading level
- `display-5` — large page heading (slightly smaller than `display-4` used on the home page)
- `mb-4` — margin-bottom for spacing between the heading and the card
- `mt-3` — margin-top to space out subsections
- `&amp;` — the HTML entity for `&`, required inside HTML content (similarly `&ndash;` produces an en-dash `–`)

### Step 2: Add education page styling to `css/style.css`

Add this at the bottom of your `style.css` file:

```css
/* Education page */
.card {
    border-left: 4px solid var(--color-primary);
}
```

**What's happening here:**
- Adds a coloured left border to cards, giving a visual accent that ties in with the site's primary colour
- Using `var(--color-primary)` keeps it consistent with the rest of the site — if you change the colour in `:root`, this updates too

### Step 3: Verify

1. Open `pages/education.html` directly in your browser (or navigate via the Education link on the home page)
2. You should see the **dark navbar** at the top with "Education" highlighted
3. Below it, a **card** with a coloured left border containing the education details
4. The **footer** should sit at the bottom
5. Click **Home** in the nav — it should take you back to `index.html`
6. Resize the browser narrow — everything should stack and the hamburger menu should work

### Step 4: Personalise (optional)

The content above matches your CV. Feel free to:
- Add years (e.g. "2018 – 2022") to the degree heading
- Add more detail or descriptions to the internships
- Add more `card` blocks if you have additional entries (e.g. secondary school)
