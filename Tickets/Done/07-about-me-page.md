# 07 - About Me Page

## Description
Create the About Me page with content migrated from the current WordPress site.

## Tasks
- Migrate all personal/about content from noukgeelen.nl/about-me

## Done when
- All about me information is present and clearly laid out

---

## Implementation Steps

### Step 1: Create `pages/about.html`

Copy an existing subpage as your starting point, then change:
1. The `<title>` to "About Me - Nouk Geelen"
2. Move the `active` class to the About Me nav link
3. Replace the `<main>` content with the code below

This page is different from the others — it's more visual and personal. We'll use Bootstrap's **grid system with images** to pair each hobby with a photo, alternating left/right for visual variety.

Replace the entire `<main>...</main>` block with:

```html
    <!-- Main content -->
    <main class="container my-5">
        <h1 class="display-5 fw-bold mb-2">About Me</h1>
        <p class="lead mb-5">I find it easy to discover interest in anything new. Part of that shows in my many hobbies, here are some of them...</p>

        <!-- Climbing -->
        <div class="row align-items-center mb-5">
            <div class="col-md-6">
                <img src="../images/FontaineClimbing.jpg" alt="Climbing in Fontainebleau"
                     class="img-fluid rounded">
            </div>
            <div class="col-md-6 mt-3 mt-md-0">
                <h2 class="h4">Climbing</h2>
                <p>From the many sports I have tried, climbing is the perfect one for me. I love how it mixes adrenaline and puzzles. And when I get the chance to look over a mountain landscape, I feel completely at peace.</p>
            </div>
        </div>

        <!-- Baking & Painting -->
        <div class="row align-items-center mb-5 flex-md-row-reverse">
            <div class="col-md-6">
                <img src="../images/CatchingBugs.jpg" alt="Baking and painting"
                     class="img-fluid rounded">
            </div>
            <div class="col-md-6 mt-3 mt-md-0">
                <h2 class="h4">Baking &amp; Painting</h2>
                <p>I love baking, I continuously challenge myself to try new recipes and designs. I also paint, and cake decorating is like a challenging three dimensional canvas.</p>
            </div>
        </div>

        <!-- Outdoor Sports -->
        <div class="row align-items-center mb-5">
            <div class="col-md-6">
                <img src="../images/Kajak.jpeg" alt="Kayaking"
                     class="img-fluid rounded">
            </div>
            <div class="col-md-6 mt-3 mt-md-0">
                <h2 class="h4">Outdoor Sports</h2>
                <p>I enjoy every sport that brings me into nature, including hiking, cycling, and kayaking.</p>
            </div>
        </div>

        <!-- Flying -->
        <div class="row align-items-center mb-5 flex-md-row-reverse">
            <div class="col-md-6">
                <img src="../images/DA40Texel.png" alt="Flying"
                     class="img-fluid rounded">
            </div>
            <div class="col-md-6 mt-3 mt-md-0">
                <h2 class="h4">Flying</h2>
                <p>Though not quite the rush and view that a mountaintop gives, I also enjoy flying and how it combines the calm of the sky and excitement of the science to fly.</p>
            </div>
        </div>
    </main>
```

**New Bootstrap class used here:**
- `flex-md-row-reverse` — reverses the column order on medium+ screens. This makes the image appear on the **right** instead of the left, creating an alternating zigzag layout. On small screens the columns still stack normally (image on top, text below)

**Image choices from your `images/` folder:**
- `FontaineClimbing.jpg` for climbing
- `CatchingBugs.jpg` for baking & painting (swap this if you have a more fitting image)
- `Kajak.jpeg` for outdoor sports
- `DA40Texel.png` for flying

Feel free to swap any image — just change the `src` path and `alt` text to match.

### Step 2: No CSS changes needed

The existing styles handle everything. The `img-fluid` class makes images responsive and `rounded` adds subtle corner rounding.

### Step 3: Verify

1. Open `pages/about.html` in your browser
2. You should see an **intro paragraph** followed by four hobby sections
3. The sections should **alternate** — image left/text right, then image right/text left
4. Resize narrow — images and text should **stack vertically**
5. Check that all four images load correctly. If one doesn't, double-check the filename and extension match exactly (case-sensitive on some servers)
