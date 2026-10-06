# Default Living Product Method

A complete default implementation of `method.md`.

Use it as-is, or replace parts of it in `project.method.md`. `method.md` wins where they disagree.

## Living files

Keep living files where everyone working on the features, people and agents, can reach all of them. They find each other and their proof by ID, so they can move without breaking anything.

In a product with one repository, a folder of their own is usually easiest. In a product whose code spans several repositories, a repository of their own may be.

There are three kinds:

- **Product file** — the product's vision, the problem, the people who have it, signals, exclusions and the feature map.
- **Feature file** — one per feature, containing its why, rules and references to proof. The contract on what.
- **Decision file** — what we agreed about how, and why, as it stands now. The contract on how.

The product file is the root. Features may contain smaller features.

Living files describe current truth and are maintained for as long as that truth remains current.

Working material — customer conversations, evidence, requests, proposals, designs and other change documents — describes transitions and is not maintained as product truth.

## Feature files

Every feature file follows the same shape:

### Header

Status, owner, reviewers where needed, sources, conditions, and the current timebox: its date and who holds it.

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

AI mints IDs as short readable slugs. A feature's slug is unique in the product. Outside its feature file, a capability or rule carries its feature's slug in front, joined by a dot: `saved-cards.remove-card.asks-to-confirm`. A project may put prefixes of its own in front, such as a module. Every proof carries the full form.

Rules are acceptance criteria and should not be restated elsewhere.

Future possibilities stay as open questions until they are shaped. Do not write detailed rules for things nobody has tried yet.

## Status

A feature has four statuses:

- **Idea** — known, but nobody has started shaping it.
- **Shaping** — in Shape and learn, toward the commit gate.
- **Building** — past the commit gate, in Build and prove, toward the release gate. Its rules are what we know so far.
- **Live** — it has passed the release gate.

A change of intent may send a Building feature back to Shaping.

A feature without passing proof is not Live regardless of its recorded status.

## Shaping

Start Shape and learn by writing enough why to start, and set the shaping timebox.

A prototype is a tool for learning, not product truth. Whether it is thrown away, grown into the product or rebuilt is an implementation decision. Until the release gate, it promises nothing.

## Proof

Every rule names how it is proved.

At the commit gate, that may be only how we will prove it. At the release gate, the executable proof exists and passes.

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

Feature files are the contract on what the product promises and why. Decision files are the contract on how: the questions on implementation or proof that a person chose to settle, and how each was answered. There a person guides the how. AI leads the rest, which lives in the code and is free to change.

An entry belongs if changing it in the code would need someone to agree first. AI keeps the file from turning into a technical spec: when someone asks to record detail the code already carries, it pushes back, and records an overrule if they hold.

A decision file is current state, not a log. It has one entry per subject, with the date it was last settled. Each entry says what holds and why.

When an agreement changes, rewrite the entries it touches so they say what holds now. Keep a past choice only where it explains why not to go back to it. Git keeps the rest.

Before recording a decision, AI names the entries it contradicts or narrows, and proposes them rewritten.

Decisions live with the requirements, not scattered through the code, at the narrowest scope that applies: the product, a module, or a feature. For example, `decisions.md` and `checkout.decisions.md`, or `payments/decisions.md`. The method prescribes no layout.

They are read together, product, then module, then feature. A narrower decision may refine a broader one, never silently contradict it. When one does, AI surfaces the conflict and a person resolves it.

Create a decision file only when there is a decision worth keeping.

## The gates

**Commit gate.** The feature's owner, as the person accountable for its intent, decides it with the person accountable for delivery, who sets the release timebox then if it is not set yet. The feature file has its why, capabilities and known rules, and its Proof says how each will be proved. Status becomes Building.

**While building.** Rules found go into the feature file with how they will be proved, and gain their proof in the same loop. They are reviewed with the rest of the change, not one by one. A change of intent goes to the owner when it is found, not at the gate. So does anything that might be one: the builder does not decide on their own that it is not.

**Release gate.** The gate in `method.md`. For behaviour the fresh agent finds with no rule, either approve a rule for it or remove it. The living files must remain understandable without reading the code. Status becomes Live.

## Timeboxes

A timebox is a commitment to reach a boundary by a date, reliable enough that other people can plan around it. It is not a prediction of how long the work will take.

- **Shaping timebox** — held by the person accountable for product intent, the feature's owner, and set when shaping starts. By its date, a conscious commit-gate decision is made: commit, reshape, keep shaping deliberately, or drop it.
- **Release timebox** — held by the person accountable for delivery, and set at the commit gate at the latest. By its date, the agreed scope is released. A change of scope is decided with the owner of the intent.

When what we learn threatens the release timebox, first change the approach, then reduce the scope while keeping the intended outcome. Only then move the date.

A timebox may change, but never silently. Moving it is a conscious decision, made before the commitment is missed, and the header records the reason. People inside the team and beyond it, sometimes customers, rely on these dates. They trust them because the dates are kept, or renegotiated openly and in time.

What lands when is a report AI gathers from the headers; no tracker is kept.

## Feature changes

Once a feature is Live, meaningful changes to its promises get a feature change entry.

A change that touches no rule needs no entry: a fix that makes code meet an existing rule, a refactor, a change in wording.

A feature change records:

- status
- who asked and why now
- its timeboxes
- rules added, changed or removed
- review findings and important reasoning

The feature remains Live while the change is underway.

When the change becomes Live, update the feature file, add a line to its change log, and move any reasoning worth keeping to the decision file at its scope. Then remove the change entry.

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
- decisions that contradict each other, overlap, no longer match the code, or have become spec

AI proposes fixes with its findings.

A human reviews the meaning and approves the change to product truth.

A living file that only grows is probably becoming history rather than current truth.

## Ownership and approval

Name a default owner for the repository. A living file may override that owner and specify additional reviewers.

What a person says about how, about the code or the wording of a rule, is input the first time, not instruction. AI does its own thinking and comes back with a better plan or a reason theirs is best. If the person holds to theirs, AI complies, and the decision is written with its why, marked as an overrule.

Do not edit approved product truth merely because implementation would be easier another way. Propose the change and have a human decide.

Important implementation decisions are recorded with their reasoning.

## Tailoring and proposals

What a project or team does differently from this file goes in `project.method.md`, each difference with its why. How one person works goes in their `my.method.md`.

Both end with a `## Proposals` section. When a convention gets in the way or something is missing, AI adds a dated `@open` proposal to the file it belongs to. One that would be true for anyone is marked **Upstream**.

An approved proposal becomes part of its file. An approved Upstream proposal becomes a pull request to the method's repository. A declined one is removed. Either way its why goes in the project's decision file.
