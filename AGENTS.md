# AGENTS.md — scientific project defaults

Edit the project name, scientific question, authors and milestones for each new repository.

## Working principles

- Organize work around the scientific question, evidence and reproducibility.
- Preserve source data and provenance. Never silently alter raw observations.
- Keep raw, interim, processed, proprietary and private/local datasets out of Git unless explicitly approved.
- Do not invent results, references, dates, milestone states or validation.
- Scientific authorship is explicit; do not infer it from Git committers.

## Figures

- Viridis is the default sequential colormap.
- Use an appropriate diverging palette when the variable is genuinely diverging.
- Label variables and units; report N where relevant.
- Never silently remove outliers, transform/smooth data or change the analyzed population.
- Keep figure generation reproducible.
- By default, a scientifically meaningful requested figure should also be added to the appropriate section of the Living Research Report with a concise caption and provenance.
- If the prompt says "exploratory only", "local only" or "don't publish", do not add it to the report.

## Living Research Report

- The report is organized by science, not commits.
- Keep a clear distinction between current evidence, interpretation, limitations and planned work.
- Maintain a curated Relevant reads section for papers that materially inform the project.
- Use NEW markers only for scientific information introduced in the latest substantive scientific update; remove them on the next substantive update.
- Keep report metadata/provenance current.
- Publish only sanitized derived assets to gh-pages; never expose local datasets merely to make the report work.
- Keep the site lightweight: static HTML/CSS, minimal JavaScript only when useful, responsive scientific navigation and accessible mobile hamburger menu.
- Use a neutral visual palette; figures provide most scientific color.

## Milestones

Use only: Planned / In progress / Complete / Blocked.
Do not invent percentages, dates or status changes.
