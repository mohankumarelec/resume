# Resume

Personal résumé built from LaTeX and published as a PDF.

## Repository layout

| File | Purpose |
|------|---------|
| `resume.tex` | Source (custom layout, `fontspec`, TikZ, Font Awesome icons) |
| `index.html` | Minimal landing page that redirects to `resume.pdf` (for GitHub Pages) |
| `resume.pdf` | Compiled output (ignored in git; produced by CI or a local build) |

## Local build

Install [Tectonic](https://tectonic-typesetting.github.io/) and compile:

```bash
tectonic --keep-logs resume.tex
```

`resume.tex` loads fonts from local paths under `fonts/`; keep those files in place where you build.

## CI and hosting

[`.github/workflows/build-resume.yml`](.github/workflows/build-resume.yml) runs on pushes and pull requests to `main`:

- Compiles `resume.tex` with Tectonic (with a cache for Tectonic bundles).
- Uploads `resume.pdf` as a workflow artifact.

On pushes to `main`, the same workflow also deploys a small site (`resume.pdf` + `index.html`) to **GitHub Pages** via `actions/deploy-pages`. Enable Pages in the repository settings (source: GitHub Actions) if you use this.
