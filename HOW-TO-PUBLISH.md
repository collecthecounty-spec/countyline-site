# How to publish a new post

The site is a Jekyll site hosted on GitHub Pages. Every essay, project update, archive entry, or product is just a Markdown file in the `_posts/` folder. Add a file, push it (or save it through GitHub's website), and the site rebuilds itself automatically in about a minute — no HTML, no local tools required.

## Adding a post through GitHub (no local setup)

1. Go to the repo on github.com, open the `_posts` folder.
2. Click **Add file → Create new file**.
3. Name it `YYYY-MM-DD-a-short-slug.md` (the date matters — it controls sort order; the slug just becomes part of the filename, not the URL).
4. Paste in one of the templates below, fill in your content, and commit directly to `main`.
5. Refresh [countylinehq.com](https://countylinehq.com) in a minute or two.

## The front matter fields

Every post starts with a block like this, between two `---` lines:

```yaml
---
title: Your Title Here
type: Essay
section: articles
permalink: /articles/your-title-here/
excerpt: "One sentence — shows up in card previews across the site."
---
```

- **title** — shown everywhere the post appears.
- **type** — the label shown on cards: `Essay`, `Project`, `Archive`, or `Product`.
- **section** — which index page it belongs to and where the "Back to ___" link goes: `articles`, `projects`, `archives`, or `products`. Must match `type` sensibly (essays → articles, etc.).
- **permalink** — the post's URL. Keep it under the matching section, e.g. `/articles/...`, `/projects/...`, `/archives/...`, `/products/...`. Must be unique across the whole site.
- **excerpt** — the short blurb used in listing cards and the home page. Keep it to one sentence.

Everything after the second `---` is the body — write it as plain Markdown (paragraphs, `**bold**`, `[links](url)`, lists, etc.).

### Optional fields

- **featured: true** — pulls this post into the "Recently" rotator on the home page. Only the 3 most recently-dated `featured: true` posts show there; if nothing is flagged, the home page just falls back to the 3 newest posts site-wide.
- **popular: true** — (archives only) bumps this entry to the front of the "Archives & Visuals" carousel on the home page, ahead of ones sorted by date.
- **visual: t1** through **t6** — picks one of six built-in gradient backgrounds for the post's visual banner and its tile in Archives/the home carousel. Cycle through `t1`–`t6` for variety; there's no need to keep them unique.
- **tag: "Some short label"** — projects only. Overrides the mono label shown on the Projects page (e.g. "Channel build-out") instead of just showing "Project".

## Templates

**Essay** (`_posts/2026-09-01-my-new-essay.md`):
```yaml
---
title: My New Essay
type: Essay
section: articles
permalink: /articles/my-new-essay/
excerpt: "One sentence describing it."
featured: true
visual: t3
---
Your essay text goes here, in plain Markdown paragraphs.
```

**Project update** (`_posts/2026-09-01-project-name.md`):
```yaml
---
title: Project Name
type: Project
tag: "Video series"
section: projects
permalink: /projects/project-name/
excerpt: "What it is, one sentence."
---
More detail about the project, in Markdown.
```

**Archive / visual entry** (`_posts/2026-09-01-archive-name.md`):
```yaml
---
title: Archive Name
type: Archive
section: archives
permalink: /archives/archive-name/
excerpt: "One line about this set."
visual: t5
popular: true
---
Optional short caption text.
```

**Product** (`_posts/2026-09-01-product-name.md`):
```yaml
---
title: Product Name
type: Product
section: products
permalink: /products/product-name/
excerpt: "What it is, one sentence."
---
Description, pricing notes, whatever you want on the page.
```

## Everything else

Site-wide design (colors, fonts, layout) lives in `assets/css/style.css` and `_layouts/`. The listing pages (`articles.html`, `archives.html`, `projects.html`, `products.html`) and the home page (`index.html`) pull posts in automatically — you shouldn't need to touch them when adding routine content. If you want a structural or design change, that's still a "come talk to Claude" task.
