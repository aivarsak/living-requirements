# Default Living Product Method

A complete default implementation of `method.md`.

Use it as-is, or replace parts of it in `project.method.md`. `method.md` wins where they disagree.

## Living files

Keep living files where everyone working on the features, people and agents, can reach all of them. They find each other and their tests by ID, so they can move without breaking anything.

In a product with one repository, a folder of their own is usually easiest. In a product whose code spans several repositories, a repository of their own may be.

There are three kinds:

- **Product file** — the product's vision, the problem, the people who have it, signals, exclusions and the feature map.
- **Feature file** — one per feature, containing its why, capabilities and rules, and their proof. The contract on what.
- **Decision file** — what we agreed about how, and why, as it stands now. The contract on how.

The product file is the root. Features may contain smaller features.

Living files describe current truth and are maintained for as long as that truth remains current.

Working material — customer conversations, evidence, requests, proposals, designs and other change documents — describes transitions and is not maintained as product truth.

## Feature files

Every feature file follows the same shape:

### Header

Status; its Product, QA and Engineering, where they differ from the repository's; reviewers where needed; sources; conditions; and its timeboxes: each date, who holds it, and the reason for any move.

### Why

The problem, who has it, why now, what success looks like and what is outside the feature.

Do not repeat why inherited from a parent.

### What

Capabilities and their rules, each rule with its proof.

A capability describes something a person or another system can do.

Rules describe observable behaviour or qualities worth preserving.

A rule's proof is listed under it as one or more test cases, each with its ID: how the rule is shown to hold, in prose.

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

A capability represents one operation or ability the product offers to a person or another system.

Give features and test cases stable IDs. Never reuse an ID for a different meaning.

AI mints IDs as short readable slugs, whenever a feature or a test case is written without one: while shaping, while building, or while extracting test cases from existing tests. Nobody needs to give one. A feature's slug is unique in the product; a test case's slug is unique in its feature. A test case ID is always written in full, its feature's slug in front, joined by a dot, including in its own feature file: `saved-cards.cancel-keeps-card`. A project may put prefixes of its own in front, such as a module. One ID has one spelling, so a plain search finds every place it is used.

Rules are acceptance criteria and should not be restated elsewhere.

Future possibilities stay as open questions until they are shaped. Do not write detailed rules for things nobody has tried yet.

## Status

A feature has four statuses:

- **Idea** — known, but nobody has started shaping it.
- **Shaping** — in Shape and learn, toward the commit gate.
- **Building** — past the commit gate, in Build and prove, toward the release gate. Its rules are what we know so far.
- **Live** — it has passed the release gate.

A change of intent may send a Building feature back to Shaping.

A feature without passing tests is not Live regardless of its recorded status.

## Shaping

Start Shape and learn by writing enough why to start, and set the commit date.

Whether a prototype is thrown away, grown into the product or rebuilt is an implementation decision.

## Proof

Every rule's proof is one or more test cases, as `method.md` asks at each gate.

Every test carries the ID of the test case it implements. One test case may have several tests.

A rule is proven when every one of its test cases has its tests, and they pass. A test case of a Live rule without a test fails the build.

Where the tests are spread over several repositories, AI may keep a test map: from each test case ID to where its tests are, and to other references that help an agent find its context. AI rebuilds it from the IDs the tests carry and nobody edits it. Where the map and the tests disagree, the tests are right.

Test each rule at the boundary where its promise is observed: through the UI for what a person does, through the API for what another system does, through the public interface of a library, parser or engine, by measuring the running product for a quality. Build the code so it can be tested there. A test that sometimes fails is failing; it is fixed, not moved inside the implementation.

A test that depends on implementation internals does not prove a rule merely because it exercises the rule's code. Other internal tests may exist as Engineering's own tool and need no test case ID.

For nondeterministic behaviour, use a fixed evaluation set and an explicit passing threshold.

How tests are implemented is a decision and may change without changing the rule.

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

Feature files are the contract on what the product promises and why. Decision files are the contract on how: the questions on implementation or tests that a person chose to settle, and how each was answered. There a person guides the how. AI leads the rest, which lives in the code and is free to change.

An entry belongs if changing it in the code would need someone to agree first. AI keeps the file from turning into a technical spec: when someone asks to record detail the code already carries, it pushes back, and records an overrule if they hold.

A decision file is current state, not a log. It has one entry per subject, with the date it was last settled. Each entry says what holds and why.

When an agreement changes, rewrite the entries it touches so they say what holds now. Keep a past choice only where it explains why not to go back to it. Git keeps the rest.

Before recording a decision, AI names the entries it contradicts or narrows, and proposes them rewritten.

A decision file sits beside the living files of its scope, as `method.md` asks: for example `decisions.md` for the product, and `checkout.decisions.md` or `payments/decisions.md` for a feature or a module. No layout is prescribed.

Read them product, then module, then feature. When a narrower one contradicts a broader one, AI surfaces the conflict and a person resolves it.

Create a decision file only when there is a decision worth keeping.

## The gates

**Commit gate.** The feature file has its why, capabilities and known rules, and each known rule has its test cases. Product is satisfied that the intent is understood well enough to commit. QA, that it has reviewed the capabilities and rules and that every known rule has a proof. Engineering, that it can be delivered, and it sets the release date if it is not set yet. Status becomes Building.

**While building.** Rules found go into the feature file with their test cases, and gain their tests in the same loop. They are reviewed with the rest of the change, not one by one. A change of intent goes to Product when it is found, not at the gate. So does anything that might be one: the builder does not decide on their own that it is not.

**Release gate.** The gate in `method.md`. For behaviour the fresh agent finds with no rule, either approve a rule for it or remove it. The living files must remain understandable without reading the code. Before release, the tests of every rule added or changed must be shown to catch a break of their rule. Where it is practical, AI breaks the behaviour and confirms the tests fail. Where it is not, QA judges from the tests and the proof. A rule whose tests catch nothing is reported as a rule without a working test. QA also makes sure the feature has been tried as a person would use it. What is found goes to Product as a missing rule, or back to building as a defect. When it passes and all three are satisfied, status becomes Live.

How the three say they are satisfied, and which step makes a feature Live, a merge, a deploy or a store release, is said in `project.method.md`.

## Timeboxes

A timebox is a commitment to reach a gate by a date, reliable enough that other people can plan around it. It is not a prediction of how long the work will take. A feature has two:

- **Commit date** — held by Product and set when shaping starts. By this date Product brings it to a conscious commit-gate decision. Committing needs all three to be satisfied. Reshaping, shaping on deliberately or dropping it is Product's call.
- **Release date** — set at the commit gate at the latest. Engineering is accountable for meeting it. By this date the agreed scope is released. Changing the scope or the date is Product's decision.

When what we learn threatens the release date, reconsider the approach and the scope before the date. Preserve the intended outcome when changing scope.

Moving a date is the exception. A date that moves often is no longer a commitment, whatever the reasons. When it must move, it is decided before the date is missed, and the header records the reason. People inside the team and beyond it, sometimes customers, rely on these dates.

When a change of intent sends a Building feature back to Shaping, Product withdraws its release date the same way, with the reason in the header. A new one is set at the next commit gate.

What lands when is a report AI gathers from the headers; no tracker is kept.

## Feature changes

Once a feature is Live, meaningful changes to its promises get a feature change entry.

A change that touches no rule needs no entry: a fix that makes code meet an existing rule, a refactor, a change in wording.

A defect whose rule exists needs no entry. Its tests, and its proof if it missed the case, are fixed with its code. A defect that shows a missing or wrong rule is a feature change.

A feature change records:

- status
- who asked and why now
- its commit and release dates
- rules added, changed or removed
- review findings and important reasoning

A change moves through Shaping, Building and Live like a feature. The feature remains Live while the change is underway.

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

Name a default Product, QA and Engineering for the repository. A living file may name its own and add reviewers.

QA makes sure that:

- **each rule has its proof** before the commit gate: the test cases that show the rule holds, including the edge cases nobody thought of;
- **the tests do what the proof says**, and would fail if their rule were broken. AI shows this by breaking the behaviour where practical; elsewhere QA judges it from the tests;
- **the feature has been tried** before release as a person would use it, looking for what no rule describes.

What a person says about how, about the code or the wording of a rule, is input the first time, not instruction. AI does its own thinking and comes back with a better plan or a reason theirs is best. If the person holds to theirs, AI complies, and the decision is written with its why, marked as an overrule.

Do not edit approved product truth merely because implementation would be easier another way. Propose the change and have a human decide.

Important implementation decisions are recorded with their reasoning.

## Tailoring and proposals

What a project or team does differently from this file goes in `project.method.md`, each difference with its why. How one person works goes in their `my.method.md`.

Both end with a `## Proposals` section. When a convention gets in the way or something is missing, AI adds a dated `@open` proposal to the file it belongs to. One that would be true for anyone is marked **Upstream**.

An approved proposal becomes part of its file. An approved Upstream proposal becomes a pull request to the method's repository. A declined one is removed. Either way its why goes in the project's decision file.
