# Personal Academic Homepage

Static HTML + CSS, mimicking the Google Sites layout shown in the reference screenshot.
Built for deployment to **GitHub Pages** (`<username>.github.io`).

## Structure

```
homepage/
├── index.html            # Home (bio + news + CV download)
├── research.html         # Research interests
├── teaching.html         # Courses
├── assets/
│   ├── css/style.css
│   └── img/
│       └── profile.jpg   # <-- put your photo here
└── files/
    ├── cv.pdf            # <-- your CV, linked from the Home page
    ├── *.pdf             # syllabi, slides, problem sets
    └── *.zip             # data, code archives
```

## Deploy (5 minutes)

1. Create a new **public** repo on GitHub named exactly `<your-github-username>.github.io`.
2. From this folder, run:
   ```bash
   git init -b main
   git add .
   git commit -m "init: academic homepage"
   git remote add origin git@github.com:<your-github-username>/<your-github-username>.github.io.git
   git push -u origin main
   ```
3. Open `https://<your-github-username>.github.io` &mdash; you'll see your site within ~30 seconds.

## Custom domain (optional)

1. Put your domain (e.g. `econ-name.com`) into a file named `CNAME` in this folder.
2. In your registrar, add a `CNAME` record pointing to `<your-github-username>.github.io`.
3. In repo **Settings &rarr; Pages &rarr; Custom domain**, enter your domain and enable **Enforce HTTPS**.

## Customize

All placeholders are marked with `[...]`. Find-and-replace across the whole `homepage/` folder:

| Placeholder | Example |
|---|---|
| `[Your Name]` | `Ming Li` |
| `[Your Title]` | `Assistant Professor` |
| `[Your University]` | `Peking University` |
| `you@uni.edu` | your real email |
| Scholar URL `?user=XXXX` | your Google Scholar ID |

Then add your profile photo at `assets/img/profile.jpg`.

## Add a publication

Publications are not on a separate page &mdash; they're inside your CV. Just drop the
PDF in `files/` (e.g. `files/cbam-paper.pdf`) and add a row for it inside your CV PDF.

If you ever want a standalone publications page later, fork an HTML like this:

```html
<div class="pub">
  <h4>"Paper Title Here"</h4>
  <div class="pub-meta">with Coauthors &middot; Journal Name, 2026</div>
  <div class="pub-links">
    <a href="files/cbam-paper.pdf">PDF</a>
    <a href="https://doi.org/10.xxxx/xxxxx">DOI</a>
  </div>
</div>
```

## Add a course

1. Drop syllabus / slides in `files/`.
2. Edit `teaching.html` &mdash; copy this block:

```html
<div class="course">
  <h4>ECON 511 &mdash; International Trade</h4>
  <div class="course-meta">Graduate &middot; Mon/Wed 14:00 &middot; Office hours: Tue 16:00</div>
  <div class="course-links">
    <a href="files/econ511-syllabus.pdf">Syllabus</a>
    <a href="files/econ511-slides.pdf">Slides</a>
  </div>
</div>
```

## Local preview (optional)

No build step. Just open `index.html` in a browser. Or run a one-liner:

```bash
python -m http.server 8000     # then visit http://localhost:8000
```

## Tips

- Keep links to **PDF** rather than external paper hosts (less 404).
- Use **permalink PDFs** (e.g. author's personal copy) as the primary, journal as secondary.
- Update the **footer date** each time you publish a new paper.
- For Chinese-language version, save as `index.zh.html` and add a language switcher in the topnav.
