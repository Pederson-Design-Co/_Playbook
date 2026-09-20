# PRINCIPLES.md

Eleven rules. They hold in every folder under this root: a template folder, a data project,
a component library, an accessibility pass. If a rule here would not make sense in a project
that has not been started yet, it does not belong here.

Anything specific to one subject (how progress is measured, what makes an element
certified, how a query becomes a fact) lives in that project's `RULES.md`.

This file and `WORKFLOW.md` change only when Sam explicitly orders it, and only after the
exact new wording has been approved at a gate.

---

**1. Only a gate pick authorizes work.**
Agreement reached while thinking something through is not a go. It is input to a proposal,
which is then gated like anything else.

**2. Every reply ends with a numbered gate.**
Whatever its shape: a change, an answer, a question handed back. A reply without a gate has
decided on Sam's behalf that there was nothing to choose.

**3. Never write a proposal as if it were a record.**
How something works today and how it should work are different claims. A proposal that reads
as a record travels: it gets quoted in a meeting, then built on, and nobody upstream knows it
was an idea.

**4. Never state as fact something you have not checked.**
Not because it is reasonable, not because an earlier document said it, not because it was
inferred. Unchecked claims are written as unchecked, in those words.

**5. Every claim says where it came from.**
A document, a query, an observation, or a person and a date. A sentence that names nothing is
a defect, whoever wrote it.

**6. One fact, one home.**
Stated in exactly one place; everywhere else points to it. A fact stated twice drifts, and the
copy that drifts is the one someone reads.

**7. Present state only.**
Docs say what is true now. No "used to", no "superseded", no narrating the document's own
history. When something changes, replace the wording. Originals in `sources/` are the
exception: they only accumulate and are never edited.

**8. Build only what something needs now.**
No empty stubs, no placeholder headings, no structure for material that has not arrived. A
rule governing something that does not exist is speculative surface too.

**9. When two things disagree, stop and surface both.**
A doc against reality, a doc against another doc, a number that does not reproduce. Do not
pick the convenient one. Bring both sides, decide which is right, and fix both in the same
change.

**10. Copy, verify, then delete.**
Before anything that rewrites, moves, or deletes more than one file. Never move across drives
in one command. That is a copy and a delete wearing one name, and it destroys the source
if the copy fails. A file another process holds open is a stop, not a retry.

**11. HTML is for delivery only.**
A page authored to be published, or a mockup built to be looked at. Everything else
(notes, records, references, sources of truth) is Markdown. HTML is how something is
delivered, not how it is kept. Knowledge held in markup is harder to read, harder to correct,
and harder to compare against what replaced it.
