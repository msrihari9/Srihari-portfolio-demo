# portfolio-demo2

A static personal portfolio website for **Srihari Mogalapalli — Quality Engineering &
GenAI/Agentic AI Product Engineering Leader**, built with plain HTML, CSS, and JavaScript
(no build tools required) so it can be published directly on **GitHub Pages**.

**Live site:** https://msrihari9.github.io/Srihari-portfolio-demo/
**Repository:** https://github.com/msrihari9/Srihari-portfolio-demo

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
│   ├── profile-photo.jpg    # Profile photo used in hero + résumé
│   ├── profile-photo.svg    # Unused placeholder avatar (kept for reference)
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

## Content status

All content reflects Srihari's actual LinkedIn profile, résumé, and photo (experience, skills,
certifications, achievements, contact details, portrait). Nothing is left as a placeholder.

Bio, 5-role experience timeline, skills, 4 featured projects, achievements, 8 certifications,
contact info, and the [profile photo](images/profile-photo.jpg) are all populated from the real
LinkedIn export, résumé PDF, and headshot provided. Revisit these sections periodically to keep
them in sync as the résumé evolves.

The contact form currently submits via `mailto:`; for a production-grade form, wire it up to
a service such as [Formspree](https://formspree.io) or [Netlify Forms](https://www.netlify.com/products/forms/).

To regenerate a PDF résumé, open [resume/resume.html](resume/resume.html) in a browser and use
"Print / Save as PDF", then drop the file into `resume/` and link to it directly if preferred
over the HTML version.

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

This site is already deployed to https://github.com/msrihari9/Srihari-portfolio-demo and live
at https://msrihari9.github.io/Srihari-portfolio-demo/. To push future updates, just commit and
push to `main` — GitHub Pages redeploys automatically. Steps below are for reference / setting
up from scratch elsewhere.

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
