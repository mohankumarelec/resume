# Resume

Hey — this is my personal CV, built in LaTeX and shipped as a PDF.

**Want to see it?** Here’s the résumé (opens as a PDF):

**[https://mohankumarelec.github.io/resume/resume.pdf](https://mohankumarelec.github.io/resume/resume.pdf)**

If you like the layout or workflow, feel free to fork or copy whatever helps for yours — no need to ask.

---

## What’s in here

| File | What it does |
|------|----------------|
| `resume.tex` | The source — custom layout, `fontspec`, TikZ, Font Awesome, etc. |
| `index.html` | Tiny GitHub Pages page that sends you to the PDF |
| `resume.pdf` | The built file (not in git; CI or your machine makes it) |

Fonts live under `fonts/` — keep those paths happy if you compile locally.

## Build it yourself

With [Tectonic](https://tectonic-typesetting.github.io/):

```bash
tectonic --keep-logs resume.tex
```

## CI & Pages

[`.github/workflows/build-resume.yml`](.github/workflows/build-resume.yml) runs on pushes/PRs to `main`: Tectonic builds the PDF, uploads an artifact, and on `main` pushes it deploys to GitHub Pages (`resume.pdf` + `index.html`). In repo **Settings → Pages**, use **GitHub Actions** as the source so that PDF URL above stays live.
