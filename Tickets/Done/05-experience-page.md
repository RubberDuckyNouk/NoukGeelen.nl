# 05 - Experience Page

## Description
Create the Experience page with content migrated from the current WordPress site.

## Tasks
- Migrate all work experience content from noukgeelen.nl/experience
- Structure using Bootstrap components (cards, timeline, or list groups)

## Done when
- All experience information is present and clearly structured

---

## Implementation Steps

### Step 1: Create `pages/experience.html`

The easiest way to start is to **copy `pages/education.html`** and modify it. You already know the subpage structure (nav, main, footer with `../` paths). The only things that change are:

1. The `<title>` tag
2. Which nav link gets `active`
3. The `<main>` content

Create `pages/experience.html` with this content:

```html
<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Experience - Nouk Geelen</title>

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
                        <a class="nav-link" href="education.html">Education</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link active" href="experience.html">Experience</a>
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
        <h1 class="display-5 fw-bold mb-4">Experience</h1>

        <!-- Aardevo card -->
        <div class="card mb-4">
            <div class="card-body">
                <div class="d-flex justify-content-between align-items-start">
                    <div>
                        <h2 class="card-title h5">Assistant Breeder</h2>
                        <h3 class="card-subtitle mb-3 text-muted h6">Aardevo</h3>
                    </div>
                    <span class="badge bg-secondary">April 2023 &ndash; Present</span>
                </div>
                <p class="fst-italic">Supporting research operations through IT solutions</p>
                <ul>
                    <li>Data administration</li>
                    <li>Data processing and visualization with R and PowerBI</li>
                    <li>Identifying which processes can be improved and implementing digital solutions</li>
                    <li>Bridge between breeding research and technical implementation</li>
                </ul>
            </div>
        </div>

        <!-- YellowTwig card -->
        <div class="card mb-4">
            <div class="card-body">
                <div class="d-flex justify-content-between align-items-start">
                    <div>
                        <h2 class="card-title h5">Software Tester</h2>
                        <h3 class="card-subtitle mb-3 text-muted h6">YellowTwig</h3>
                    </div>
                    <span class="badge bg-secondary">2016 &ndash; Present</span>
                </div>
                <p class="fst-italic">Project based software testing and quality control</p>
                <ul>
                    <li>Software testing and quality control across various industries</li>
                    <li>Simple front-end development</li>
                    <li>Working between technical teams and business stakeholders</li>
                </ul>
                <p class="mt-3"><strong>Clients include:</strong> Daklapack, Pr&eacute; Pain, Nooteboom Trailers, RVDB, Brakel, Royal Replubliq</p>
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

**New Bootstrap classes used here (not seen in the education page):**
- `d-flex` — turns the element into a flexbox container, so its children sit side by side
- `justify-content-between` — pushes children to opposite ends (title left, date right)
- `align-items-start` — aligns children to the top (so the badge doesn't drop to the middle if the title wraps)
- `badge bg-secondary` — a small pill-shaped label, used here for the date range. `bg-secondary` gives it a grey background
- `fst-italic` — makes text italic, used for the role summary/tagline
- `&eacute;` — the HTML entity for `é` (in "Pré Pain")

### Step 2: No CSS changes needed

The `.card` border-left styling you added in ticket 04 already applies here too — that's the benefit of styling by class name rather than per-page.

### Step 3: Verify

1. Open `pages/experience.html` in your browser (or click Experience in the nav)
2. You should see **two cards**, each with the job title and company on the left and the date range as a **grey badge** on the right
3. The role summary should appear in *italics* below the heading
4. Check that the **coloured left border** from the card styling appears on both cards
5. Resize narrow — the badge should stay next to the title until the screen gets very small
