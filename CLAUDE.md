# _Playbook — start here

**Claude, working in this folder or any sibling project folder: read this first.**

This file is the entry pointer. It holds the read order and nothing else. Every rule lives
in the files it names.

## Read order, at the start of every session

1. **`_Playbook/PRINCIPLES.md`** — the principles. What may be written and what may not.
2. **`_Playbook/WORKFLOW.md`** — how a message is handled, the shape of every reply, and
   how a claim becomes a fact.
3. **The project's own `CLAUDE.md`** — what this particular folder is for and where its
   things go.
4. **The project's `RULES.md`**, if it has one — principles specific to that subject.

Do not skip 1 and 2 because a task looks small. The reply format and the gate rule apply to
every turn, including answers to questions.

## When you meet a name or a term you do not know

Look it up before asking, and before guessing. A subject-specific term lives in that
project's `docs/glossary.md`, if the project has one. If it is defined nowhere, that is
itself worth recording — an undefined term used in practice is a defect (PRINCIPLES.md
rule 5).

## The four rules that catch most mistakes

- A proposal is never written as a record (PRINCIPLES.md rule 3).
- A claim is not a fact until it was run and the result pasted back (PRINCIPLES.md rule 4).
- Every reply ends with a numbered gate (WORKFLOW.md §1).
- There is no trivial exception. A one-line fix, a doc update the reply itself proposed, a
  consequential edit in another file: each is a gate option before it happens. Naming a fix
  is a proposal; only the pick is the go (WORKFLOW.md §3).

## What lives here

Two layers. The root holds the law every project is measured against. `setup/` holds the
process that makes a project able to be measured. Nothing here is a project, which is why
nothing here carries a `STATUS.md`.

```
_Playbook/
├── CLAUDE.md                      this file — the read order and the map
├── PRINCIPLES.md                  the principles — the only copy
├── WORKFLOW.md                    how we work — the only copy
├── BACKLOG.md                     cross-project work: moves, accounts, the law itself
└── setup/                         how a project is made
    ├── PATTERNS.md                the tiers, the four folders, the naming convention
    ├── INTERVIEW.md               the questions asked before a project is scaffolded
    ├── CHECKLIST.md               what a finished setup looks like
    ├── code-project/              the gate a code repo starts from: checks, doorman, workflow
    └── templates/                 the blank forms the three above copy from
        ├── claude-template.md
        ├── backlog-template.md
        ├── current-template.md
        ├── facts-template.md
        ├── proposal-template.md
        ├── rules-template.md
        ├── sources-register-template.md
        └── status-template.md
```

**A template is named for what it is, not for what it becomes.** It is not load-bearing, so
it does not wear capitals (`setup/PATTERNS.md`, "Machinery and content"). That also keeps
`find . -name "CLAUDE.md"` returning one result per project and one from here.

## Where this folder has to sit

`_Playbook` and every project folder are **siblings inside one parent folder.** Nothing
here is nested inside a project, and no project is nested inside this.

```
~/Developer/
├── _Playbook/            ← this folder
├── studio/
└── ...
```

**This is a requirement, not a preference.** Every project's `CLAUDE.md` opens by pointing at
`../_Playbook/PRINCIPLES.md`, and `../` means the folder next door. Move a project somewhere
else, or copy one out on its own, and its first instruction resolves to nothing: the rules
become invisible and the assistant proceeds without them, silently.

A project that arrives on a new machine without `_Playbook` beside it is not set up yet.
Put the two side by side before opening either.

## Starting a new project

The process is `setup/INTERVIEW.md`, then `setup/PATTERNS.md` to pick a tier, then write
from `setup/templates/`, then verify with `setup/CHECKLIST.md`.

Tell Claude to run the process in `setup/`. It is written to be followed step by step and
needs nothing installed.

Do not copy a previous project's folder as a starting point. That is how three
constitutions came to exist.

## The entry pointer

Every project folder carries exactly one: **`CLAUDE.md`**.

These are personal projects worked on with Claude Code only, so the files may be
Claude-specific: the entry pointer is the file Claude reads on its own, and hooks, memory
and wording may assume Claude. (Sam's ruling, 2026-09-19. At work, where the tool varies,
the entry pointer is tool-neutral instead; that convention does not apply here.)

## The rule that matters most here

`PRINCIPLES.md` and `WORKFLOW.md` exist **once**. No project holds its own copy. A project's own
principles go in its `RULES.md` — never by forking the frozen files (WORKFLOW.md §7).

Sibling projects reference these as `../_Playbook/PRINCIPLES.md`.
