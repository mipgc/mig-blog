# mig-blog

Static blog about AI, technology and opinions from a software developer. Posts are written in Markdown and [Astro](https://astro.build) compiles them to HTML.

## Requirements

- Node.js 22.12 or later

## Usage

```bash
npm install      # first time only
npm run dev      # http://localhost:4321
npm run build    # output in dist/
```

## Writing a post

Create a file in `src/content/posts/`, for example `src/content/posts/my-post.md`:

```markdown
---
title: "Title"
description: "Short summary for the listing."
pubDate: 2026-10-25
tags: ["ai"]
draft: false
---

Markdown content...
```

The file name becomes the URL: `/posts/my-post/`. Posts with `draft: true` only show up in `npm run dev`, but they are still visible in the repository.

## Deployment

Every push to `master` publishes the blog to GitHub Pages at [migpuerta.com](https://migpuerta.com) through `.github/workflows/deploy.yml`. The domain is set in `public/CNAME` and in `site` in `astro.config.mjs`.

## Structure

```
src/
├── content/posts/      # Markdown posts
├── content.config.ts   # frontmatter schema
├── layouts/Base.astro  # shared HTML (head and footer)
├── lib/posts.ts        # loads and sorts posts
├── pages/
│   ├── index.astro         # listing
│   └── posts/[slug].astro  # post page
└── styles/global.css   # palette and styles
```
