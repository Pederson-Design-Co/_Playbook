# CHECKLIST.md — what a finished setup looks like

Run this after `/new-project`, and again whenever an existing folder is retrofitted.

---

## Structure

- [ ] The folder sits directly under `~/Developer/`, beside `_Playbook`, not nested inside
      another project.
- [ ] `CLAUDE.md` exists and points at `../_Playbook/PRINCIPLES.md` and `WORKFLOW.md`.
- [ ] **`CLAUDE.md` is the only entry pointer.** These projects are worked on with Claude
      Code only, so Claude-specific files (hooks, settings, memory) are allowed; a second
      entry pointer under another name is not (`_Playbook/CLAUDE.md`, "The entry pointer").
- [ ] Machinery is in capitals (`CLAUDE` `STATUS` `BACKLOG` `RULES`), content is
      lowercase-kebab (`current.md` `facts.md`). No prefixes (setup/PATTERNS.md).
- [ ] **No `PRINCIPLES.md` or `WORKFLOW.md` in the project folder.** `find . -name "PRINCIPLES.md"`
      run from `~/Developer/` returns exactly one result.
- [ ] Every file created has content. No empty stubs, no placeholder headings
      (PRINCIPLES.md rule 8).
- [ ] **At most four subfolders**, named `sources/`, `docs/`, `deliverables/`, `assets/`
      (setup/PATTERNS.md). A fifth name means one of the four was not understood. Code and
      asset libraries are exempt from this one — not from the machinery.
- [ ] **No `README.md` anywhere in the project.** `CLAUDE.md` is the only entry pointer;
      `sources/REGISTER.md` is the only ledger. (A code library that is published may need
      one for its readers; that is a deliverable, and the call is recorded in `CLAUDE.md`.)
- [ ] **No `GLOSSARY.md` in the project folder.** Subject-specific terms live in this
      project's `docs/glossary.md`, lowercase because it is content and not machinery.

## Content

- [ ] `CLAUDE.md` states what the project is for, in one sentence, and carries its own map of where things go.
- [ ] The STATUS file describes the actual current position, not a template.
- [ ] The BACKLOG file holds real work items, ordered so earlier ones unblock later ones.
- [ ] If a RULES file exists, every rule in it is specific to this project. Anything that would
      be true of another project belongs in `PRINCIPLES.md` and was moved there instead.
- [ ] If `sources/` exists, `sources/REGISTER.md` registers every file: name, status
      (record or proposal), origin, date, and what it was extracted into.
- [ ] If a FACTS file exists, every entry carries a status from that file's own status list
      and the exact check that would settle it.

## Boundaries

- [ ] The CURRENT file contains no proposals. The PROPOSAL file contains no records.
- [ ] Every claim about behavior names its source.
- [ ] Nothing in `sources/` has been edited.
- [ ] No fact in this project is also stated in another project (PRINCIPLES.md rule 6).
      Check against `_Playbook/` and every sibling project.

## Code project

For a project that produces code (setup/PATTERNS.md, "Where this stops"):

- [ ] The gate files come from `setup/code-project/` with every `{{…}}` filled: `package.json`,
      `.nvmrc`, `tsconfig.base.json`, `tsconfig.json`, `eslint.config.js`, `lefthook.yml`,
      `.github/workflows/check.yml`, `scripts/check-docs.ts`, `.gitignore`.
- [ ] `npm run typecheck && npm run lint && npm run check` exit 0 on the empty project.
- [ ] `.git/hooks/pre-commit` exists (lefthook installed), and a commit carrying a deliberate
      violation is refused.
- [ ] The repo lives under `Pederson-Design-Co`, and the first push shows a green `check` run.
- [ ] RULES.md § Never is mirrored in `eslint.config.js`'s Never block, one line per rule that
      an import can violate.

## Working

- [ ] Telling any assistant to read `CLAUDE.md` and then asking a question produces a reply
      that ends in a numbered gate.
- [ ] A sibling project can be read from here — confirm with one read of
      `../_Playbook/PRINCIPLES.md`.

---

## Retrofit additions

For a folder that existed before `_Playbook`:

- [ ] Its old `PRINCIPLES.md` and `WORKFLOW.md` are deleted, and anything project-specific in them
      was moved to `RULES.md` first. Read them before deleting — they hold real decisions.
- [ ] Its `CLAUDE.md` no longer describes the reply format or the verify loop; it points at
      `_Playbook` for both.
- [ ] Its documents follow the naming convention, and every internal reference to the old
      names was updated in the same change.
- [ ] Its subfolders were mapped onto the four. Anything that fitted none of them was a
      judgement call, and the call is recorded in `CLAUDE.md`.
- [ ] Every `WORKFLOW.md §N` and `PRINCIPLES.md rule N` citation in it names a section or
      rule that exists. Both files have been trimmed before. A `BACKLOG.md` that *records* a
      broken citation elsewhere will trip this check — write those as "section 8" in prose,
      never with the §, so the two cannot be confused.
- [ ] Loose files at the folder root are sorted into the spine, or a reason is recorded for
      each one that stays loose.
- [ ] Its facts were compared against every sibling project and duplicates replaced with
      pointers.
