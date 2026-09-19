# ut-crp-phd-program

Document repository and website for the PhD program of the Graduate Program in Community and Regional Planning at The University of Texas at Austin.

The site is published with GitHub Pages at <https://aakarner.github.io/ut-crp-phd-program/>.

## Layout

```
index.md                         Home page: list of policies and their status
_config.yml                      Site configuration (Jekyll, just-the-docs theme)
policies/
  comprehensive-exam/
    index.md                     Current text (draft or adopted; see status header)
    2025-07-adopted.md           Text as adopted July 2025, for reference
    changes.md                   Summary of what changed and why
    diff.html                    Side-by-side line diff of the two versions
    changes.diff                 Unified diff (for git/GitHub users)
```

## Conventions

- Each policy lives in its own folder under `policies/`, with `index.md` as the current text.
- Every policy page begins with a status table: **Status** (Adopted / Draft), **Supersedes**, **Prepared by** or **Adopted**.
- When a draft is adopted, rename the previous adopted file by its date (e.g., `2025-07-adopted.md`), make the draft the new `index.md`, and update the status header and the home page table.
- The role is always written **PhD Program Coordinator**.
- This repository is public. It holds policy text only: no student records, exam questions, essays, grades, or correspondence.

## Publishing

Settings → Pages → Build and deployment: Source "Deploy from a branch", branch `main`, folder `/ (root)`. GitHub builds the site with Jekyll; no local install is needed. Changes appear a minute or two after each push.
