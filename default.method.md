# Default Living Product Method

A complete default implementation of `method.md`.

Use it as-is, or replace parts of it in `project.method.md`. `method.md` wins where they disagree.

## Living files

Keep living files where everyone working on the features, people and agents, can reach all of them. They find each other and their proof by ID, so they can move without breaking anything.

In a product with one repository, a folder of their own is usually easiest. In a product whose code spans several repositories, a repository of their own may be.

There are three kinds:

- **Product file** — the product's vision, the problem, the people who have it, signals, exclusions and the feature map.
- **Feature file** — one per feature, containing its why, rules and references to proof.
- **Decision file** — records important choices about how and why they were made.

The product file is the root. Features may contain smaller features.

Living files describe current truth and are maintained for as long as that truth remains current.

Working material — customer conversations, evidence, requests, proposals, designs and other change documents — describes transitions and is not maintained as product truth.

## Feature files

Every feature file follows the same shape:

### Header

Status, owner, reviewers where needed, sources, conditions and committed date where one exists.

### Why

The problem, who has it, why now, what success looks like and what is outside the feature.

Do not repeat why inherited from a parent.

### What

Capabilities and their rules.

A capability describes something a person can do.

Rules describe observable behaviour or qualities worth preserving.

### Proof

For each rule, where and how it is proven.

Every executable proof references its rule.

### Signals

The product signals this feature is intended to move, where there are any.

### Depends on

Other features this feature requires.

### Open questions

Things not yet decided.

Use `@open` for a question and `@todo` with an owner for work that must be done.

### Change log

A compact, newest-first index of meaningful changes:

```md
## Change log

- 2026-09-22 — Added automatic trip briefing.
- 2026-09-14 — Removed manual refresh after order sync.
- 2026-08-30 — Initial feature went live.
```

Log changes in meaning, not formatting or wording that preserves meaning.

The feature file remains current truth. The log only points to how that truth changed.

## Features

Break the product into features until each can be experienced by a real person in one sitting.

Break along observable behaviour, not implementation.

Break late. Shape the parent before describing distant children in detail.

A smaller feature inherits its parent's why.

Rules sit on the smallest feature where their behaviour is observed. A parent has rules only for behaviour created by its parts working together.

Each feature may become Live independently. A parent is Live when its children and its own rules are Live.

## Capabilities and rules

Inside a feature, group related rules under capabilities.

A capability represents one user-facing operation or ability.

Give capabilities and rules stable IDs. Never reuse an ID for a different meaning.

Rules are acceptance criteria and should not be restated elsewhere.

Future possibilities stay as open questions until they are shaped. Do not write detailed rules for things nobody has tried yet.

## Status

A feature has four statuses:

- **Idea** — known, but nobody has started shaping it.
- **Shaping** — being discovered through prototypes and use.
- **Building** — its intended rules are known and it is moving through the gate.
- **Live** — it has passed the gate.

A feature without passing proof is not Live regardless of its recorded status.

## Shaping

Start the loop in `method.md` by writing enough why to start.

A prototype is not product truth. Keep it apart from real code until its feature passes the gate.

## Proof

Every rule names its proof.

Every executable proof references its rule ID.

A Live rule without proof fails the build.

Proof may include tests, assertions, evals or other executable checks.

For nondeterministic behaviour, use a fixed evaluation set and an explicit passing threshold.

How proof is implemented is a decision and may change without changing the rule.

## Signals

Keep product signals in the product file.

Each signal has:

- a measure
- a baseline
- a target
- a horizon

Say when a signal must be observed by a human rather than computed.

A feature references the product signals it is intended to move.

Review signals regularly. A signal that does not move is input to learning, not a build failure.

Measure the baseline before relying on later comparisons.

## Decisions

Record important choices about **how** separately from why and rules.

A decision records the choice and its reasoning.

Decisions may exist at product or feature level.

Replace a decision when a better one appears, while preserving enough reasoning for the next person or agent to understand why the choice was made.

## The gate

The gate is the one in `method.md`. A feature becomes Live when it passes.

For behaviour the fresh agent finds with no rule, either approve a rule for it or remove it.

Whether the prototype is cleaned up or rebuilt is an implementation decision.

The living files must remain understandable without reading the code.

## Feature changes

Once a feature is Live, meaningful changes to its promises get a feature change entry.

A change that touches no rule needs no entry: a fix that makes code meet an existing rule, a refactor, a change in wording.

A feature change records:

- status
- who asked and why now
- committed date where one exists
- rules added, changed or removed
- review findings and important reasoning

The feature remains Live while the change is underway.

When the change becomes Live, update the feature file, add a line to its change log, and move any reasoning worth keeping to the decision file. Then remove the change entry.

Several changes may be shaped independently. Conflicts are resolved when their resulting living-file changes meet.

## Living review

AI proposes changes to living files and checks the surrounding product truth for consequences.

Look for at least:

- contradictory rules
- unreachable rules
- duplicated promises
- implementation behaviour with no rule
- stale living information
- inconsistencies between the feature map and feature files

AI proposes fixes with its findings.

A human reviews the meaning and approves the change to product truth.

A living file that only grows is probably becoming history rather than current truth.

## Ownership and approval

Name a default owner for the repository. A living file may override that owner and specify additional reviewers.

Do not edit approved product truth merely because implementation would be easier another way. Propose the change and have a human decide.

Important implementation decisions are recorded with their reasoning.

## Tailoring and proposals

What a project or team does differently from this file goes in `project.method.md`, each difference with its why. How one person works goes in their `my.method.md`.

Both end with a `## Proposals` section. When a convention gets in the way or something is missing, AI adds a dated `@open` proposal to the file it belongs to. One that would be true for anyone is marked **Upstream**.

An approved proposal becomes part of its file. An approved Upstream proposal becomes a pull request to the method's repository. A declined one is removed. Either way its why goes in the project's decision file.
