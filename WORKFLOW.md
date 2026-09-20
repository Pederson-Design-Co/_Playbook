# WORKFLOW.md

How work runs, in every folder under this root. `PRINCIPLES.md` outranks this file.

Process specific to one subject (a verification loop, a certification pass, an accessibility
check) lives in that project's `RULES.md`, not here.

---

## 1. The loop

1. **A phase ends. Plan the next one.** State the goal in a sentence, then list the subphases
   as `1a`, `1b`, `1c`, one focused piece of work each.
2. **Sam approves or edits the list.** Nothing is built until then.
3. **Build one subphase.** Never batch ahead.
4. **Reply with the checklist and the gate** (Section 2).
5. Repeat until the phase ends, then back to step 1.

A discovery mid-subphase inserts as `1a part 2` and finishes before `1b` starts.

**The phase list lives in `STATUS.md`**, updated in the same change that completes a subphase.
A subphase is not done until the file says so. Chat scrollback is not a record.

## 2. The reply

Every reply is built from three parts, in this order: the checklist, the blocks, the gate.
Only the gate is always present.

**The checklist** appears only when a subphase or phase has just finished. It is a state
readout, not an explanation, and stays flat:

- [x] **1a** Move the assets into one folder: 44 moved, 1,980 duplicates removed
- [x] **1b** Update references: 4 files repointed
- [~] **1c** Rename the four project folders: 2 renamed, 2 locked, 2 blocked
- [ ] **1d** Sort the loose files
- [ ] **1e** Delete the verified originals

Written as a markdown task list, never inside a code fence, so it renders as checkboxes rather
than literal brackets. The subphase ID is bold; the result follows a colon.

A ticked box is done and carries a one-line result. An empty box is still to come. A `[~]` box
is started and stopped: it names what blocked it, and clearing that blocker is the first thing
the gate offers. `[~]` renders as literal text rather than a checkbox, which is what marks it
out from the other two at a glance.

**The blocks** are everything the reply has to say, whatever the reply is for: an answer, a
brainstorm, a flagged pitfall, a question handed back, the account of a finished subphase. Each
block is a heading naming the topic, a sentence under it that answers, then bullets for the
detail, with a blank line between blocks. Someone who reads only the headings and their first
sentences has the reply; the bullets are there for whoever wants the evidence.

**One reply answers one question.** Five blocks is the ceiling. Needing more is the signal that
several topics arrived in one message, not that the reply is long: it names the topics it is
not covering, handles the one it is, and the gate offers the rest in turn. A long reply is a
planning failure, not thoroughness.

A one-sentence answer stays one sentence. Prose that runs for paragraphs under no heading is
the failure this replaces, and so is a block whose first sentence summarizes nothing.

**Everything surfaced gets a destination in the same reply.** A finding, a discrepancy, a
better idea, an unasked question: name where it goes before the gate, whether that is a gate
option, a `BACKLOG.md` item with its ID, a §4 stop, or a pop-up question for Sam to rule on.
"Noted" is not a destination, and an item with none is a defect. §3 covers what Sam raises;
this covers what the work turns up.

**The gate** ends every reply and has exactly three options.

Keep it short: one or two sentences per point. Sources are named, not explained.

**Mark one gate option as the recommendation.** Exactly one, every time. An unranked list hands
the ranking work back to Sam. A recommendation is never an action. The mark is its only
privilege.

**The gate is the question.** A request to ask one thing at a time is served by the gate, not
by replacing it. Three options with one recommendation is already a single question. A question
asked outside the gate, with the reply ending on it, drops the format rule 2 requires of every
reply, including a question handed back.

## 3. What authorizes work

**Nothing is created, edited, moved, or deleted until Sam picks a gate option naming exactly
what changes.**

A chat instruction is direction for the plan, never the go itself. Enthusiasm is not a go.
An answer to a question asked outside the gate is not a go either.

A question, comment, or concern anywhere in a message gates the whole reply: answer first,
build nothing. One gate option is always to continue where the work left off.

**Approval does not carry across messages.** A pick covers that item until it is done. The
next message is classified fresh.

## 4. When something disagrees

A doc against reality, a doc against another doc, or a number that will not reproduce.

1. **Stop.** Nothing builds on it.
2. Bring both sides, with file and line for each. Find why, not just what.
3. Decide which is right. Fix both sides in the same change, never one.
4. Then propose what would have prevented it. An error fixed without a prevention decision is
   half fixed.

## 5. Before writing

Check it first: the source reopened, the query run, the person named. Not remembered, not
carried forward from an earlier doc. What cannot be checked now is written as unchecked and
says what would settle it.

## 6. Where things go

Every project carries its own map in its `CLAUDE.md`. Shared homes:

| Kind of thing | Home |
|---|---|
| A rule true in every project | `_Playbook/PRINCIPLES.md` |
| How work runs everywhere | `_Playbook/WORKFLOW.md` |
| How this project works | `<project>/RULES.md` |
| Where we are, and the phase list | `<project>/STATUS.md` |
| Ordered work and open questions | `<project>/BACKLOG.md` |
| An original, unaltered | `<project>/sources/` |

`STATUS.md` is overwritten each session. `BACKLOG.md` accumulates until an item ships, then
the item is deleted rather than marked done.

## 7. The frozen files

`PRINCIPLES.md` and this file change only when Sam explicitly orders it, never as a side
effect of other work, and only after the exact new wording has been approved at a gate.

They exist once, at `_Playbook/`. No project holds a copy.
