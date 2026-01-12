# README — Public Mirror Repository

## Purpose

This repository is a **public contribution mirror** for the project. It exists so external contributors can:

* Propose edits to site content
* Submit pull requests
* Participate without access to the private editorial repo

This repo does **not** build or publish the website. It only sends contributions onward.

---

## How this repo works

* Default branch: `mirror`
* Contributors edit files and open PRs against `mirror`
* When a PR is merged:

  * A workflow notifies the private repo
  * The private repo pulls changes into its `content` branch
  * Editors review before publishing

Nothing you merge here goes live automatically.

---

## How to contribute

1. Click "Edit this page" on the website, or edit files here directly.
2. Commit to your fork or branch.
3. Open a Pull Request targeting `mirror`.
4. Wait for editors to review and merge in the private repo.

---

## What not to change

Do not:

* Add workflows
* Change repository settings
* Modify infrastructure files

This repo is intentionally "dumb": content in, messages out.

---

## What happens after you merge

1. Your PR is merged into `mirror`
2. A workflow notifies the private repo
3. Editors review your changes
4. If approved, changes are published to the website


