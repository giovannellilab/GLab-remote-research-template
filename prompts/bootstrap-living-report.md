# Bootstrap a Living Research Report

Use this once, after the scientific repository has been initialized and contains enough project material to inspect.

```text
Create the initial Living Research Report for this scientific repository and publish it through GitHub Pages.

First read AGENTS.md, README.md, the repository structure, existing scientific documentation, figures and provenance material. Preserve existing work. Do not rerun expensive analyses unless needed and explicitly justified.

Before changing anything, briefly report:
- the scientific question you infer from the repository;
- the authoritative material you found;
- the proposed scientific report sections;
- any ambiguity that actually requires my decision.

If the repository already makes these points clear, proceed without a long interview.

REPORT PURPOSE

Create a polished living scientific evidence report. It is not a project dashboard, commit log or generic documentation site.

Organize the navigation around the scientific structure of THIS project. Typical sections may include:
- Overview
- Project roadmap, when milestones exist
- project-specific evidence/result sections
- Results & evidence
- Limitations & open questions
- Relevant reads
- Methods & provenance
- Research evolution

Adapt these to the actual science. Do not create empty sections merely to follow a template.

At the top show:
- project title;
- explicit scientific author(s);
- Living Research Report / Work in progress status;
- last update;
- source main commit;
- report commit/provenance where practical;
- a short human-readable summary of the latest substantive update.

SCIENTIFIC REPORTING

For important results, make the relationship between result, evidence, interpretation and claim boundary clear.

Preserve negative results, uncertainty, failed criteria and unresolved questions.

Do not claim validation, representativeness, completeness, causation or generality unless the evidence supports it.

Clearly distinguish completed evidence from planned analyses.

Add a curated Relevant reads section. Include only references that are documented in the repository or can be unambiguously verified. Link to DOI/publisher pages and add one short sentence explaining why each paper matters to the project. Do not invent references.

If milestones are documented, show a compact scientific roadmap using only:
Planned / In progress / Complete / Blocked.
Do not invent dates, percentages or milestone states.

FIGURES

Reuse verified existing figures when possible.

For new scientific figures follow AGENTS.md:
- Viridis as default sequential palette;
- reproducible generation;
- variables and units labeled;
- N/population and relevant filtering/transformation stated;
- no silent outlier removal, smoothing or transformations.

Place figures in the scientific section where they provide evidence. Do not create a generic figure gallery.

PUBLICATION ARCHITECTURE

Keep main unchanged except for changes genuinely required by the research project.

Create an orphan gh-pages branch for the public report.

Use a small self-contained static site:
- semantic HTML;
- maintainable CSS;
- minimal JavaScript only if useful;
- neutral scientific palette with restrained warm/orange accents;
- responsive figures and tables;
- compact desktop scientific navigation;
- accessible three-line hamburger navigation on mobile;
- descriptive alt text and captions;
- .nojekyll.

Do not introduce Jekyll, a frontend framework, a dashboard framework or a build system unless the repository already requires one.

The report is organized by science, not commits.

DATA SAFETY

Before publishing, audit the current tree and reachable Git history for secrets, credentials, raw data, proprietary material, private notes and unintended large files.

Do not publish:
- raw datasets;
- acquisition caches;
- private/local notes;
- credentials;
- proprietary data;
- complete processed datasets merely because a figure uses them.

Publish only the report and explicitly selected sanitized presentation assets such as derived figures/tables.

If the safety audit finds something that makes public publication unsafe, stop and tell me before pushing gh-pages.

NEW INFORMATION

Scientific information introduced in the latest substantive update may receive a small NEW marker in its scientifically appropriate section.

NEW is not a milestone label and not chronological navigation. Remove old NEW markers on the next substantive scientific update.

RESEARCH EVOLUTION

Keep a short human-readable record only of major scientific changes: new evidence components, completed milestones, important changes in interpretation or scope.

Do not copy the Git commit log.

VERIFY AND PUBLISH

Check:
- mobile and desktop rendering;
- navigation anchors;
- figure/table responsiveness;
- local and external links;
- accessibility basics;
- report metadata/provenance;
- accidental data exposure.

Push the orphan gh-pages branch.

If GitHub Pages still requires manual repository configuration, tell me exactly:
Settings → Pages → Deploy from a branch → gh-pages → /(root).

At completion report only:
- gh-pages commit SHA;
- report URL or expected URL;
- files published;
- final scientific navigation;
- any manual GitHub step still required;
- confirmation that no raw/local/private data were published.
```
