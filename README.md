# Roze95.github.io

Personal academic website for **Georgi Gary Rozenman** — C.L.E. Moore Instructor of Applied Mathematics, MIT.

Live at **https://Roze95.github.io**

## Structure

| File | Page |
|------|------|
| `index.html` | Home / bio / news |
| `research.html` | Research themes |
| `publications.html` | Full publication list |
| `teaching.html` | Courses + materials |
| `code.html` | Software / repos |
| `cv.html` | Curriculum vitae |
| `assets/style.css` | All styling |
| `files/` | PDFs (CV, lecture notes, problem sets) |
| `images/` | `profile.jpg` for the home photo |

Plain HTML/CSS — **no build step**. Edit a file, commit, push; GitHub Pages
redeploys in ~1 minute. `.nojekyll` disables Jekyll processing.

## Common edits

- **Add your photo:** drop `images/profile.jpg` (square). It replaces the
  "GR" monogram automatically.
- **Add the CV PDF:** put `files/cv.pdf` in place (e.g. the Overleaf build of
  your `main_old.tex`). The CV-download button then works.
- **Publish teaching PDFs:** add files to `files/` matching the names in
  `teaching.html`, or edit the links/labels there.
- **Update news / links:** edit the lists in `index.html` (Google Scholar and
  ORCID URLs are marked with `#` placeholders).

## Local preview

```sh
cd Roze95.github.io
python3 -m http.server 8000
# open http://localhost:8000
```
