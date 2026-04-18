# 03 - Home Page

## Description
Create the landing page (`index.html`) based on the current WordPress home page.

## Content to migrate
- Name / heading
- Tagline: "Passionate about IT and people, I aim to continually learn and grow."
- Profile photo

## Tasks
- Build a clean hero section with name, tagline, and photo
- Ensure it looks good on both desktop and mobile

## Done when
- Home page displays all current content in a clean layout

---

## Implementation Steps

### Step 1: Add a profile photo

Place your profile photo in the `images/` folder. Name it `profile.jpg` (or `.png` — just adjust the filename in the code below).

### Step 2: Replace the `<main>` content in `index.html`

Find lines 59-63 (the `<main>...</main>` block) and replace them with:

```html
    <!-- Main content -->
    <main class="container my-5">
        <div class="row align-items-center">
            <!-- Text column -->
            <div class="col-md-7">
                <h1 class="display-4 fw-bold">Nouk Geelen</h1>
                <p class="lead mt-3">Passionate about IT and people, I aim to continually learn and grow.</p>
            </div>

            <!-- Photo column -->
            <div class="col-md-5 text-center mt-4 mt-md-0">
                <img src="images/profile.jpg" alt="Nouk Geelen"
                     class="img-fluid rounded-circle" style="max-width: 280px;">
            </div>
        </div>
    </main>
```

**What's happening here:**
- `row` — creates a Bootstrap grid row so we can place text and photo side by side
- `col-md-7` and `col-md-5` — on medium screens and up, text takes 7/12 of the width, photo takes 5/12. On small screens they stack vertically (full width each)
- `display-4` — a large, prominent heading style from Bootstrap
- `fw-bold` — makes the heading bold
- `lead` — slightly larger paragraph text, good for taglines
- `mt-3` — margin-top on the tagline for spacing
- `img-fluid` — makes the image responsive (scales down on smaller screens)
- `rounded-circle` — crops the image into a circle
- `mt-4 mt-md-0` — adds top margin on small screens (when stacked) but removes it on medium+ screens (when side by side)

### Step 3: Add hero section styling to `css/style.css`

Add this at the bottom of your `style.css` file:

```css
/* Hero section */
.display-4 {
    color: var(--color-primary);
}
```

This colors your name heading with the primary brand color. Feel free to change `--color-primary` in the `:root` block at the top of the file to any color you like.

### Step 4: Verify

1. Refresh the page in your browser
2. You should see your **name** in large text on the left, **tagline** below it, and **photo** on the right
3. Resize the browser narrow — the photo should drop **below** the text
4. If the photo doesn't show, double-check the filename matches exactly (including the extension `.jpg` vs `.png`)
