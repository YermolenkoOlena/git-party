# Projcets 

Website for Creative Code Kortrijk, a new creative coding club in Kortrijk, Belgium.
The site introduces the club to visitors and potential members: its workshops, its foundations (core ideas) and its team, plus a news page.

- Built by a team of four students as part of the "Web 3 Git Party" challenge, using Git and GitHub Flow.
- Each team member works in their own clone, on their own `feature/*` branch, with their own agent session.
- Changes reach `main` only through pull requests on GitHub.
- Pages: `/` (index with Workshops, Foundations and Team sections), `/about`, `/news`, a detail page per workshop, foundation and team member (dynamic route by entry id), and a `/code` page where visitors enter a hidden 4-digit code.
- The live site is deployed to GitHub Pages and rebuilds automatically when `main` changes.

# Stack & constraints

- Framework: Astro.
- Content: Astro content collections defined in `src/content.config.ts`, loaded from markdown with the `glob` loader and validated with Zod schemas (`astro/zod`).
- `workshops` (`src/content/workshops`): `title`, `image`
- `foundations` (`src/content/foundations`): `title`, `description`
- `team` (`src/content/team`): `name`, `function`, `bio`, `pic`
- `news` (`src/content/news`): not defined yet; source items are in `resources/news/`
- If a markdown file is missing a required frontmatter field, the build fails.
- Styling: plain CSS only, no CSS framework. Files are `src/styles/reset.css`, `global.css`and `markdown.css`. The font is Space Grotesk (`@fontsource-variable/space-grotesk`).
- Structure:
- `src/components/`: Astro components, e.g. `Workshops`/`WorkshopCard`, `Foundations`/`FoundationsCard`, `Team`/`TeamCard`, `Code`, `Header`, `Footer`, `Hero`
- `src/layouts/`: `Base.astro`, `Markdown.astro`
- `src/pages/`: routes
- `src/assets/`: images
- `resources/`: starter files for the detail pages and news items (not part of the build)
- Scripts: `npm run dev` (dev server with `--host`), `npm run build`, `npm run preview`.
- Deployment: GitHub Pages through a GitHub Actions workflow, following the Astro deploy guide. The Astro config is currently empty (`astro.config.mjs`).
