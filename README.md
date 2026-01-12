# README — Public Mirror Repository

## Purpose

This repository is a **public contribution mirror** for the project. It exists so external contributors can:

* Propose edits to site content
* Submit pull requests
* Participate without access to the private editorial repo

This repo does **not** build or publish the website. It only sends contributions onward.

---

## How This Repo Works

* Default branch: `mirror`
* Contributors edit files and open PRs against `mirror`
* When a PR is merged:

  * A workflow notifies the private repo
  * The private repo pulls changes into its `content` branch
  * Editors review before publishing

Nothing you merge here goes live automatically.

---

## How to Contribute

1. Click "Edit this page" on the website, or edit files here directly.
2. Commit to your fork or branch.
3. Open a Pull Request targeting `mirror`.
4. Wait for editors to review and merge in the private repo.

---

## What Not to Change

Do not:

* Add workflows
* Change repository settings
* Modify infrastructure files

This repo is intentionally "dumb": content in, messages out.

---

## What Happens After You Merge

1. Your PR is merged into `mirror`
2. A workflow notifies the private repo
3. Editors review your changes
4. If approved, changes are published to the website

---

# README — Private Editorial Repository

## Purpose

This is the **source of truth** for the website.

It handles:

* Editorial review
* Syncing public contributions
* Building the Jekyll site
* Publishing to GitHub Pages
* Mirroring published content back to the public repo

---

## Branches and Their Roles

| Branch    | Purpose                                              |
| --------- | ---------------------------------------------------- |
| `content` | Staging area for raw content (from public + writers) |
| `current` | Editorial working branch                             |
| `main`    | Published site                                       |

Flow:

```
Public Repo → content → current → main → Website + Public Mirror
```

---

## Typical Workflow

### Public Contributions

1. Public PR merged into public repo
2. Private repo auto-pulls into `content`
3. Bot opens PR: `content → current`
4. Editors review and merge

### Private Writers

1. Writers work in feature branches or directly in `current`
2. Editors merge into `current`
3. When ready, merge `current → main`
4. This triggers:

   * Jekyll build
   * Site deploy
   * Sync to public mirror

---

## Publishing Rules

* Only `main` is published
* Only `current → main` triggers publishing
* Nothing from `content` is published directly

---

## Automation Overview

Automated:

* Public → content sync
* PR creation from content → current
* Build + deploy on main
* main → public mirror sync

Manual:

* Review content
* Merge content → current
* Merge current → main

---

## For Editors

You are responsible for:

* Reviewing public contributions
* Resolving conflicts
* Deciding when to publish

Automation helps you, but never replaces judgment.

---

## For Writers

* Prefer working in feature branches or `current`
* Do not commit directly to `main`
* Expect editorial review before publishing

---

## Safety Principles

* Public never writes directly to published content
* All publishing is intentional
* Automation never removes human checkpoints

That’s by design.
