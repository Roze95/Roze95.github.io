# 18.085 — Computational Science and Engineering I (Fall 2026)

Course website. Plain HTML and one stylesheet, no build step — the same design
language as `roze95.github.io` (Charter serif, MIT red `#a31f34`, 880px measure,
sticky nav), extended with a schedule table, lecture-note boxes matched to the
colours in `cse085.sty`, and MathJax.

## Layout

```
18085-site/
  index.html            course home — logistics, arcs, grading, policies
  lectures.html         all 26 sessions, dated, by arc
  psets.html            the seven problem sets, submission and quiz policy
  resources.html        curated supplementary materials
  lectures/
    L01.html            Lecture 1, full notes with MathJax
    _template.html      copy this for L02 ... L26
  assets/style.css      the whole design
  files/                syllabus.pdf, L01.pdf, ... (empty for now)
```

## Deploying to roze95.github.io/18085/

The site is written with relative links and expects to live in a folder called
`18085` at the root of the personal-site repo.

```sh
cp -R 18085-site /path/to/roze95.github.io/18085
cd /path/to/roze95.github.io
git add 18085 && git commit -m "Add 18.085 Fall 2026 course site" && git push
```

It is then live at `https://roze95.github.io/18085/`. Add a nav entry on the
main site (`teaching.html` is the natural place) pointing at `18085/`.

To host it as its own repo instead, the only change needed is the
`← Rozenman` link in each page's nav, currently `../`.

## Adding a lecture

1. `cp lectures/_template.html lectures/L02.html`
2. Fill in the number, title, date, reading, and body. The MathJax config in
   the template already defines the `cse085.sty` macros — `\mat`, `\vec`, `\T`,
   `\Oh{...}`, `\R`, `\Kmat`, `\Tmat`, `\Bmat`, `\Cmat` — so LaTeX from the
   `.tex` source can be pasted in almost verbatim between `\[ ... \]`.
3. Note boxes: `<div class="keyidea">`, `<div class="remark">`,
   `<div class="watch">`, `<div class="objectives">` — the four `tcolorbox`
   environments, in the same colours.
4. Drop `L02.pdf` into `files/`.
5. In `lectures.html`, turn the row's topic into a link and add
   `<span class="tag">notes</span>`; move the `class="now"` highlight to it.

## Re-adding the PDFs

The syllabus and lecture PDFs are not in `files/` yet, so their links were
removed rather than left broken. To put them back:

1. Copy `admin/syllabus.pdf` and `lectures/L01/L01.pdf` from the Drive FA2026
   folder into `files/`.
2. Add `<a href="files/syllabus.pdf">Syllabus</a>` back to the `<nav class="main">`
   block on every page (`../files/…` from inside `lectures/`).
3. In `index.html`, restore the "Syllabus (PDF)" quick-link card.
4. In `lectures/L01.html`, restore the `Download PDF` button under the header.

## Notes

- Dark mode is handled by `prefers-color-scheme` at the bottom of the
  stylesheet; there is no toggle and the light design is unchanged.
- MathJax loads from jsDelivr. To pin it or serve it locally, change the one
  `<script src>` in each lecture page.
- No JavaScript anywhere else — every page works with scripts disabled except
  for the rendered equations.
