# Decisions

Why the method is the way it is. One entry per subject, dated when
last settled. An entry names what it covers and gives the why; the
method files say the rest. When a decision changes, its entry is
rewritten, and git keeps what it said before. Overrules and declined
proposals are marked.

## Two learning loops and two gates — 2026-10-06

Why: shaping cannot find everything building will. Edge cases, rules
that interact, limits of the platform, sometimes a missing capability:
these often show up only once we work in code and tests. With one
gate, every rule found while building looked like a shaping failure,
or was waved through unnoticed. So building is a loop of its own, and
what it finds goes into the living files as normal work. The old gate
stays as strong as it was and becomes the release gate: for every
rule, its tests exist and pass. A lighter commit gate asks to know how
each known rule will be proved, not for the tests themselves, nor for
a prototype or UI, and marks the conscious choice to build. The gates
are named, not numbered, so each name says what is decided. A change
of intent is defined narrowly, as a material change to the problem,
the outcome or the scope of the commitment, not as any new capability.
Otherwise every capability building finds would go back to shaping,
and the rigidity of one gate would return. Product decides it, so the
loop cannot quietly turn into a new feature, and when it is unclear it
goes to Product, because "not material" judged alone is how intent
drifts. Keeping a prototype apart from real code until the gate was
dropped: the release gate is what protects the product, and where the
prototype goes is a question of how. Shaping still makes something a
real person can experience, as manifesto belief 2 asks; softening it
to whatever can teach us, with a person only where one can be reached,
was declined. The manifesto is unchanged: belief 1 already covers
learning by trying, and belief 7 is the split the release gate keeps.

## Product, QA and Engineering — 2026-10-06

Why: work with nobody accountable drifts. Three accountabilities are
held: Product for intent, Engineering for delivery, QA for proof. They
carry titles because titles are what people say, and each title is
defined by its accountability, not by a job, so a founder or a
designer can be Product and a team of one holds all three. Until this
date there were two, named only by accountability, for fear titles
would bring the wrong associations; the definitions answer that fear.

Proof and tests have different owners. The proof, how each rule is
shown to hold, is QA's to make sure of before the commit gate, where
finding the cases nobody thought of pays off most. The tests are
Engineering's. They are built with the implementation, by whoever
writes it, against the agreed proof, because knowing how a thing will
be tested changes how it is built; tests added afterwards work around
code that never planned for them, and turn flaky. Others, QA
included, may add or improve tests. QA makes sure of the proof, that
the tests do it, and that the feature has been tried by hand.
"Tests" replaced "executable proof", because nobody says the latter,
and the method defines the word broadly enough to keep evals and
assertions. In the manifesto, proof means a rule's proof together with
its tests.

A gate passes only when all three are satisfied, each for their own
part, and have said so. Before, Product decided both after hearing
delivery, which gave Engineering a voice but no hold; now Engineering
can refuse a commitment it cannot keep before others plan around its
date. Any of the three can hold a gate, none can force it: failing
tests are not released whoever is satisfied, which keeps the reason
the release gate was once "decided by nobody". All three at both
gates, rather than "each relevant accountability", because relevance
judged in the moment is how one gets skipped. The word is "satisfied",
not "signed": signing made the method read as a formal approval
process, and the invariant is the three accountabilities, not a
mechanism. "Have said so" stays, because an accountability nobody
voices is not held, and an agent cannot be satisfied on a person's
behalf. Gates are for features and changes to promises, so a fix that
restores a rule passes none. How the three say so in a repository, by
pull request approvals or otherwise, and which step makes a feature
Live, is the team's, in its `project.method.md`: a pull request cannot
be approved by its own author, and merging and releasing are often
apart.

A defect in use is triaged by where the gap was: capabilities or rules
to Product, proof to QA, the code or its tests to Engineering.
Behaviour that keeps every promise but disappoints a person is a
signal, not a defect, or every complaint would be routed as a bug.
Rules stay with Product, not QA, because a rule is a promise and
deciding what we promise is intent; QA reviews them. Capabilities
joined the rules in one row of the four things rather than becoming a
fifth, so the manifesto's bet still names them. The four things sit in
three layers, why, what and how, so the line between what we promise
and how we deliver it shows in the table. Code and tests are named
together, so it also shows where proof ends and tests begin. A
capability may be offered to another system, as the API tests already
assumed. The why is named Problem and outcome, in the words the gates
already use. Proof sits in the what: it is part of the feature file,
known at the commit gate before any code, and unchanged when the
implementation is replaced. Tests are its how, so the line between
proof and tests is the line between what and how. Beyond the tests
being written with the implementation, who writes is not in the
method. Each team knows its people better than a method can, and
naming who writes any part turns a role into a job. The method names
only who is accountable, and that AI works across all four. For the
same reason the table lost its "Led by" column, and "AI leads the
proof and the implementation" went with it.

## Tests prove a rule from outside — 2026-10-06

Why: manifesto belief 4 keeps the promises and lets the implementation
be replaced. A test of internals breaks when the implementation is
replaced while the promise still holds; it proves the code, not the
rule. So a rule's tests observe it at the boundary where its promise
is observed. The line is between behaviour boundary and
implementation detail, not between end-to-end and unit: for a
library, a parser or an engine, a unit-level test at its public
interface may be exactly the proof. "As close to end-to-end as
possible" was dropped because it made that a contradiction. A flaky
test is still a failing test, fixed by making the code testable at
its boundary, not by moving the test inside. A rule observed at an
API is tested there, not forced through a browser, which adds
flakiness and proves nothing more. That a rule's tests must be shown to
catch a break of the rule sits in the default, as how tests are
checked, not in the method. It is a principle, not a mechanism:
breaking the behaviour and watching the tests fail is used where
practical, and QA judges from reading where it is not, because for an
external system, a quality or an eval it is expensive or impossible.

## Timeboxes are commitments, not estimates — 2026-10-06

Why: a date treated as an estimate drifts, and nobody decides anything
when it passes. A timebox is worth something only if others can plan
around it. For shaping, that means a conscious commit-gate decision by
its date. For building, it means the agreed scope is released by its
date. They are called the commit date and the release date, so each
name says which gate it is for. Product holds the
commit date and decides any move of either date; Engineering
is accountable for meeting the release date.
When building threatens it, the approach and the scope are
reconsidered before the date, because a date that moves first stops
forcing those questions and becomes an estimate again. Moving a date
is the exception, and a date that moves often is no longer a
commitment. No count of moves is prescribed, because that would
pretend uncertainty goes away. A move is a conscious decision, made
before the commitment is missed, with its reason recorded. Sending a
feature back to Shaping withdraws its release date the same way, so it
is no way around a move. We take accountability seriously: people in
the team, across the organisation and sometimes customers rely on
these dates. Both dates are required, and a team of one that needs
neither writes its exception in `project.method.md`. They replace the
committed date. As with it, no tracker is kept, and what
lands when is a report AI gathers from the headers. Timeboxes sit in
the default, not the method, because the method would work without
them.

## Decision files are the contract on how — 2026-10-06

Why: once AI leads the how, a person still needs one place where the
questions they chose to settle are answered and kept, the way feature
files keep what the product promises. The method holds only that
settled choices about how are kept with the living files, at their
scope; the files and their shape sit in the default, because the
method would work with another shape. They live with the requirements
and not in the code, so the how a person settled is found where the
what is read, and survives the code being replaced. Each sits at the
narrowest scope it applies to, so a feature's reader finds its how
beside it without reading the whole product's. The scopes are read
together, and a narrower one may refine a broader one but never
silently contradict it, because two files saying different things
leave nobody sure what holds. A file is created only when there is a
decision worth keeping, so no empty files are left behind. No layout
is prescribed, because products are cut into modules differently.
Until 2026-10-05 where they sit was left open, for fear a fixed place
would leave empty files; scope without a fixed layout, and a file only
when needed, answers that fear.

## Decisions are current state, by subject — 2026-10-06

Why: dated entries pile up, and three records on one subject that say
different things leave nobody sure what holds. They are kept to
agreements, because the code is the how and is free to change; a
decision file that specs it drifts from it.

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
