# INTERVIEW.md — the questions asked before a project is scaffolded

Asked in order. Answers determine the tier, which files get written, and what goes in each.

**Ask as multiple-choice wherever the options are knowable**, two to four options each, with
one marked as the recommendation. Explanations go in the reply, never inside the options.
Stop and ask a follow-up when an answer opens a real fork; do not batch every question and
build blind.

---

## Round 1 — What this is

**1. What is this project for, in one sentence?**
Free text. This becomes the first line of `CLAUDE.md` and the north star in the RULES file if
one is needed.

**2. What does the folder produce?**
- an action performed repeatedly → Tier 1
- an understanding of how something works → Tier 2
- an artifact someone else uses → Tier 3

**3. Who reads the output?**
- only you
- your team
- leadership or partners
- the public

Anything past "only you" means the record/proposal split has to be visible in the
deliverable, not just in the working docs.

**4. Is this finished work or ongoing?**
- a one-time deliverable with an end
- ongoing, revisited whenever something changes

Ongoing projects need `STATUS.md` maintained; one-time ones mostly do not.

---

## Round 2 — Where the material comes from

**5. What material already exists, and where is it?**
Free text, then confirmed by listing the paths. Anything named here gets registered in
`sources/REGISTER.md` at scaffold time rather than later.

**6. Does this project make claims about data or systems that could be checked?**
- yes, and the checks are queries → `docs/facts.md` plus `deliverables/`
- yes, but the checks are interface steps → `docs/facts.md` only
- no, it is a build project → skip the facts ledger

**7. Does it share data or definitions with another project?**
If yes, the definitions live in exactly one of them and the other points there
(PRINCIPLES.md rule 6). Decide which at scaffold time, not later.

**8. Are there terms that could be read more than one way?**
- yes → `docs/glossary.md` is created now, with the disputes as its first entries
- not yet → it is created when the first dispute appears

---

## Round 3 — How you want to work

**9. Does this project need rules that differ from PRINCIPLES.md?**
Examples: a formatting standard, a domain principle, a definition of "done". If yes, they go
in `RULES.md` and the interview collects them here rather than discovering them later.

**10. What does "done" look like for one unit of work?**
Free text. Shapes what `STATUS.md` tracks and what a gate offers.

**11. Anything that must never happen?**
Examples: never write to a production table, never edit a source file, never publish without
review. These become the first entries in `RULES.md`.

---

## Round 4 — Confirm before writing

Show the file list that will be created, one line each, and gate it. Nothing is written
until Sam picks a number.

After writing, the first reply names every file created, what each holds, and what is still
empty and why — then gates the next step.

---

## What the interview must not do

- **Do not create empty files.** If an answer says a document is not needed yet, it is not
  created. Saying "we'll fill it in later" is how placeholder structure gets built
  (PRINCIPLES.md rule 8).
- **Do not copy another project's content.** Templates only.
- **Do not write PRINCIPLES.md or WORKFLOW.md into the project.** They live once
  (WORKFLOW.md §7).
- **Do not name an AI assistant in any file.** The documents must work whichever tool reads
  them.
- **Do not assume the tier from the folder name.** Ask question 2.
