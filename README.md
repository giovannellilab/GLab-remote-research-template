# GLab Remote Research Template

[![Built with Science](https://forthebadge.com/images/badges/built-with-science.svg)](https://forthebadge.com/)
[![Powered by Coffee](https://forthebadge.com/images/badges/powered-by-coffee.svg)](https://forthebadge.com/)
[![Giovannelli Lab](https://img.shields.io/badge/BY-Giovannelli_Lab-blue)](https://www.donatogiovannelli.com)

A practical template for running reproducible scientific projects with Codex on a remote workstation, GitHub for version control, and a continuously updated GitHub Pages living research report.

**Author:** Donato Giovannelli

## What this gives you

The working model is simple:

**phone → ChatGPT Remote → Codex on the workstation → local research repository → GitHub → public living research report on GitHub Pages**

The main branch contains code, documentation, and lightweight reproducible material. Large or restricted datasets stay local. A separate `gh-pages` branch contains only the sanitized HTML report and selected derived figures.

This repository documents the setup once so that normal research prompts can stay short.

## 1. Install ChatGPT and Codex on the workstation

Install the official ChatGPT desktop app and sign in with the same ChatGPT account you use on your phone.

For Linux, use the official ChatGPT desktop Linux package for your supported distribution. The Linux app includes Codex. Current OpenAI documentation should be checked before a new installation because supported distributions and Remote availability can change:

- Linux desktop: https://learn.chatgpt.com/docs/linux/linux-app
- Codex: https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan
- Remote: https://learn.chatgpt.com/docs/remote

Open ChatGPT, switch to **Codex**, and allow access to the local folder that will contain the research project.

### Remote Control

On the workstation, open the Remote/Connections settings and enable control of the computer if the option is available for your build/account.

On the phone:

1. Open the official ChatGPT mobile app with the same account and workspace.
2. Open **Remote**.
3. Pair/select the workstation.
4. Select the research project/workspace.
5. Start or continue a Codex task.

Keep the workstation awake, online, and the ChatGPT desktop app running.

**Linux note:** the Linux desktop app is official, but OpenAI's public Remote documentation may lag Linux rollout and currently documents Mac/Windows explicitly. This workflow has been tested on our Linux workstation; if Remote is unavailable on another Linux installation, check the current OpenAI Remote documentation rather than adding SSH/Tailscale infrastructure immediately.

## 2. Connect GitHub to ChatGPT

In ChatGPT, open **Settings → Plugins** and connect GitHub.

Authorize the repositories you want ChatGPT/Codex to access. For repositories owned by a GitHub organization, make sure the GitHub app is also installed/authorized for that organization. Personal-repository access does not automatically imply access to organization repositories.

Test the connection by asking ChatGPT to inspect the target repository.

## 3. Create a new scientific repository

Create a repository on GitHub for the project, then clone it on the workstation:

```bash
cd ~/github
git clone git@github.com:OWNER/REPOSITORY.git
cd REPOSITORY
```

A useful generic starting structure is:

```text
REPOSITORY/
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
```

Create only the directories the project actually needs. Do not add infrastructure just because it appears in this example.

## 4. Keep research data out of Git

Start from the `.gitignore` in this template.

The default rule is:

- code, documentation, small configuration files and reproducibility instructions: **Git**
- raw downloads, proprietary data, large intermediate files, processed datasets and private/local material: **local**
- selected sanitized derived figures/tables needed for the public report: **gh-pages only when appropriate**

The template keeps `.gitkeep` placeholders while ignoring the contents of the data directories.

Before making a repository public, audit the **entire Git history**, not only the current tree, for credentials, raw data, proprietary material and accidental large files.

## 5. Initialize Codex for the project

Open the cloned repository as a Codex workspace.

Copy the template `AGENTS.md` into the new repository and edit the project-specific lines at the top.

Use the normal workspace for the continuing research project. Use a worktree only when you deliberately want isolated parallel work.

The point of `AGENTS.md` is to store durable rules once. Routine prompts should remain short.

For example:

```text
Plot the density distributions of cell width and length.
```

Codex should already know the project figure/report conventions from `AGENTS.md`.

For a figure that should not appear in the public report:

```text
Exploratory only: plot the density distributions of cell width and length.
```

## 6. Initial Git commit

Once the initial repository structure and project README are correct:

```bash
git add .
git status
git commit -m "Initialize research project"
git push -u origin main
```

Check `git status` and the staged files before committing. Large/local datasets should not appear.

## 7. Create the Living Research Report

The report is a **scientific evidence report**, not a dashboard and not a commit log.

Use the bootstrap prompt in:

`prompts/bootstrap-living-report.md`

Give that prompt to Codex from the project workspace. It should inspect the actual project before creating the report.

The intended architecture is:

- `main`: research code, lightweight reproducible material and documentation
- local ignored directories: raw/interim/processed/private data
- orphan `gh-pages`: sanitized static report and selected presentation assets

The report should be organized by the scientific structure of the project. Git history records how it changed; commits do not define the navigation.

## 8. Enable GitHub Pages

After Codex creates and pushes the orphan `gh-pages` branch:

1. Open the repository on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select `gh-pages`.
5. Select `/(root)`.
6. Save.

The normal URL is:

```text
https://OWNER.github.io/REPOSITORY/
```

Open it anonymously to verify that the site is actually public and that figures, links and navigation work.

## 9. Normal research workflow

After setup, do science rather than maintain infrastructure.

Examples:

```text
Add these three papers to Relevant reads and summarize why each matters.
```

```text
Plot the density distributions of width and length.
```

```text
Update Milestone 2 to In progress.
```

```text
Re-run the analysis with the revised filter and update the relevant report section.
```

By default, scientifically meaningful new results and figures should be integrated into the appropriate section of the Living Research Report. Use **exploratory only** or **local only** when you do not want something published.

## 10. What belongs in the report

The living report should normally contain:

- scientific question and current interpretation;
- project roadmap when milestones exist;
- evidence/results organized by scientific topic;
- selected figures and tables;
- limitations and unresolved questions;
- curated **Relevant reads** with links and a sentence on why each matters;
- methods and provenance;
- a compact research-evolution record for major scientific changes.

It should show the scientific author(s) explicitly. Do not infer scientific authorship from Git commits.

Recommended milestone status vocabulary:

`Planned` · `In progress` · `Complete` · `Blocked`

Do not use invented percentage completion.

## Plotting convention

Use **Viridis** as the default sequential scientific palette. For ordered discrete categories, sample distinguishable colors from Viridis. Use a suitable diverging palette when the scientific variable is genuinely diverging.

Figures should be reproducible, labeled with units, state the analyzed population and N where relevant, and never silently remove outliers, transform data, smooth data, or change population definitions.

A requested scientific figure is published to the appropriate report section by default. Only the sanitized derived figure is copied to `gh-pages`; the underlying dataset remains local unless explicitly intended for publication.

## Updating this template

OpenAI desktop/Remote behavior and GitHub interfaces can change. When starting a new project, verify the linked official documentation if the setup screens differ from this README.

## Author

**Donato Giovannelli**  
Giovannelli Lab
