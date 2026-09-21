# BACKLOG.md — cross-project work

Work that touches more than one project, or the law itself. A project's own work stays in
its own `BACKLOG.md`. Same shape as any backlog: ordered, an ID a gate can name, a `Why`, a
`Ref`; an item is deleted when it ships.

---

## The order of work

| # | What | Blocked by | State |
|---|---|---|---|
| P-01 | Branch protection on `main` is unavailable on private repos under the free plan | — | open |
| P-02 | Move the project folders under `~/Projects/` | — | open |
| P-03 | Sam's teaching projects are unpublished and exist only in his memory | — | open |

**P-01: branch protection on `main` is unavailable on private repos under the free plan.**
- Why: GitHub refuses the lock that stops a red check from being merged into `main` on a
  private repo unless the organization is on GitHub Pro. `studio` runs unlocked, which only
  matters once someone other than Sam commits, or a commit comes from a machine without the
  doorman. Every repo now lives under `Pederson-Design-Co` (`quail-api` transferred from
  `reydeus` on 2026-09-19), so this is the last piece of the GitHub setup left open.
- Decisions: `_Playbook` went public on 2026-09-19 so a GitHub job can check it out without a
  token; it holds no code and no credentials. `main` on `studio` stays unlocked (Sam's ruling,
  2026-09-19); the options when revisited are GitHub Pro, or making a repo public.
- Ref: the 403 from `gh api .../branches/main/protection`, 2026-09-19.

**P-02: move the project folders under `~/Projects/`.**
- Why: `~/Developer/` is named for code, but tier 1 and 2 projects are not code. One neutral
  parent, one sibling rule (Sam's ruling, 2026-09-19).
- Decisions: `_Playbook` and `studio` move from `~/Developer/`; `kestrel` and `quail` move from
  `~/Desktop/`. Each move follows PRINCIPLES.md rule 10 (copy, verify, then delete), and every
  path written in a doc is updated in the same change. `.env` files travel with their repo
  and are never copied anywhere else.
- Ref: `_Playbook/CLAUDE.md`, "Where this folder has to sit"; `setup/CHECKLIST.md` item 1.

**P-03: Sam's teaching projects are unpublished and exist only in his memory.**
- Why: a 2km solar system model with the sun as an exercise ball and Uranus 2km away; a
  life-size running track designed with geometry and then run on; flags built from
  perpendicular constructions, after Nepal's constitution, which specifies its own. These are
  the one asset nobody else has, and they are currently nowhere. Publishing them is also the
  only honest route to the marketplace Sam wants to build instead of Teachers Pay Teachers: a
  marketplace dies without an audience, and writing builds the audience a marketplace would
  later need. It needs no code, so it runs alongside studio rather than competing with it.
- Decisions: not a project folder yet (Sam's ruling, 2026-09-21); it becomes one through
  `setup/INTERVIEW.md` if he starts writing. TPT's actual split is 55 percent on a Basic
  account and 80 percent on Premium at $59.95 a year, with a one-time $29 to open a Basic store
  since early 2024 — so the grievance that survives is the entry fee and the squeeze on small
  sellers, not a 50 percent cut. IXL Learning acquired TPT on 2 March 2023.
- Ref: the app-selection session, 2026-09-21; TPT's seller fees and payout rates help page and
  K-12 Dive on the IXL acquisition, both read 2026-09-21.
