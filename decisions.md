# Decisions

How the method was chosen, each with its why. A decision is easy to
change: replace it, keep the reasoning, have a human agree. An overrule
is marked as such. Only decisions that still hold are here; git keeps
the rest.

Some were made in Stay Close (`aivarsak/stay-close-oss`) and moved
here on 2026-09-22 with the method. Decisions about a product stay in
that product.

## 2026-09-24 — IDs are slugs, prefixed by their feature

From a project, owner's proposal, simplified with AI. This brings back
the slug IDs that went with `layout.md`. Why: an ID read anywhere, in a
test name or a commit, says what it means. Two people shaping different
features never collide, because feature slugs are unique in the
product. Numbers do neither. By default the prefix is the feature
alone. The feature map already says where a feature sits, and a path
would rename rules whenever features are split or moved. A team that
wants a module or a path in front adds it in its project method.

## 2026-09-23 — How is input the first time

From a project, owner's proposal. Why: an agent that takes the first
word on how as instruction stops thinking where it is strongest, in
implementation and in wording rules. Asking once for its own plan
costs little; complying when the person holds keeps them in charge.
The overrule is written so the next reader knows it was a choice.

## 2026-09-23 — Living files go anywhere everyone can reach

Owner's decision, replacing "Living files sit apart from the code". The
method no longer says where living files are kept. Why: we kept them
apart because code changes places. Moving them is harmless as long as
everyone working on the features can reach all of them and they refer
to each other and to proof by ID. Removing one removes its feature. An
accidental removal shows up as drift, because the proof left behind
carries rule IDs that have no rule. A folder of their own, or a
repository of their own for a multi-repository product, is a
suggestion, not a rule. This repository, the method apart from every
project, is one such choice.

## 2026-09-23 — A change entry is removed when its change goes Live

Owner's question, AI's proposal. This replaces "The feature file
carries its change log", whose log pointed into `changes/`. The feature
file still ends with a change log, but each line stands alone: the date
and what changed in meaning. Why: while a change is underway, its entry
holds what cannot yet go in the feature file. Once it is Live, the
entry is only history, which living files are not. Keeping it meant a
path that breaks when files move and a listing the log repeated.
Reasoning worth keeping goes to the decision file, and git keeps the
rest.

## 2026-09-23 — The method is five layers

Owner's idea. Manifesto, method, default method, project method,
personal method. Each layer only chooses or adds, and never restates
the one above. A lower layer may replace a choice made by the default,
with its why, but never contradicts `method.md`. Why: when a lower
layer repeats a higher one, the copies drift apart and it stops being
one method. So `default.method.md` lost what it repeated from
`method.md`: the loop, the gate, who owns what.

## 2026-09-23 — layout.md is gone; default.method.md is the only default

Owner's decision. Why: where files sit and how work moves through git
are choices of one way to do it, not a layer of their own. The
decisions about branches, task files, slug ids and file names went
with it.

## 2026-09-23 — The repository holds only what anyone needs to start

Owner's idea; the first customer is the owner, on greenfield projects
in the Living Requirements app. Manifesto, method, default method,
`adopt.md`, README, CLAUDE.md, this file and the license. The example
personal method, the agent file for projects and the logos went. Why:
a stranger should be able to start from here alone.

## 2026-09-23 — A project adopts the method by copying it

AI's proposal, owner agreed. This reverses "a project keeps no copy":
before, projects imported the method from a path on the owner's
machine. `adopt.md` copies the manifesto, the method and the default
into `living-requirements/` in the project, records the commit, and
adds a block to `CLAUDE.md` or `AGENTS.md`. Why: a copy can be read on
GitHub, by any agent and by a teammate who just cloned the project, as
manifesto 8 asks. A path worked only for the owner and only in Claude
Code. A copy is pinned, so taking a new version is a reviewed change
with its conflicts named. Nothing edits the copies, so they lag but do
not drift. A submodule gives the same with more friction.

`adopt.md` and not an example `CLAUDE.md`: what one gives an agent is
an instruction, not a template. The block sits inside it.

## 2026-09-23 — People edit two files: the project's and their own

Owner's idea. `project.method.md` in the project, shared through git.
`my.method.md` with the person, in Claude Code `~/.claude/my.method.md`
imported from `~/.claude/CLAUDE.md`. Why: the personal method follows
the person across projects, and set up once it works in every project,
in the app or outside it. Where the two disagree the project wins,
because the team shares it.

## 2026-09-23 — Proposals to the method collect in those two files

Owner's idea. Each ends with a `## Proposals` section of dated `@open`
lines. One that would be true for anyone is marked Upstream and, once
approved, becomes a pull request here. Why: no inbox to build or keep;
the proposals are text in files already read and remarked on. The why
of each decision goes to the project's decision file, so the section
never grows into a history.

## 2026-09-23 — A change that touches no rule needs no feature change entry

Owner's decision, from the first example proposal. A fix that makes
code meet an existing rule, a refactor, a change in wording. Why: an
entry records how promises changed; where none did, it is ceremony.

## 2026-09-23 — CC BY 4.0

Owner's decision. Why: the repository is prose, and CC BY is the usual
license for it. Anyone may use, copy and adapt the method, commercially
too, with credit. MIT is for software; CC0 gives up the credit.

## 2026-09-19 — The product file is the umbrella, not a feature file

Owner's decision, AI agreed. Why: the root has no rules and no proof of
its own. Forcing the feature-file shape on it produced an empty
"Depends on", an Id of "the root" and a Proof with nothing to prove.
The root's job is vision and alignment, so it has its own shape. It is
the one exception to every feature file having the same shape in
`default.method.md`.

## 2026-09-19 — A committed date lives in the header

Owner's idea. Optional; a promise, never an estimate. Why: with status
and dates in the living files, what is cooking and when it lands is a
report AI gathers on request, and no tracker is kept beside the work.

## 2026-09-22 — The method's home keeps no log

Owner's decision. Nothing is built here, only the method, so this file
is the one record: each decision with its why, overrules and declined
proposals included, one line for the declined.
