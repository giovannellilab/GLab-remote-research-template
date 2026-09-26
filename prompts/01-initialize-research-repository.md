# Prompt 01 — Initialize the research repository

Use this immediately after creating an empty GitHub repository, cloning it to the workstation, and opening that folder in Codex.

```text
Initialize this repository as a clean, reproducible scientific research project.

First inspect the repository. If it is genuinely empty or contains only Git metadata, proceed. If project files already exist, preserve them and adapt rather than overwrite.

If the project title, scientific question, scientific author(s), or initial milestones are not available from the repository or my prompt, ask me for only those missing items before proceeding.

Create this generic structure, omitting a directory only when it is clearly irrelevant:

PROJECT/
├── AGENTS.md
├── README.md
├── data/
│   ├── raw/.gitkeep
│   ├── interim/.gitkeep
│   ├── processed/.gitkeep
│   └── local/
├── docs/
├── notebooks/
├── scripts/
├── src/
└── tests/

DATA AND GIT

Create a .gitignore that keeps the contents of data/raw, data/interim, data/processed and data/local out of Git while retaining .gitkeep placeholders where appropriate.

Also ignore normal secrets, local configuration, Python environments/caches, Jupyter checkpoints, editor files and temporary files.

Do not commit raw downloads, proprietary/private datasets, large intermediate files, complete processed datasets, credentials or secrets unless I explicitly approve them.

README

Create a concise project README containing:
- project title;
- short scientific purpose/question;
- explicit scientific author(s);
- current project status;
- repository structure;
- basic reproducibility instructions as they become known.

Do not invent methods, dependencies, results, references, dates or milestones.

AGENTS.md

Create a short project-specific AGENTS.md that establishes these durable defaults:

- organize work around the scientific question, evidence and reproducibility;
- preserve raw observations and provenance;
- scientific authorship is explicit and is not inferred from Git committers;
- never invent results, references, dates, milestone states or validation;
- milestone status vocabulary is only: Planned / In progress / Complete / Blocked;
- raw, interim, processed, proprietary and local datasets remain out of Git unless explicitly approved;
- Viridis is the default sequential scientific colormap; use a scientifically appropriate diverging palette for genuinely diverging variables;
- figures must be reproducible, labeled with variables/units and N/population where relevant;
- never silently remove outliers, smooth/transform data or change the analyzed population;
- once a Living Research Report exists, scientifically meaningful requested figures/results are added to their appropriate report section by default;
- "exploratory only", "local only", or "don't publish" means do not publish that output;
- maintain a curated Relevant reads section for papers that materially inform the project;
- the Living Research Report is organized by science, not commits;
- publish only sanitized derived assets to gh-pages.

Keep AGENTS.md short. These are persistent behavior rules, not a second README.

INITIAL COMMIT

Check git status and confirm no ignored research data or secrets are staged.

Commit the initialized project to main with a clear message and push it.

At completion report only:
- files/directories created;
- main commit SHA;
- any project information still missing;
- confirmation that research-data directories are ignored.
```
