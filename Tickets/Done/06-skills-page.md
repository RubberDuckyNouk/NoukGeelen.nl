# 06 - Skills Page

## Description
Create the Skills page with content migrated from the current WordPress site.

## Tasks
- Migrate all skills content from noukgeelen.nl/skills
- Present skills in a clean visual format (e.g. Bootstrap badges, progress bars, or grouped cards)

## Done when
- All skills are displayed clearly and are easy to scan

---

## Implementation Steps

### Step 1: Create `pages/skills.html`

Copy `pages/education.html` (or `experience.html`) as your starting point, then change:
1. The `<title>` to "Skills - Nouk Geelen"
2. Move the `active` class to the Skills nav link
3. Replace the `<main>` content with the code below

Replace the entire `<main>...</main>` block with:

```html
    <!-- Main content -->
    <main class="container my-5">
        <h1 class="display-5 fw-bold mb-4">Skills</h1>

        <!-- Technical Skills -->
        <div class="card mb-4">
            <div class="card-body">
                <h2 class="card-title h5">Technical Skills</h2>
                <p>Experienced with R, DAX and Power Query used with PowerBI for data processing and visualization. Basic understanding of SQL, JSON, XML, HTML, CSS, JavaScript and Python. Hands-on experience with software testing, quality control and simple web development.</p>
                <div class="mt-3">
                    <span class="badge bg-primary me-1 mb-1">R</span>
                    <span class="badge bg-primary me-1 mb-1">DAX</span>
                    <span class="badge bg-primary me-1 mb-1">Power Query</span>
                    <span class="badge bg-primary me-1 mb-1">PowerBI</span>
                    <span class="badge bg-secondary me-1 mb-1">SQL</span>
                    <span class="badge bg-secondary me-1 mb-1">JSON</span>
                    <span class="badge bg-secondary me-1 mb-1">XML</span>
                    <span class="badge bg-secondary me-1 mb-1">HTML</span>
                    <span class="badge bg-secondary me-1 mb-1">CSS</span>
                    <span class="badge bg-secondary me-1 mb-1">JavaScript</span>
                    <span class="badge bg-secondary me-1 mb-1">Python</span>
                    <span class="badge bg-secondary me-1 mb-1">Software testing &amp; QC</span>
                    <span class="badge bg-secondary me-1 mb-1">Web development</span>
                </div>
            </div>
        </div>

        <!-- Methodologies & Tools -->
        <div class="card mb-4">
            <div class="card-body">
                <h2 class="card-title h5">Methodologies &amp; Tools</h2>
                <p>Experience working with Agile methodologies using Jira and DevOps. Version control with Git in a collaborative team setting.</p>
                <div class="mt-3">
                    <span class="badge bg-primary me-1 mb-1">Agile</span>
                    <span class="badge bg-primary me-1 mb-1">Jira</span>
                    <span class="badge bg-primary me-1 mb-1">DevOps</span>
                    <span class="badge bg-primary me-1 mb-1">Git</span>
                </div>
            </div>
        </div>

        <!-- Languages -->
        <div class="card mb-4">
            <div class="card-body">
                <h2 class="card-title h5">Languages</h2>
                <p>Multilingual professional comfortable working in Dutch and English environments.</p>
                <div class="mt-3">
                    <span class="badge bg-primary me-1 mb-1">Dutch &ndash; Native</span>
                    <span class="badge bg-primary me-1 mb-1">English &ndash; Near native</span>
                    <span class="badge bg-secondary me-1 mb-1">German &ndash; A2</span>
                    <span class="badge bg-secondary me-1 mb-1">French &ndash; A1</span>
                </div>
            </div>
        </div>
    </main>
```

**New Bootstrap classes used here:**
- `me-1` — margin-end (right margin), adds a small gap between badges so they don't touch each other
- `mb-1` — margin-bottom on each badge, so when badges wrap onto the next line there's spacing between rows too
- `badge bg-primary` / `badge bg-secondary` — coloured pill labels. `bg-primary` (blue) is used for experienced/strong skills, `bg-secondary` (grey) for basic level — giving a quick visual distinction between proficiency levels

**Layout approach:**
- Instead of a three-column grid, this uses **stacked full-width cards** (same layout as education and experience). Each card has a description paragraph providing context, followed by a row of inline badges. This fills the page better and gives the reader useful context about how you actually use these skills.

### Step 2: No CSS changes needed

The existing card styling from ticket 04 applies here too.

### Step 3: Verify

1. Open `pages/skills.html` in your browser
2. You should see **three stacked cards** — Technical Skills, Methodologies & Tools, and Languages
3. Each card has a **description paragraph** followed by **inline badges** that wrap naturally
4. Badges should be **blue** for experienced skills and **grey** for basic ones
5. Resize narrow — the badges should **wrap** to fit the screen width
