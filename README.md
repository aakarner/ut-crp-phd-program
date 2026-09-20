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
  proposal-defense/index.md          Adopted text, verbatim, with transcription notes
  dissertation-defense/index.md      Adopted text, verbatim, with transcription notes
  three-article-dissertation/index.md
  methods-requirements/index.md      Qual/quant requirements and recommended course lists
```

## Conventions

- Each policy lives in its own folder under `policies/`, with `index.md` as the current text.
- Every policy page begins with a status table: **Status** (Adopted / Draft), **Supersedes**, **Prepared by** or **Adopted**.
- When a draft is adopted, rename the previous adopted file by its date (e.g., `2025-07-adopted.md`), make the draft the new `index.md`, and update the status header and the home page table.
- The role is always written **PhD Program Coordinator**.
- The unit's name is **Graduate Program in Community and Regional Planning** when naming it as an institution (headers, bylines, footer). The doctoral track within it is "the PhD program" (descriptive, no "in Community and Regional Planning" tail). Never the bare "Program in Community and Regional Planning."
- This repository is public. It holds policy text only: no student records, exam questions, essays, grades, or correspondence.

## How to edit

The pages are plain Markdown text files. Two ways to change them:

**On GitHub (no software needed).** Open the file in the repository, click the pencil icon, make your change, and click "Commit changes." Good for quick fixes.

**Locally.** Clone the repository, open the `.md` file in any plain-text editor (VS Code, TextEdit in plain-text mode, etc.), save, then in a terminal:

```
git add -A
git commit -m "Short description of the change"
git push
```

Either way, the site rebuilds itself within a minute or two of the change reaching `main`. No build step, no local install.

Things to keep intact when editing:

- The block between the `---` lines at the top of each file (`title`, `nav_order`, `parent`, `has_children`) controls the sidebar. Leave it alone unless you are renaming or moving a page.
- Two trailing spaces at the end of a line force a line break. That is how the three address lines under each title stack.
- Tables are rows of `|` and `-`. Keep the same number of `|` in every row.
- Links to sibling pages use the `.md` filename, e.g. `[what changed](changes.md)`. GitHub converts them to `.html` when it builds the site.
- `# Heading` is a page title, `## Heading` a section, `### Heading` a subsection. `**bold**`, `*italic*`, `- ` for a bulleted list.

Do not hand-edit `diff.html` or `changes.diff`. They are generated from `index.md` and `2025-07-adopted.md` and should be regenerated when either of those changes (with `git diff --no-index` and Python's `difflib.HtmlDiff`, or by asking an assistant to redo them). `changes.md` is hand-written and can be edited freely.

## Adding a new policy

1. Create a folder under `policies/`, e.g. `policies/masters-equivalency/`.
2. Add `index.md` with a front-matter block like the comprehensive exam one (`title`, `nav_order`, and `has_children: true` if there will be sub-pages), the three-line program header, and a status table.
3. If migrating an existing adopted policy, add the adopted text as a dated file (e.g., `2025-04-adopted.md`) with `parent:` set to the policy title.
4. Add a row to the table on the home page (`index.md` at the repository root).

## Publishing

Settings → Pages → Build and deployment: Source "Deploy from a branch", branch `main`, folder `/ (root)`. GitHub builds the site with Jekyll; no local install is needed. Changes appear a minute or two after each push.
