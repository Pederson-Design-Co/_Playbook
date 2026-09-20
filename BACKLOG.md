# BACKLOG.md — cross-project work

Work that touches more than one project, or the law itself. A project's own work stays in
its own `BACKLOG.md`. Same shape as any backlog: ordered, an ID a gate can name, a `Why`, a
`Ref`; an item is deleted when it ships.

---

## The order of work

| # | What | Blocked by | State |
|---|---|---|---|
| P-01 | Move every repo under the `Pederson-Design-Co` GitHub account, and put `_Playbook` there too | — | open |
| P-02 | Move the project folders under `~/Projects/` | — | open |
| P-03 | Claude asks permission for routine terminal commands it could just run | — | open |

**P-01: move every repo under the `Pederson-Design-Co` GitHub account, and put `_Playbook` there too.**
- Why: `kestrel` and `quail` already live there; `quail-api` lives under `reydeus`; `studio`
  has no remote; `_Playbook` is on one Mac with no history. One account means one place to
  look, one set of permissions, and every piece of the law and the code backed up.
- Decisions: Sam wants this done as a dedicated subphase with step-by-step instructions, not
  as a side effect of other work (2026-09-19). `_Playbook` becomes a private repo of its own,
  since it is a sibling of every project, not part of one.
- Ref: `git remote -v` in each repo, 2026-09-19.

**P-02: move the project folders under `~/Projects/`.**
- Why: `~/Developer/` is named for code, but tier 1 and 2 projects are not code. One neutral
  parent, one sibling rule (Sam's ruling, 2026-09-19).
- Decisions: `_Playbook` and `studio` move from `~/Developer/`; `kestrel` and `quail` move from
  `~/Desktop/`. Each move follows PRINCIPLES.md rule 10 (copy, verify, then delete), and every
  path written in a doc is updated in the same change. `.env` files travel with their repo
  and are never copied anywhere else.
- Ref: `_Playbook/CLAUDE.md`, "Where this folder has to sit"; `setup/CHECKLIST.md` item 1.

**P-03: Claude asks permission for routine terminal commands it could just run.**
- Why: the 2026-09-19 settings guard (`~/.claude/settings.json`, `permissions`) makes every
  file edit, delete, move, commit and push ask first, which Sam wants. It also left the
  session in the mode where every other terminal command asks too (`npm install`, `npx tsc`,
  `ls`), which he does not: during 2a he clicked "yes" a dozen times for commands that change
  nothing he cares about. Editing STATUS.md and the other docs must keep asking; running a
  check, reading a file, or installing a declared dependency should not.
- Decisions: the ask list for edits, deletes, moves, commits and pushes stays. What changes is
  an allow list for the routine commands. Claude Code has a built-in helper for this
  (`/fewer-permission-prompts`) that reads past sessions and proposes the list.
- Ref: `~/.claude/settings.json` after the 2026-09-19 edit; the 2a transcript.
