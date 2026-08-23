# Portfolio

Workspace for coursework, experiments, and personal projects during my
postgraduate studies in **AI / ML**.

## Structure

| Path | Purpose |
| --- | --- |
| `Srini235.github.io/` | Jekyll source for my personal site and blog. Published to <https://srini235.github.io>. |
| `venv/` | Local Python virtual environment. Re-create with `python -m venv venv` rather than committing dependencies here. |

## The blog

The site inside `Srini235.github.io/` is the public-facing part of this repo.
Posts live in `Srini235.github.io/_posts/` and use standard Jekyll front
matter (see any post for the template).

### Running locally

```powershell
cd Srini235.github.io
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
- Don't commit virtualenv contents, model weights, or generated graph dumps.

## Contact

- [GitHub](https://github.com/Srini235) - Open an issue or explore my repositories.
- [LinkedIn](https://www.linkedin.com/in/srinivasan-ravichandran-8340b9128/) - Connect with me professionally.
