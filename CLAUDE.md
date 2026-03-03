# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Self-Improvement

When the user corrects a mistake, points out a wrong assumption, or expresses a preference about how to work in this repo, update CLAUDE.md to capture that knowledge. Add it to the relevant section or create a new one. This keeps future sessions from repeating the same errors.

## Commands

```sh
npm run dev       # Start dev server at localhost:4321
npm run build     # Build production site to ./dist/
npm run preview   # Preview production build locally
npm run astro ... # Run Astro CLI commands (e.g., astro check, astro add)
```

There is no test runner configured.

## Architecture

This is an **Astro 5 blog site** using the blog starter template. Key architectural points:

- **Content Collections**: Blog posts live in `src/content/blog/` as `.md` or `.mdx` files. The collection schema is defined in `src/content.config.ts` — required frontmatter fields are `title`, `description`, and `pubDate`; optional fields are `updatedDate` and `heroImage`.
- **Routing**: File-based. `src/pages/index.astro` = homepage, `src/pages/blog/index.astro` = blog listing, `src/pages/blog/[...slug].astro` = dynamic post pages, `src/pages/rss.xml.js` = RSS feed.
- **Global constants**: Site title and description are in `src/consts.ts` — update these when customizing the site.
- **Integrations**: MDX (`@astrojs/mdx`), sitemap (`@astrojs/sitemap`), and RSS (`@astrojs/rss`) are configured in `astro.config.mjs`. The `site` URL in `astro.config.mjs` must be set correctly for sitemap and RSS to work.
- **TypeScript**: Strict mode with `strictNullChecks` enabled.
