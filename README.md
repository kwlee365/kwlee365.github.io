# kwlee365.github.io

Personal academic site — Jekyll + GitHub Pages, no external theme.

## Local preview

```bash
bundle install
bundle exec jekyll serve      # http://127.0.0.1:4000
```

## Where content lives

Almost nothing is hard-coded in HTML. Edit the YAML in `_data/` and the pages rebuild.

| File | Feeds |
|---|---|
| `_data/interests.yml` | Research interests on the About page |
| `_data/education.yml` | Education timeline |
| `_data/teaching.yml` | Teaching timeline |
| `_data/publications.yml` | Publications page (grouped by `year:`, wrap your own name in `**...**`) |
| `_data/projects.yml` | Projects page |
| `_data/navigation.yml` | Top nav |
| `_data/affiliations.yml` | Lab affiliations on the About page |
| `_data/media.yml` | Media page; leave `url: ""` until you have the link |
| `_config.yml` → `author:` | Sidebar: name, photo, the `meta:` lines under it, social icons |

Prose that isn't a list lives in `index.md` (About).

## Adding a publication

```yaml
- title: "Paper title"
  authors: "**K. Lee**, and J. Park"     # ** ** marks your own name
  venue: "IEEE Transactions on Robotics"
  year: 2026
  type: Journal                           # Journal / Conference / Preprint
  links:
    - text: arXiv
      url: https://arxiv.org/abs/...
```

Keep the list sorted newest-first; the page numbers entries `[1], [2], ...` in that order.

## Styling

Everything is in `assets/css/main.scss`. Colors are CSS custom properties on `:root`
(with a dark-mode block below it) — change `--accent` to recolor the whole site.

## CV

`assets/CV_kwlee.pdf` is deliberately **not** committed (see `.gitignore`) and no CV
button is shown. To publish one later, host the PDF somewhere and set
`author.cv` in `_config.yml` to its URL — the sidebar button reappears on its own.
