# Decisions

How the method and the layout were chosen, each with its why. A
decision is easy to change: replace it, keep the reasoning, have a
human agree. An overrule is marked as such.

These were made in Stay Close (`aivarsak/stay-close-oss`) and moved
here on 2026-09-22 with the method. Decisions about a product stay in
that product.

## 2026-09-19 — The product file is the umbrella, not a feature file

Owner's decision, AI agreed. Why: the root has no rules and no proof of
its own. Forcing the feature-file shape on it produced an empty
"Depends on", an Id of "the root" and a Proof that contradicted
manifesto rule 1. The root's job is vision and alignment, so it has its
own shape. This is the one exception to manifesto rule 9, every
feature file has the same shape, and it is recorded here on purpose.

## 2026-09-19 — File names carry the slug

Owner's decision. `features/<slug>/<slug>.feature.md` and
`features/<slug>/<slug>.decisions.md`. Why, as AI understood it and
the owner is to confirm: the file says what it is when opened alone,
in a tab or a search result, and a feature's files sort together. AI
had proposed `feature.md`; overruled.

## 2026-09-19 — Work branches from the branch it belongs to

Owner's idea; AI had proposed cutting every piece of work from main
and came round. A branch is one piece of work: a new feature, a
feature change, or a task inside either. A feature or a feature change
branches from main; a task from what it is part of, and merges back
there; one worktree per open branch; names are flat, joined by dots.
Why: nothing red may be on main, so tasks need a place to come
together before their proof is green, and the feature's branch is that
place. A task is not a feature, because features are broken along what
a person observes and work is not. When a task does follow one
capability or one rule, it takes that id as its name. Dots because git
cannot hold a branch and a branch under it by the same name.

The repository is the tracker: every branch is described by one file,
a task by its file in `tasks/`, brief, typed only when a bug or a
chore, and without status; work shelved on purpose says so in the file
and in its branch name. AI writes and pushes the task file when it
creates the branch. Owner's idea; AI had proposed an empty commit and
came round, because a file can be seen, commented on and corrected in
the editor. At the merge what is worth keeping is proposed where it
belongs and reviewed by the owner; then the task file is removed and
its text goes into the merge commit: a task is how, how is free to
change, and the sequence stays readable from git. A branch is deleted
once merged for good, so open or done is whether it still exists;
alive or stalled is when it was last touched. No accounting.

## 2026-09-19 — A committed date lives in the header

Owner's idea. Optional; a promise, never an estimate. Why: with
status, branches and dates in the repository, what is cooking and when
it lands is a report AI gathers on request, and no tracker is kept
beside the work.

## 2026-09-19 — Ids are slugs, and a branch is named by the id it works on

Owner's proposal, both halves. AI had proposed numbered ids, `C1.1`,
and branch names that could not be mistaken for ids, and came round.
An id is `<feature path>.<capability>.<rule>`, each part a slug,
minted once in the feature file. Why: a slug reads anywhere, in a test
name, a task file or a merge request, without the file open; two
people never mint the same next number; and folders, files and
branches are slugs joined by dots already. What numbers gave was
surviving a rename, so an id does not follow its heading. A rule that
changes so much that its slug lies is a new rule, and the old one goes
with its proof. AI's three adjustments, accepted: the last part names
the rule, not the proof, because one rule may have several tests; the
front is the feature's path, with no new word for a parent; a
capability does not take the slug of a smaller feature beside it.

A branch takes the id of what it works on. Why: the name says what the
work answers to, nobody invents a slug for a task, and searching an id
finds its rule, its tests and the work done on it. A second branch
open on the same id takes the date it was opened at the end; a date,
not an index, because an index needs someone to know the last one.
Work that answers to no single capability or rule keeps the date and a
slug.

## 2026-09-22 — Living files sit apart from the code

Owner's decision, closing the question AI had left open in Work
Sessions. Living files, change entries and task files live under
`features/`; code, proof and prototypes live outside it. Why: one
product's code is often in several repositories, the owner may not
know how or by whom a thing is built, and where the requirements live
must not move when the code moves. What ties a rule to its code is the
id every test carries and the place each rule names as its proof; a
rule's change and its code's change still travel on one branch. This
repository, the method apart from every project, is the same decision
one level up.

## 2026-09-22 — The method's home keeps no log

Owner's decision. Nothing is built here, only the method, so this
file is the one record: each decision with its why, overrules and
declined proposals included, one line for the declined. Projects that
work by the method keep their own `log.md`, where the owner's
interventions on how are the experiment's record.

## 2026-09-22 — The feature file carries its change log

Owner's idea. A section at the end of the feature file: date, one
line, the entry's file in `changes/`, newest first, changes in meaning
only. Why: the file reads alone, the same why as file names carrying
the slug. What we give up: `changes/` is already a dated listing, so
the log is that listing said again, and the review checks the two
agree.
