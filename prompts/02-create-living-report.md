# Prompt 02 — Create the Living Research Report

Run this after Prompt 01 has initialized and pushed the main research repository.

```text
Create the initial Living Research Report for this scientific repository and publish it on an orphan gh-pages branch.

Read AGENTS.md, README.md, the repository structure, existing scientific documentation, figures and provenance material first. Preserve existing work. Do not rerun expensive analyses unless needed and explicitly justified.

If the repository already makes the science clear, proceed. Ask me only about ambiguities that materially affect the scientific structure of the report.

REPORT

Create a polished living scientific evidence report, not a dashboard, commit log or generic documentation site.

Organize navigation around THIS project's scientific structure. Include only sections that are useful. Normally consider:
- Overview
- Project roadmap, if milestones exist
- project-specific evidence/results sections
- Results & evidence
- Limitations & open questions
- Relevant reads
- Methods & provenance
- Research evolution

At the top show:
- project title;
- explicit scientific author(s);
- Living Research Report / Work in progress;
- last update;
- source main commit;
- report provenance;
- short human-readable summary of the latest substantive update.

For important results, clearly distinguish evidence, interpretation and claim boundaries. Preserve negative results, uncertainty and unresolved questions. Never present planned analyses as completed evidence.

If milestones exist, show a compact scientific roadmap using only Planned / In progress / Complete / Blocked. Do not invent dates, percentages or status.

Relevant reads should contain only documented or unambiguously verified papers, with DOI/publisher links and one sentence explaining relevance. Do not invent references.

FIGURES

Follow AGENTS.md. Reuse verified existing figures when appropriate. Put figures where they provide scientific evidence, not in a generic gallery.

By default, future scientifically meaningful figures/results should be incorporated into the appropriate report section. Exploratory/local-only work remains unpublished.

PUBLICATION

Create an orphan gh-pages branch containing only the public report and selected sanitized presentation assets.

Use a lightweight self-contained static site:
- semantic HTML and maintainable CSS;
- minimal JavaScript only when useful;
- neutral gray/off-white scientific palette with restrained orange/ochre accents;
- responsive figures/tables;
- compact desktop navigation;
- accessible three-line hamburger navigation on mobile;
- .nojekyll.

Do not add Jekyll, frontend frameworks, dashboards or build systems unless genuinely required.

Before publishing, audit the current tree and reachable Git history for secrets, credentials, raw/proprietary/private data and unintended large files. If public publication is unsafe, stop and tell me before pushing.

Use NEW markers only for scientific information introduced in the latest substantive scientific update. Research evolution should record major scientific changes, not ordinary commits.

Push gh-pages.

At completion report only:
- gh-pages commit SHA;
- expected Pages URL;
- files published;
- scientific navigation;
- any manual GitHub Pages step still required;
- confirmation that no raw/local/private data were published.
```
