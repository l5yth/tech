# Repository Guidelines

## Project Structure & Module Organization
- Static site lives at the repo root; primary entry is `index.html`.
- Long-form posts use date-prefixed HTML files (e.g., `2025-09-meshtastic-daemon.html`, `2025-09-potato-mesh.html`) beside `index.html`.
- Shared stylesheet is `style.css`; assets stay adjacent to pages (`com0.l5y.tech.pub.asc`); keep relative paths stable to avoid broken links when hosting from the root.

## Build, Test, and Development Commands
- No build step; open `index.html` directly or serve locally for relative-asset checks: `python3 -m http.server 8000`.
- Optional HTML sanity check (if installed): `tidy -errors index.html`.

## Coding Style & Naming Conventions
- HTML/CSS only; keep the austere typographic look (system font stacks, one amber accent, no web fonts or external requests) and do not add JavaScript. Page styles live in `style.css`; avoid per-page `<style>` blocks.
- Indent with two spaces; prefer semantic tags (`header`, `article`, `footer`, `h1`–`h3`, `ul`/`ol`, `table`) as seen in existing posts.
- Keep filenames lowercase, words separated by hyphens; for new posts, use `YYYY-MM-topic.html` to keep chronological sorting.
- Maintain ASCII content unless the page already mixes in emoji; keep alt text on images.

## Testing Guidelines
- Manual: load pages in a browser at desktop and phone widths and verify links (post links, PGP link, mailto) resolve and the stylesheet loads.
- View with and without a local server to ensure relative links do not assume a specific host path.
- If you add new posts, add them to the "Latest posts" list in `index.html` (newest first) and click through to confirm navigation works. Copy the header, `.post-header` and footer markup from an existing post.

## Commit & Pull Request Guidelines
- Commits: concise, imperative subject lines (e.g., “Add potato mesh article”); group related HTML/CSS asset changes together.
- PRs: include a short summary of what changed, screenshots of new/updated pages, and note any new assets added to the root.
- Link any relevant issue/ticket; call out compatibility considerations (e.g., paths that assume root hosting vs. subdirectory hosting).

## Security & Hosting Notes
- Keep email/PGP links accurate; avoid committing secrets or non-public keys.
- When adding external links, prefer HTTPS and test them.
- If deploying under a subpath, ensure relative links stay relative (avoid leading `/` in new links or assets).
