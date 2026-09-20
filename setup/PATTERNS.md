# PATTERNS.md — which documents a project needs

Three tiers. The interview picks one, then adds or drops individual files. Nothing is
created that has no content waiting for it (PRINCIPLES.md rule 8) — a tier is a menu, not a mandate.

---

## Tier 1 — Task

For a folder that **executes** something rather than building understanding. A runbook, a
recurring report, a set of assets.

```
<project>/
├── CLAUDE.md              entry pointer, scope, and this project's map
├── STATUS.md       where we are, what's next
└── BACKLOG.md      ordered work and open questions
```

Add `RULES.md` only if this project has principles that differ from PRINCIPLES.md.

**Examples:** a release checklist run before every App Store submission.

---

## Tier 2 — Research

For a folder that **builds understanding** of how something works, from material supplied by
other people. The verification loop is the whole point.

```
<project>/
├── CLAUDE.md · STATUS.md · BACKLOG.md
├── docs/
│   ├── current.md    how it works today — records only
│   ├── facts.md      checkable claims — the verify ledger
│   └── glossary.md   terms specific to this subject
└── sources/          originals, unaltered
    └── REGISTER.md   file, status, origin, dated, extracted into
```

Add `docs/proposal.md` the moment a design intent exists.

**Examples:** working out how App Store review, EU trader rules, or a payment SDK actually
behave before building on them.

---

## Tier 3 — Build

For a folder that **produces** something — a system, a page, a deliverable that ships.

```
<project>/
├── CLAUDE.md
├── RULES.md · STATUS.md · BACKLOG.md
├── docs/              the contracts: what each thing is and why
├── sources/           originals, unaltered
├── deliverables/      what leaves the folder
└── assets/            images and media the deliverables use
```

A RULES file is required here, because build projects always have their own standards —
naming, formatting, what "done" means.

**Examples:** a set of App Store screenshots and listing copy.

`studio` produces something too, but the thing it produces is code. See "Where this stops"
below — it carries the machinery files and nothing else from this tier.

---

## Choosing between them

The test is **what the folder produces**:

| It produces | Tier |
|---|---|
| an action performed on a schedule | 1 |
| an understanding of how something works | 2 |
| an artifact someone else uses | 3 |

A project that starts at 1 and grows to 2 adds `docs/` and `sources/` when the first real
content arrives. That is normal and is not a mistake. Creating them empty on day one is.

---

## The four folders

A project has at most four subfolders. Everything a project accumulates is one of these, and
a fifth name means one of the four was not understood.

| Folder | Holds | The test |
|---|---|---|
| `sources/` | originals, exactly as they arrived | someone outside this folder made it |
| `docs/` | what we know and have checked | we wrote it, and it is about the subject |
| `deliverables/` | what leaves the folder | someone reads or runs it somewhere else |
| `assets/` | images, video and PDFs the deliverables use | it is embedded in something, not read on its own |

A query is a deliverable — it runs somewhere else. A screenshot inside a document is an
asset. A meeting transcript is a source. A page you wrote explaining the subject is a doc.

`sources/` carries a `REGISTER.md`: what each original is, where it came from, when it was
true, and what supersedes it. Originals are never edited (PRINCIPLES.md rule 7); the register
is how a superseded one gets marked.

None of the four is created before it has content (PRINCIPLES.md rule 8).

---

## Where this stops

`studio` is a code library. The folder is the product, its structure is dictated by what the
code and its tooling need, and some of its names appear inside shipped identifiers. The
four folders do not apply inside it.

The machinery files do. Every project carries `CLAUDE.md`, `STATUS.md` and `BACKLOG.md`
regardless of what it holds.

**A code project also carries the gate**, copied from `setup/code-project/` on day one, before
any code: three checks (`typecheck`, `lint`, `check`) that run before every commit (lefthook)
and on every push (GitHub Actions). `check` is the docs checker: it reads the machinery docs
as claims and the folder as the truth, so a doc that names a file that does not exist, or a
backlog ID with no item, refuses the commit. It also refuses a doc past its size cap
(CLAUDE.md and STATUS.md 60 lines, RULES.md 160, BACKLOG.md 200, any `docs/*.md` 300: split
it or delete something, never append past the cap), and a gate file that has drifted from the
template (`check-docs.ts`, `tsconfig.base.json`, `lefthook.yml`, `.nvmrc`, and the four-rules
block in CLAUDE.md stay identical to the template; change the template and every project in
one commit), and a doc with Windows line endings. The gate is green on an empty project, and a project whose gate is not green is
not set up. A framework's own lint base (Expo's, for an Expo app) replaces the template's
generic one; the Never block stays.

`_Playbook` is exempt too, and for a different reason: it is not a project. It is what
projects are measured against. Its `setup/` holds the scaffolding process, which is neither a
source, a doc, a deliverable nor an asset — it is the thing that creates all four.

---

## Naming

### Machinery and content

Two kinds of file, and they should not look alike.

**Machinery** — the rules and the state. Identical filenames in every folder, governs the
work: `CLAUDE.md`, `STATUS.md`, `BACKLOG.md`, and `RULES.md` where a project needs one.
Capitals.

**Content** — what the project has learned or been given. Varies by project, changes
constantly: `current.md`, `facts.md`, `glossary.md`, `proposal.md`. Lowercase.

Capitals mean load-bearing. `facts.md` is a working document; `WORKFLOW.md` is law. They
should not wear the same clothes.

**No prefixes.** Every folder uses the same filenames, so you always know what to look for.
The folder path says which project it is.

### The convention

| Style | Where | Examples |
|---|---|---|
| `ALL CAPS` | machinery only — the read-me-first files | `CLAUDE.md` `STATUS.md` `RULES.md` |
| `lowercase-kebab` | content, folders inside a project, and code repos | `current.md` `motion-lab/` `studio/` |
| `Title Case With Spaces` | top-level project folders that are not code, browsed in Finder | `App Store Notes` |
| `snake_case` | left alone where it already exists in an identifier | a library's own field names |

**Hyphens, not underscores, for anything new.** Both work; hyphens are the document
convention. The only real defect is mixing them in one place.

**Never a space in a filename.** Only in a folder name you browse. A space in a filename
breaks scripts, and it has already broken one here.

**No `README.md`, anywhere.** It means two different things in two different places — the way
into a folder, and the ledger of what a folder holds. `CLAUDE.md` is the only entry pointer;
`sources/REGISTER.md` is the only ledger. A file named README will be read as whichever one
the reader expected.

### Names that are frozen

Some names ship: a bundle ID, a package name, an import path, a database migration name.
These are **identifiers, not labels.** Renaming one breaks an installed app, a published
package, or an existing database. When a folder is both a project and an identifier, the
identifier wins: `studio` stays lowercase because it is a repo and a package scope, and its
`CLAUDE.md` says so.

Acronyms keep their casing. `_Playbook` keeps its underscore; it sorts to the top on purpose.

## Files that are never per-project

| File | Its one home |
|---|---|
| PRINCIPLES.md | `_Playbook/` |
| WORKFLOW.md | `_Playbook/` |

A project that wants either of these forks the frozen files and starts the drift over. It
references them instead.

There is no shared glossary yet. A term that only means something inside one subject stays
in that project's `docs/glossary.md`. The day two projects need the same definition, it
earns `_Playbook/GLOSSARY.md`, and the test for what goes there is: **would the definition
still be needed if every project were cancelled?**
