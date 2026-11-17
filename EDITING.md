# Editing Jane Zhang's website

This is the existing Quarto website. Edit the source files, then check the local preview. Quarto generates the browser-ready HTML in `docs/`; edit the source rather than that generated HTML.

The GitHub project is `Jane-bunny/jane-zhang`. The public website is https://jane-bunny.github.io/jane-zhang/.

## Where things live

| File | What it controls |
| --- | --- |
| `_quarto.yml` | Site title, menu labels and destinations, footer, shared rendering options |
| `_brand.yml` | Named colours and typography |
| `custom.scss` | Quarto / Bootstrap theme settings |
| `styles.css` | Homepage layout, spacing, responsive breakpoints, link and focus styles |
| `index.qmd` | Homepage text, portrait photograph, sections A–E |
| `about.qmd` | Background, qualifications, interests, profile links |
| `data-projects.qmd` | Data portfolio overview |
| `projects/msc-space-plasma.qmd` | MSc project details and references |
| `writing.qmd` | Published fiction, manuscripts, earlier creative notes |
| `ai-energy.qmd` | Independent study and AI & Energy Monitor introduction |
| `ai-energy/monitor/index.qmd` | Monthly Monitor issue index |
| `ai-energy/monitor/YYYY-MM.qmd` | Individual Monitor articles, with reporting and publication dates |
| `posts/` | Existing data-blog posts and saved figure metadata |
| `side-project.qmd` | Preserved earlier side-project notes |
| `filters/figure-alt.lua` | Descriptive alt text for saved analysis figures |

## Three useful concepts

- The block between `---` lines at the top of a `.qmd` file is page configuration. Text below it is page content.
- In a menu, `text` is the visible label and `href` is the destination. The website title already links to the homepage.
- A block such as `::: {.home-hero}` groups content and attaches a CSS class. Its appearance is defined by `.home-hero` in `styles.css`.

The homepage uses one large heading (`#`) and section headings (`##`). Keep that hierarchy when editing. HTML comments mark its five sections and are invisible to visitors.

## Preview and build

From the project folder:

```powershell
quarto preview --port 4321
```

Open http://localhost:4321/. Save a source edit to refresh the preview; press Ctrl+C in the terminal to stop it. `quarto render` rebuilds the entire site using saved computational results where available. Previewing an edited computational post can run its Python code and requires the original dependencies, including `palmerpenguins` for the penguin post.

## Publishing and preserving earlier work

Rendering updates the local `docs/` files. A local Git commit saves work without publishing it. Pushing the `main` branch to GitHub updates the public website through GitHub Pages, which serves the `docs/` folder.

The older practice post and `side-project.qmd` are excluded from the public build. Their source files and saved computational results remain available for learning. The obsolete `_site/` output has been removed and is ignored.

Add real Monitor issues under `ai-energy/monitor/YYYY-MM.qmd`, then link them from the Monitor index. Keep reporting periods separate from publication dates and retain identifiable sources. No newsletter, contact form or public email link is active.
