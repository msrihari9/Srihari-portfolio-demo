# portfolio-demo2

A static personal portfolio website for **Srihari Mogalapalli — Data & AI Leader**, built with plain
HTML, CSS, and JavaScript (no build tools required) so it can be published directly on
**GitHub Pages**.

## Folder structure

```
portfolio-demo2/
├── index.html          # Main single-page site (all sections)
├── 404.html             # Custom "page not found" page
├── .nojekyll             # Tells GitHub Pages to skip Jekyll processing
├── css/
│   └── styles.css       # All site styling (light + dark theme)
├── js/
│   └── main.js          # Theme toggle, mobile nav, scroll reveal, back-to-top
├── images/
│   ├── profile-photo.svg    # Placeholder avatar — replace with your real photo
│   ├── favicon.svg
│   └── projects/             # Icons used on project cards
├── resume/
│   ├── resume.html      # Printable résumé (Print → Save as PDF)
│   └── README.md
└── temp/
    └── README.md         # Scratch space for drafts, not linked from the live site
```

## Sections included on the site

Home/Hero, About, Experience (timeline), Skills, Projects, Achievements, Certifications,
and Contact (with a mailto-based contact form) — every section is fully populated with
sample content so nothing is left blank.

## Before you publish: personalize the content

All content is placeholder/sample data meant to be replaced with your real details:

1. **Photo** — replace [images/profile-photo.svg](images/profile-photo.svg) with your real photo.
   Keep the filename `profile-photo` (you can use `.jpg`/`.png` — just update the `src`
   references in [index.html](index.html) and [resume/resume.html](resume/resume.html) accordingly),
   or simply overwrite the file with a same-named raster image and update the extension.
2. **Bio** — update the About, Experience, and Summary text in `index.html` and
   `resume/resume.html` to reflect your real background.
3. **Experience** — update company names, titles, dates, and bullet points in the
   `#experience` timeline and in `resume/resume.html` to reflect your real career history.
4. **Skills / Projects / Achievements / Certifications** — edit the sample entries to match
   your real expertise, portfolio projects, and credentials.
5. **Contact details** — update phone, LinkedIn, and GitHub links in the `#contact` section
   (the email is pre-filled with the address you provided). The contact form currently
   submits via `mailto:`; for a production-grade form, wire it up to a service such as
   [Formspree](https://formspree.io) or [Netlify Forms](https://www.netlify.com/products/forms/).
6. **Resume PDF** — open [resume/resume.html](resume/resume.html) in a browser and use
   "Print / Save as PDF" to generate a downloadable PDF, then drop it into `resume/` and
   link to it directly if preferred over the HTML version.

## Running locally

No build step is required — just open `index.html` in a browser, or serve the folder with
any static file server, e.g.:

```bash
# Python
python -m http.server 8080

# Node
npx serve .
```

Then visit `http://localhost:8080`.

## Deploying to GitHub Pages

1. Create a new GitHub repository (e.g. `portfolio-demo2` or `your-username.github.io`).
2. Push the contents of this folder to the repository root:
   ```bash
   cd portfolio-demo2
   git init
   git add .
   git commit -m "Initial portfolio site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. In the repository on GitHub, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/ (root)`, then click **Save**.
6. GitHub will publish the site at:
   - `https://<your-username>.github.io/<repo-name>/` (project repo), or
   - `https://<your-username>.github.io/` (if the repo is named `<your-username>.github.io`).
7. Wait 1–2 minutes for the first deployment, then visit the URL to confirm it's live.

The included `.nojekyll` file prevents GitHub Pages' default Jekyll processing from
interfering with folders/files that start with an underscore or otherwise conflict with
Jekyll conventions — safe to keep even though this site doesn't use any.

## Tech notes

- Pure HTML/CSS/JS — zero dependencies, zero build step.
- Light/dark theme with a manual toggle (persisted via `localStorage`) plus automatic
  detection of OS preference on first visit.
- Responsive layout down to mobile widths, with a collapsible nav menu.
- Scroll-reveal animations via `IntersectionObserver` (gracefully degrades if unsupported).
