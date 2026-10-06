# Decisions

Why the method is the way it is. One entry per subject, dated when
last settled. An entry names what it covers and gives the why; the
method files say the rest. When a decision changes, its entry is
rewritten, and git keeps what it said before. Overrules and declined
proposals are marked.

## Two learning loops and two gates — 2026-10-06

Why: shaping cannot find everything building will. Edge cases, rules
that interact, limits of the platform, sometimes a missing capability:
these only show up in code and proof. With one gate, every rule found
while building looked like a shaping failure, or was waved through
unnoticed. So building is a loop of its own, and what it finds goes
into the living files as normal work. The old gate stays as strong as
it was and becomes the release gate: for every rule, the executable
proof exists and passes. A lighter commit gate asks to know how each
known rule will be proved, not for the proof itself, nor for a
prototype or UI, and marks the conscious choice to build. Each loop
names the person accountable for it, intent for shaping and delivery
for building, by accountability rather than by title so any team can
fill them. It is in the method because a loop with nobody accountable
drifts, with or without timeboxes. A change of intent is decided by
the person accountable for intent, so the loop cannot quietly turn
into a new feature. It is defined narrowly, as a material change to
the problem, the outcome or the scope of the commitment, not as any
new capability. Otherwise every capability building finds would go
back to shaping, and the rigidity of one gate would return. When it is
unclear, it goes to that person, because "not material" judged alone
is how intent drifts. The gates are named, not numbered, so each name
says what is decided. Keeping a prototype apart from real code until
the gate was dropped: the release gate is what protects the product,
and where the prototype goes is a question of how. The manifesto is
unchanged: belief 1 already covers learning by trying, and belief 7 is
the split the release gate keeps.

## Timeboxes are commitments, not estimates — 2026-10-06

Why: a date treated as an estimate drifts, and nobody decides anything
when it passes. A timebox is worth something only if others can plan
around it. For shaping, that means a conscious commit-gate decision by
its date. For building, it means the agreed scope is released by its
date. Each of the two people the method holds accountable for a loop
holds that loop's timebox. When building threatens it, the approach
and the scope are reconsidered before the date, because a date that
moves first stops forcing those questions and becomes an estimate
again. No frequency of moves is prescribed: that would pretend
uncertainty goes away, and it is not what makes a date reliable. What
does is that it never moves silently. A move is a conscious decision,
made before the commitment is missed, with its reason recorded. We
take accountability seriously: people in the team, across the
organisation and sometimes customers rely on these dates. Timeboxes
replace the committed date. As with it, no tracker is kept, and what
lands when is a report AI gathers from the headers. Timeboxes sit in
the default, not the method, because the method would work without
them.

## Decision files are the contract on how — 2026-10-06

Why: once AI leads the how, a person still needs one place where the
questions they chose to settle are answered and kept, the way feature
files keep what the product promises. They live with the requirements
and not in the code, so the how a person settled is found where the
what is read, and survives the code being replaced. Each sits at the
narrowest scope it applies to, so a feature's reader finds its how
beside it without reading the whole product's. The scopes are read
together, and a narrower one may refine a broader one but never
silently contradict it, because two files saying different things
leave nobody sure what holds. A file is created only when there is a
decision worth keeping, so no empty files are left behind. No layout
is prescribed, because products are cut into modules differently.

## Decisions are current state, by subject — 2026-10-06

Why: dated entries pile up, and three records on one subject that say
different things leave nobody sure what holds. They are kept to
agreements, because the code is the how and is free to change; a
decision file that specs it drifts from it. The method holds only that
settled choices about how are kept with the living files, at their
scope. The files and their shape sit in the default, because the
method would work with another shape.

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
