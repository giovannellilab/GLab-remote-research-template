# Prompt 03 — Verify and publish

Run this after the main repository and Living Research Report have been created.

```text
Perform the final bootstrap verification for this research project. Do not redesign or add infrastructure unless something is actually broken.

Verify main:
- working tree is clean;
- expected project structure and AGENTS.md are present;
- data/raw, data/interim, data/processed and data/local contents are ignored as intended;
- no secrets, credentials, raw/proprietary/private data or unintended large files are tracked;
- remote and branch state are correct.

Verify gh-pages:
- only the report and selected sanitized presentation assets are published;
- navigation and anchors work;
- figures/tables are responsive;
- mobile hamburger navigation works;
- authorship, milestones, Relevant reads and provenance follow AGENTS.md and the available project evidence;
- no scientific claims, references, dates or milestone states were invented.

Check the expected public GitHub Pages URL if it is already enabled.

Push any necessary corrective commits, but do not make cosmetic changes merely to create activity.

If GitHub Pages still requires manual configuration, tell me exactly:
Settings → Pages → Deploy from a branch → gh-pages → /(root)

At completion give me a compact bootstrap summary:
- main branch commit;
- gh-pages commit;
- Pages URL/status;
- any remaining manual action;
- whether the project is ready for normal short Codex research prompts.
```
