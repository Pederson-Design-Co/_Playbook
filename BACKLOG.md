# BACKLOG.md — cross-project work

Work that touches more than one project, or the law itself. A project's own work stays in
its own `BACKLOG.md`. Same shape as any backlog: ordered, an ID a gate can name, a `Why`, a
`Ref`; an item is deleted when it ships.

---

## The order of work

| # | What | Blocked by | State |
|---|---|---|---|
| P-01 | Move `quail-api` under the `Pederson-Design-Co` GitHub account; decide branch protection | — | open |
| P-02 | Move the project folders under `~/Projects/` | — | open |

**P-01: move `quail-api` under the `Pederson-Design-Co` GitHub account; decide branch protection.**
- Why: `kestrel`, `quail`, `studio` and `_Playbook` live under `Pederson-Design-Co`;
  `quail-api` still lives under `reydeus`, Sam's personal account. One account means one place
  to look and one set of permissions. Separately, GitHub refuses branch protection (the lock
  that stops a red check from being merged into `main`) on a private repo under the free plan;
  `studio` runs unlocked for now, which only matters once someone other than Sam commits or a
  commit comes from a machine without the doorman.
- Decisions: `_Playbook` went public on 2026-09-19 so a GitHub job can check it out without a
  token; it holds no code and no credentials. `main` on `studio` stays unlocked (Sam's ruling,
  2026-09-19); the options when revisited are GitHub Pro, or making a repo public. The
  `quail-api` transfer is done as a dedicated subphase with step-by-step instructions.
- Ref: `git remote -v` in each repo; the 403 from `gh api .../branches/main/protection`,
  2026-09-19.

**P-02: move the project folders under `~/Projects/`.**
- Why: `~/Developer/` is named for code, but tier 1 and 2 projects are not code. One neutral
  parent, one sibling rule (Sam's ruling, 2026-09-19).
- Decisions: `_Playbook` and `studio` move from `~/Developer/`; `kestrel` and `quail` move from
  `~/Desktop/`. Each move follows PRINCIPLES.md rule 10 (copy, verify, then delete), and every
  path written in a doc is updated in the same change. `.env` files travel with their repo
  and are never copied anywhere else.
- Ref: `_Playbook/CLAUDE.md`, "Where this folder has to sit"; `setup/CHECKLIST.md` item 1.
