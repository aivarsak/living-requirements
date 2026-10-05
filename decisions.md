# Decisions

Why the method is the way it is. One entry per subject, dated when
last settled. An entry names what it covers and gives the why; the
method files say the rest. When a decision changes, its entry is
rewritten, and git keeps what it said before. Overrules and declined
proposals are marked.

## Decision files are the contract on how — 2026-10-05

Why: once AI leads the how, a person still needs one place where the
questions they chose to settle are answered, and kept, the way feature
files keep what the product promises. Where decision files sit is left
open on purpose: we do not yet know a placement that fits every
product, and a fixed one would leave empty files behind.

## Decisions are current state, by subject — 2026-09-29

Why: dated entries pile up, and three records on one subject that say
different things leave nobody sure what holds. Kept to agreements,
because the code is the how and is free to change; a decision file
that specs it drifts from it. It sits in the default, not the method,
because the method would work without it.

## Five layers — 2026-09-23

Why: when a lower layer repeats a higher one, the copies drift apart
and it stops being one method. Where files sit and how work moves
through git are choices within the default, not a layer of their own.

## What this repository holds — 2026-09-23

Why: a stranger should be able to start from here alone, so it holds
only what anyone needs to start. Nothing is built here, so it keeps no
log; this file is the one record.

## Adopting by copying — 2026-09-23

Why: a copy can be read on GitHub, by any agent and by a teammate who
just cloned the project, as manifesto 8 asks. A path on one machine
works only for its owner and one tool. A copy is pinned, so a new
version is a reviewed change with its conflicts named, and since
nothing edits the copies they lag but do not drift. A submodule gives
the same with more friction. `adopt.md` is an instruction and not an
example `CLAUDE.md`, because what one gives an agent is an
instruction, not a template.

## Two files people edit, and proposals in them — 2026-09-23

Why: the personal method follows the person across projects, in any
tool. The project wins over the person because the team shares it.
Proposals are text in files already read and remarked on, so there is
no inbox to build. Their why comes here, so the Proposals section
never grows into a history.

## Where living files go — 2026-09-23

Why: moving them is harmless while everyone can reach all of them and
they refer to each other and to proof by ID. An accidental removal
shows up as drift, because the proof left behind carries rule IDs
that have no rule. So a folder or repository of their own is a
suggestion, not a rule.

## The product file's own shape — 2026-09-19

Why: the root has no rules and no proof of its own. The feature-file
shape forced on it produced an empty "Depends on", an Id of "the root"
and a Proof with nothing to prove. Its job is vision and alignment.
A committed date in the header is a promise, never an estimate, so
what lands when is a report AI gathers and no tracker is kept.

## Slug IDs, prefixed by their feature — 2026-09-24

Why: an ID read anywhere, in a test name or a commit, says what it
means, and unique feature slugs keep independent features from
colliding. Numbers do neither. A path in the prefix would rename rules
whenever features are split or moved.

## Change entries and the change log — 2026-09-23

Why: once a change is Live its entry is only history, which living
files are not, so it goes and its reasoning comes to the decision
file. A change that touches no rule needs no entry: it records how
promises changed, and where none did it is ceremony.

## How is input the first time — 2026-09-23

Why: an agent that takes the first word on how as instruction stops
thinking where it is strongest, in implementation and in wording
rules. Asking once for its own plan costs little; complying when the
person holds keeps them in charge. The overrule is written so the next
reader knows it was a choice.

## CC BY 4.0 — 2026-09-23

Why: the repository is prose, and CC BY is the usual license for it.
MIT is for software; CC0 gives up the credit.
