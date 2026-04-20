# 13 - Personal Design: Colours & Finishing Touches

## Description
Make the site feel more personal by replacing the default blue palette with a soft green/cream colour scheme (Option C — Soft / Minimal from the mockup in `test/color-mockups.html`).

## Palette (Option C)

| Variable | Value | Purpose |
|----------|-------|---------|
| `--color-primary` | `#7aab8e` | Muted mint — headings, card borders, buttons, badges |
| `--color-accent` | `#f0e0a0` | Soft butter yellow — footer links, subtle highlights |
| `--color-bg` | `#fafaf7` | Warm off-white background |
| `--color-text` | `#3a3a3a` | Softer than pure black for readability |
| `--color-nav-bg` | `#4a7a5e` | Dark green for navbar and footer |

## Tasks
- Update CSS custom properties in `css/style.css`
- Override navbar and footer background colours
- Add card hover effect (lift + shadow)
- Style outline buttons and badges in the new palette
- Update footer link colours

## Done when
- All pages use the new green/cream colour scheme
- Navbar and footer are dark green instead of black
- Cards have a subtle hover animation
- The site feels cohesive and personal

---

## Implementation Steps

### Step 1: Update the CSS custom properties

Open `css/style.css` and replace the `:root` block with the new palette. This is where all your colours live — every rule that uses `var(--color-primary)` will automatically pick up the new value.

```css
:root {
  /* Brand colours — Option C: Soft / Minimal */
  --color-primary: #7aab8e;
  --color-accent: #f0e0a0;
  --color-bg: #fafaf7;
  --color-text: #3a3a3a;
  --color-nav-bg: #4a7a5e;
}
```

**What changed:**
- `--color-primary` went from blue to muted mint green
- `--color-bg` went from pure white to a warm cream — this makes the page feel softer and less sterile
- `--color-text` went from near-black (`#212529`) to a slightly lighter dark (`#3a3a3a`) — easier on the eyes
- Two new variables: `--color-accent` (yellow for small highlights) and `--color-nav-bg` (dark green for the navbar/footer)

You can remove `--color-secondary` since it wasn't being used in any custom rules.

---

### Step 2: Override the navbar background

Bootstrap's `bg-dark` class sets the navbar to near-black. Instead of removing that class from every HTML file, you can override it in CSS for just the navbar.

Add this below your existing `body` rule in `css/style.css`:

```css
/* Navbar — dark green instead of Bootstrap's black */
.navbar {
    background-color: var(--color-nav-bg) !important;
}
```

**Why `!important`?** Bootstrap's `bg-dark` uses `!important` internally, so your override needs it too to win the specificity battle. This is one of the few cases where `!important` is acceptable.

---

### Step 3: Override the footer background

Same idea — the footer currently uses Bootstrap's `bg-dark`. Add this rule:

```css
/* Footer — match the navbar */
footer {
    background-color: var(--color-nav-bg) !important;
}
```

---

### Step 4: Style footer links with the accent colour

The social icons in the footer are currently plain white. Make them pop with the butter yellow accent:

```css
/* Footer social links */
footer a {
    color: var(--color-accent);
    transition: opacity 0.2s;
}

footer a:hover {
    color: var(--color-accent);
    opacity: 0.8;
}
```

**New concept — `transition`:** This tells the browser to animate changes smoothly. `opacity 0.2s` means "when the opacity changes, take 0.2 seconds to do it" — giving links a soft fade effect on hover instead of an abrupt change.

---

### Step 5: Add card hover effect

This makes cards feel interactive — they lift slightly when you hover. Replace your existing `.card` rule:

```css
/* Card styling */
.card {
    border-left: 4px solid var(--color-primary);
    border-top: none;
    border-right: none;
    border-bottom: none;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
    transition: transform 0.2s, box-shadow 0.2s;
}

.card:hover {
    transform: translateY(-3px);
    box-shadow: 0 6px 16px rgba(0, 0, 0, 0.1);
}
```

**New concepts:**
- `box-shadow: 0 2px 8px rgba(0,0,0,0.06)` — adds a subtle shadow beneath the card (x-offset, y-offset, blur-radius, colour). `rgba` lets you set opacity — `0.06` means 6% black, very faint.
- `transform: translateY(-3px)` — moves the card 3 pixels upward on hover, creating a "lift" effect
- `transition: transform 0.2s, box-shadow 0.2s` — animates both properties smoothly over 0.2 seconds

---

### Step 6: Style outline buttons in the new colour

The portfolio page uses `btn-outline-primary` buttons. Bootstrap's default primary is blue, but you can override it:

```css
/* Primary outline buttons — use our green */
.btn-outline-primary {
    color: var(--color-primary);
    border-color: var(--color-primary);
}

.btn-outline-primary:hover {
    background-color: var(--color-primary);
    border-color: var(--color-primary);
    color: #fff;
}
```

This ensures any `btn-outline-primary` button matches your green palette without changing any HTML.

---

### Step 7: Style badges

The tech badges on the portfolio page currently use `bg-secondary` (grey). To make them match the palette:

```css
/* Badges — use primary green */
.badge.bg-secondary {
    background-color: var(--color-primary) !important;
}
```

**Why target `.badge.bg-secondary`?** This only changes badges that have both classes, so date-range badges on other pages (if styled differently) won't be affected unintentionally.

---

### Step 8: Verify

1. Open any page in the browser
2. The navbar and footer should now be **dark green** (`#4a7a5e`)
3. The page background should feel **warm/creamy** (not stark white)
4. Card left borders should be **minted green**
5. Hover over a card — it should **lift slightly** with a deeper shadow
6. Footer social icons should be **soft yellow**
7. Portfolio buttons should be **green outlined**, filling green on hover
8. Check multiple pages — the colours should be consistent everywhere since they all share `style.css`

### Final `css/style.css` for reference

After all steps, your file should look like this:

```css
/* ==========================================================================
   NoukGeelen.nl — Custom Styles
   ========================================================================== */

:root {
  /* Brand colours — Option C: Soft / Minimal */
  --color-primary: #7aab8e;
  --color-accent: #f0e0a0;
  --color-bg: #fafaf7;
  --color-text: #3a3a3a;
  --color-nav-bg: #4a7a5e;
}

/* Basic reset / global defaults */
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

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

/* Navbar — dark green instead of Bootstrap's black */
.navbar {
    background-color: var(--color-nav-bg) !important;
}

/* Footer — match the navbar */
footer {
    background-color: var(--color-nav-bg) !important;
}

/* Footer social links */
footer a {
    color: var(--color-accent);
    transition: opacity 0.2s;
}

footer a:hover {
    color: var(--color-accent);
    opacity: 0.8;
}

/* Hero section */
.display-4 {
    color: var(--color-primary);
}

/* Page titles */
.display-5 {
    color: var(--color-primary);
}

/* Card styling */
.card {
    border-left: 4px solid var(--color-primary);
    border-top: none;
    border-right: none;
    border-bottom: none;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
    transition: transform 0.2s, box-shadow 0.2s;
}

.card:hover {
    transform: translateY(-3px);
    box-shadow: 0 6px 16px rgba(0, 0, 0, 0.1);
}

/* Primary outline buttons — use our green */
.btn-outline-primary {
    color: var(--color-primary);
    border-color: var(--color-primary);
}

.btn-outline-primary:hover {
    background-color: var(--color-primary);
    border-color: var(--color-primary);
    color: #fff;
}

/* Badges — use primary green */
.badge.bg-secondary {
    background-color: var(--color-primary) !important;
}

.fw-sm {
    font-weight: 600;
}

.fs-small {
    font-size: 0.875rem;
}
```
