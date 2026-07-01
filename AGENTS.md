# AGENTS.md

## Cursor Cloud specific instructions

This is a [Zenn](https://zenn.dev) content repository (Japanese tech articles/books), not a traditional app. Content lives in `articles/*.md` and `books/`.

### Services

- **Zenn preview server** — the "application". Renders articles/books in the browser (mermaid diagrams, tables, callouts).
  - Run: `npx zenn preview --port 8000`, then open `http://localhost:8000`.
  - It is a long-running dev server; start it in a background/tmux session.
- **textlint (AI writing lint)** — `npm run lint:ai` checks `articles/**/*.md` against `@textlint-ja/preset-ai-writing` (config in `.textlintrc.json`). Use `npm run lint:ai:fix` to autofix.

### Notes

- No automated test suite and no build step exist; scripts are only in `package.json` (`lint:ai`, `lint:ai:fix`, `textlint:mcp`).
- Articles with `published: false` in frontmatter still render in local preview.
- When editing/reviewing Japanese articles, follow `.cursor/rules/japanese-writing.mdc` and the `stop-ai-slop-jp` skill, then run `npm run lint:ai` before considering an article done.
