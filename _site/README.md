# Communication Primer Website (Jekyll + GitHub Pages)

This repository contains the **site structure** for a Jekyll-powered website that introduces non-technical readers to major schools of communication theory and their relevance to communication problems in the AI era.

## Site Structure

- `index.md` — project home page
- `transmission-view.md`
- `meaning-and-culture.md`
- `interpretation-and-power.md`
- `interpretation-and-intention.md`
- `reader-guidance.md`
- `how-i-built-this-site.md`
- `_layouts/default.html` — accessible base template
- `assets/css/style.css` — blue palette and typography variables
- `assets/images/` — image folder for your content
- `.github/workflows/jekyll-build.yml` — CI build on pushes to `main`

## Authoring Content

Each page is Markdown with front matter:

```md
---
layout: default
title: Page Title
permalink: /your-path/
---

Your content here.
```

Recommended workflow:

1. Keep front matter at the top of each page.
2. Replace starter paragraphs with your analysis.
3. Use semantic sections (`##`, `###`, bullet lists) for readability.
4. Add links, references, and examples relevant to your argument.

## Adding Images

1. Place images in `assets/images/`.
2. Reference them from Markdown:

```md
![Alt text describing image]({{ '/assets/images/example.png' | relative_url }})
```

Accessibility notes:

- Always provide descriptive alt text.
- Use informative headings and short paragraphs.
- Ensure linked text describes destination context.

## Basic Jekyll Configuration

Update `_config.yml` when needed:

- `title`: site title shown in header and browser title
- `description`: summary used for metadata
- `url`: your GitHub Pages host (already set)
- `baseurl`: repository path (already `/comm-primer`)

For this repository, keep:

- `url: "https://lillydonohoe.github.io"`
- `baseurl: "/comm-primer"`

If the repository name changes, update `baseurl` to match.

## CSS Customization (Blue Theme Variables)

Edit `assets/css/style.css` under `:root`:

- `--blue-950`, `--blue-800`, `--blue-700` for primary shades
- `--blue-100`, `--blue-50` for light backgrounds
- `--text-main`, `--text-muted` for text contrast
- `--focus` for keyboard focus outline

Tip: keep color contrast strong for accessibility (especially links and text over blue backgrounds).

## Local Preview

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000/comm-primer/`.

## CI Build

The GitHub Action in `.github/workflows/jekyll-build.yml` runs on every push to `main` and builds the site with `bundle exec jekyll build`.
