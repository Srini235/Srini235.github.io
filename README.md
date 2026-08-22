# Portfolio

Workspace for coursework, experiments, and personal projects during my
postgraduate studies in **AI / ML**.

## Structure

| Path | Purpose |
| --- | --- |
| `index.md` | The Jekyll homepage. Edit this to change what visitors see at <https://srini235.github.io>. |
| `_posts/` | Blog posts. One Markdown file per post, named `YYYY-MM-DD-title.md`. |
| `assets/` | Static files (CSS, images) served as-is by Jekyll. |

## The blog

Posts live in `_posts/` and use standard Jekyll front matter (see any
post for the template).

### Running locally

```powershell
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>.

### Writing a new post

Create `YYYY-MM-DD-your-title.md` under `_posts/` with at least:

```markdown
---
layout: post
title: "Your title"
date: YYYY-MM-DD
categories: [Category]
---
```

## Conventions

- Keep prose in plain Markdown — no HTML unless a layout requires it.
- Code fences include the language tag (` ```powershell `, ` ```python `, …).
- Don't commit model weights or generated graph dumps.

## Contact

Open an issue on GitHub or reach me through the links on the site.
