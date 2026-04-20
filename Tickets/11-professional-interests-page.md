# 11 - Professional Interests Page

## Description
Create a Professional Interests page where I showcase topics and technologies I want to learn more about. This page highlights curiosity and growth areas rather than existing skills.

## Tasks
- Build a Professional Interests page layout
- Include sections or cards for topics I want to explore further
- Keep the structure easy to update as interests evolve

## Implementation Steps

### Step 1 — Create the file and copy the page skeleton

Create a new file `pages/interests.html`. Copy the full structure from an existing page like `about.html` — the `<!DOCTYPE>`, `<head>`, nav, footer, and Bootstrap script tag.

Change these parts:
- `<title>` → `Professional Interests - Nouk Geelen`
- In the nav, move the `active` class to the Professional Interests link:
  ```html
  <a class="nav-link active" href="interests.html">Professional Interests</a>
  ```
  And remove `active` from whichever page you copied from.

### Step 2 — Replace the `<main>` content

Delete everything inside `<main>...</main>` and paste this:

```html
<!-- Main content -->
<main class="container my-5">
    <h1 class="display-5 fw-bold mb-2">Professional Interests</h1>
    <p class="lead mb-5">Skills and areas I want to develop and grow in.</p>

    <!-- Agile Project Management -->
    <div class="card mb-4">
        <div class="card-body">
            <h2 class="card-title h5">Agile Project Management</h2>
            <p>
                Moving beyond task-level Agile into the bigger picture: learning
                how to set up projects from scratch, motivate teams to adopt Agile
                efficiently, and handle the details and nuances of project leadership.
            </p>
        </div>
    </div>

    <!-- Bridging Business and Development -->
    <div class="card mb-4">
        <div class="card-body">
            <h2 class="card-title h5">Bridging Business and Development</h2>
            <p>
                Becoming the person who can translate business needs into technical
                requirements. Learning to code to understand what's feasible so I
                can have informed conversations with developers about what to ask
                and expect.
            </p>
        </div>
    </div>

    <!-- User-Centered Thinking -->
    <div class="card mb-4">
        <div class="card-body">
            <h2 class="card-title h5">User-Centered Thinking</h2>
            <p>
                Developing the skill of putting myself in the end user's shoes to
                identify unique requirements. I want to apply this across a variety
                of projects and domains.
            </p>
        </div>
    </div>

    <!-- Scripting & Automation -->
    <div class="card mb-4">
        <div class="card-body">
            <h2 class="card-title h5">Scripting &amp; Automation</h2>
            <p>
                Building practical coding skills to support my work — not to become
                a full developer, but to be able to automate tasks and work more
                efficiently.
            </p>
        </div>
    </div>

    <!-- Automated Testing -->
    <div class="card mb-4">
        <div class="card-body">
            <h2 class="card-title h5">Automated Testing</h2>
            <p>
                Learning to write test scripts for automated testing to improve
                quality assurance processes.
            </p>
        </div>
    </div>

    <!-- Team Leadership -->
    <div class="card mb-4">
        <div class="card-body">
            <h2 class="card-title h5">Team Leadership</h2>
            <p>
                Learning how to foster tight collaboration with constant
                communication and transparent, well-structured task management
                so work can flow smoothly across a team.
            </p>
        </div>
    </div>
</main>
```

This uses the same card layout as the Skills page — stacked full-width cards with a primary-coloured left border (from your existing `.card` rule in `style.css`).

### Step 3 — Test your page

Open `pages/interests.html` in your browser and verify:
- The nav highlights "Professional Interests" as active
- All six cards display with the blue left border
- The footer sticks to the bottom
- The page looks good on mobile (resize your browser to check)

## Done when
- Professional Interests page exists at `pages/interests.html` with a clean layout for listing learning goals and areas of interest
