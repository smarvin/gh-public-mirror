# README — Private Editorial Repository

## Purpose

The private repo is the **source of truth** for the website.

It handles:

* Editorial review
* Syncing public contributions
* Building the Jekyll site
* Publishing to GitHub Pages
* Mirroring published content back to the public repo

---

## Branches and their roles

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

## Typical workflow

### Public contributions

1. Public PR merged into public repo
2. Private repo auto-pulls into `content`
3. Bot opens PR: `content → current`
4. Editors review and merge

### Private writers

1. Writers work in feature branches or directly in `current`
2. Editors merge into `current`
3. When ready, merge `current → main`
4. This triggers:

   * Jekyll build
   * Site deploy
   * Sync to public mirror

---

## Publishing rules

* Only `main` is published
* Only `current → main` triggers publishing
* Nothing from `content` is published directly

---

## Automation overview

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

## For editors

You are responsible for:

* Reviewing public contributions
* Resolving conflicts
* Deciding when to publish

Automation helps you, but never replaces judgment.

---

## For writers

* Work in a feature branch and then push to `current`
* Do not commit directly to `main`

---

## Safety principles

* Public never writes directly to published content
* All publishing is intentional
* Automation never removes human checkpoints
