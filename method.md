# The Living Product Method

How we work with Living Requirements. The manifesto says what we believe.

## The problem

Teams with agents write code faster than they can say what it should do, or check that it still does it.

What the product should do lives in many places: heads, tickets, tests, code. No single one is readable by both people and agents, and none is run against the product to prove it is true.

So every change is a risk, humans reviewing code become the bottleneck, and the code cannot be replaced because only the code says what the product does.

Earlier fixes — specs, BDD, documentation — failed because a person had to keep the description and the code in sync, and the description always lost.

## Three artifacts

| Artifact | Says | Truth for | Leads |
| --- | --- | --- | --- |
| Why | why | context | human |
| Rules and proof | what | what should be | AI |
| Code | how | what is | AI |

Green means the rules and the code agree.

Red means one of them is wrong. Fix the wrong one.

## Living files

What people and AI agree on is kept in the repo as state, in a folder of its own, apart from the code and the proof.

There are three kinds:

- **The product file** is the umbrella. It holds the problem, the people, the future we want, how we will know, what we are not building, and the map of features. It has no rules and no proof of its own, so it has its own shape.
- **A feature file** per feature holds the feature's why, capabilities, rules and proof.
- **A decision file** wherever how had to be chosen: one beside the product for product-wide decisions, and one beside a feature for decisions of its own.

Together these are the **living files**.

Living files describe current truth. They have no end.

Everything else about a feature — evidence, what was asked for and refused, questions from sales, customer conversations, design files — belongs to a change. It stays in the documents that produced it. Those documents are named by the living files they fed and are not maintained.

Change documents describe transitions. Living files describe state.

## The feature file

Every feature has one feature file.

Every feature file has the same shape:

- **Header.** Status, owner, reviewers where they are not the owner and how many must approve, sources, the conditions its rules assume where they narrow the product's, and the date someone has committed to once there is one. A rule inherits the feature's conditions unless it names its own.
- **Why.** The problem, whose pain, why now, what success looks like, and what we are not building. It does not repeat the why above it.
- **What.** Capabilities, each with its rules.
- **Proof.** Each rule, where it is proven, and the test that proves it.
- **Signals.** The product's signals this feature moves, by name. Only when it moves one.
- **Depends on.** The features this one needs.
- **Open questions.** What is not decided, kept until it is. A question sits where it arises, marked `@open`; something someone has to do is marked `@todo` and names who. This section holds only what belongs to no single place.
- **Change log.** A compact history of meaningful changes to the feature, described below.

### Change log

The last section of the feature file is a compact history of meaningful changes to it.

Each entry has:

- the date
- a one-line description of what changed
- the feature change entry's file in `changes/`, where one exists

Newest first.

The initial release is the first entry. Later entries correspond to feature changes.

The change log records changes in meaning, not edits in wording. Formatting, spelling and wording changes that preserve meaning are not logged.

The feature file remains the current truth. The change log is only an index of how that truth changed; the reasoning belongs in the feature change entry.

Example:

```md
## Change log

- 2026-09-22 — Added automatic trip briefing. `changes/2026-09-20-trip-briefing.md`
- 2026-09-14 — Removed manual refresh after order sync. `changes/2026-09-10-order-sync-refresh.md`
- 2026-08-30 — Initial feature went live.
```

## Status

A feature has one of four statuses.

**Idea** — named in the map above it, one line. It gets a feature file in the same shape as any feature as soon as there is more to capture than that line, so nothing about it lives outside the repo. The status says only that nobody has started on it.

**Shaping** — someone has started. The loop below is defining and prototyping it.

**Building** — it is at the gate.

**Live** — it has passed the gate once. The loop keeps running on it through feature changes.

A feature with no green proof is not live, whatever its header says.

## Feature changes

A feature's initial version is not a feature change.

Its own status carries it from Idea to Live, its feature file holds the why, and the review's findings travel with the proposal.

A **feature change** is work on a live feature. It adds, alters or removes rules.

Each feature change has an entry in the feature's `changes/` folder containing:

- status
- who asked and why now
- the date someone has committed to, once there is one
- the rules it adds, changes or removes
- the review's findings

It is about a change, not a state, so it is not a living file.

It needs no approval to edit. It closes when the feature change is live and is not touched again. It is right that it then goes out of date.

A feature change has the same four statuses as a feature, and the feature stays Live throughout.

Several feature changes may be open on one feature at once, one branch each. Where they touch the same lines of the feature file they conflict, and resolving that by hand is the coordination.

Two open feature changes that mint the same rule id settle it at merge, the same way.

## Features, capabilities and rules

A product is one feature, too big to hold.

Break it into features, and those into smaller ones, until a real person can try each in one sitting.

A feature inside a feature is still a feature. The same rules apply at every size. Only the root is different: it is the umbrella and keeps the product file's shape.

Inside a feature are **capabilities**: one operation each — adding, finding, editing, closing.

A capability is the user story, written as one: the person, what they want, and what they do today without it.

Under it are its **rules**, each with an id, each testable. The rules are the acceptance criteria, and nothing restates them elsewhere.

A capability meant for a later version is one line under Open questions, with no rules. Rules come from holding the thing.

Ids are minted in the feature file and never reused.

A rule's id is unique inside its capability and a capability's inside its feature, so an id read anywhere says which feature, capability and rule it means, and two people shaping different features never collide.

A feature's why names its smaller features, one line each, as the product file names its features. Nothing else keeps that list.

A smaller feature does not repeat the why above it; it inherits it.

### Breaking

Break when a person could not try it in one go, or when the why needs more than one why.

Break along what a person can observe, never along how it is built.

"A rep gets a brief for the trip" is a feature.

"Read orders from the ERP" is not; no rep can hold it. It lives inside features and is proven only through them.

Break late.

Name smaller features in one line each; describe in full only the ones being shaped now. One described in detail before you have held its parent is a guess written down as a plan.

Breaking is a product decision, recorded in the parent's why.

### Shaping in parallel

Smaller features are shaped independently, several at once if there are hands.

Each runs its own loop. They share only the whys above them.

Trying one teaches you about the parent: it may vanish, merge with a neighbour, or break again.

The split is clay too.

### Where rules sit

Rules sit on the smallest feature where a person observes the behaviour.

A parent carries rules only for what shows when its smaller features work together, never a rule that belongs to one of them.

### Shipping

Each feature passes the gate alone, against its own why, the whys above it, and its rules.

It is Live when green. It does not wait for its siblings or its parent.

A feature is Live when everything inside it is Live and its own rules, if any, are green.

A prototype may go in front of real customers on its own. That is Try.

It is not the product until its gate.

## Shaping

A feature starts as clay. Nobody knows the final shape.

You find it by holding it.

1. **Define.** A rough why: the problem, for whom. One paragraph is enough to start.
2. **Prototype.** AI builds a rough version. No rules. Not product code yet.
3. **Try.** A real person uses it. This is where the learning is.
4. **Learn.** Rewrite the why. What you saw and want to keep becomes a rule. One angle sharpened.
5. Back to Prototype until it looks like what you want.

At any step you may find the feature too big to hold.

Stop, name the smaller ones, and shape those instead. Breaking is not a step of the loop; it can interrupt any of them.

Rules come last in shaping, not first.

A rule written before you have held the thing is a guess frozen as a requirement.

A rule written after records something you know.

The number of rules is how shaped the feature is.

## Proof

A rule names where it is proven.

Every test carries its rule id.

A live rule with no test fails the build. How that is checked is a decision.

Behaviour that is not deterministic is scored against a threshold on a fixed set of cases.

A drop below the threshold fails the build the way a failing test does.

What the product does below the threshold is a rule on that feature, not a sentence here.

Other kinds of proof that need saying out loud stay under Later until a feature needs one.

## Signals

Proof asks whether the code does what the rules say.

A signal asks whether the product is doing what the why hoped.

| Check | Read from | When | On failure |
| --- | --- | --- | --- |
| Proof | tests | every change | red; nothing red on main |
| Signal | the product's data | weekly | never blocks; steers the why |

A signal is a sentence a person reads, with:

- a measure the intelligence computes from data the product already holds
- a baseline
- a target
- a horizon

Some signals are observed by a human rather than computed; the file says which.

The product file holds the signals, ranked. A feature names the ones it moves.

Signals are read weekly and shown where the people who own the why already look.

A signal that does not move is the strongest input to Learn: rewrite the why, or drop the feature.

The baseline is measured before the first feature goes live. Without it there is nothing to compare against later.

## Decisions

Some choices are neither why nor what: a stack, a hosting service, a security trade-off.

They go in a decision file with their why: one beside the product, and one beside a feature with how of its own.

Decision files are separate from feature files on purpose.

A decision is how, and how can change without the why moving.

A stranger reads the decision and the reason before touching the code.

How a decision is reached is under Who does what.

A decision is easy to change. Replace it whenever a better one turns up, keep the reasoning, and have a human agree.

This is the file where trust moves towards AI over time: today a human may decide most of it; later the AI may decide and the human reads.

## The gate

A prototype becomes the product when it passes the gate:

- every behaviour it has is described by a rule
- every rule is proven

A fresh agent that has read only the living files reads the code and lists every behaviour no rule describes.

Each one becomes a rule, with human approval, or comes out of the code.

Then the proof runs green.

Whether the code that passes is the prototype cleaned up or a rebuild from the living files is a how, chosen per feature and free to change later.

The living files must never need the code to be understood.

The code may lean on them all it likes.

A feature is Live when its proof is green.

Nothing else makes it Live.

## Living

After the gate, the same loop runs on the product:

1. **Try.** People use it.
2. **Learn.** Read the signals. Change a rule or the why.
3. **Build.** Code follows.

Every rule change is one learning.

Its reasoning lives in the feature change entry. Its effect is reflected in the feature file and indexed in the change log.

If the learning is big, the change goes through Shaping with a new prototype.

It is clay again.

### A change is not finished when it adds

Behaviour that goes away takes its rule and proof with it.

Behaviour that changes changes them.

A feature file that only ever grows is going out of date in a new location.

### How a change is reviewed

AI proposes the change to a living file and says what it conflicts with:

- a rule it contradicts
- a rule it makes unreachable
- a rule in another feature that now says the same thing twice
- behaviour in the diff that no rule describes
- a feature in the map past Idea with no folder
- a folder with no line in the map
- any sentence elsewhere made stale by the change

The check covers every living file and this method, not only the file being changed.

The proposed fix travels with each finding.

A human reads those findings and approves, or does not.

For a feature change, the findings travel in its change entry, so the human judges a short list rather than rereading the whole feature file.

The proposal is read as a document that shows the current state: what changes, what is still open, the part as it would read. The back and forth is not kept. What was settled, overrules included, is recorded once, at the end, with the findings. The findings reach the second reader too: in the feature change entry, or in the request's description.

What AI cannot catch is a rule that is coherent, proven and no longer what the customer needs.

That surfaces when a person reads the file, when a signal stops moving, or when the next change arrives and the old promise no longer fits.

That is why a human owns the why.

## Self-improvement

The same intelligence that keeps the files reviews the way we work.

Signals that do not move, rules that could merge, proofs that take too long, a step of the loop nobody uses, a decision that has stopped paying: the AI notices and proposes.

The human negotiates, agrees or declines.

The proposal and the answer go in the log, so the next reader knows it was considered.

This applies to the product, to the manifesto, and to this method.

## Who does what

- Humans own why. They take responsibility for what gets built and for whom.
- Humans check that rules say what they meant. AI writes them.
- Humans approve every change to a living file. AI proposes it and says what it conflicts with.
- What a human says about how is input, not instruction. AI takes it, does its own thinking and research, and comes back with a better plan or a reason the human's is best.
- Human and AI negotiate how. The human decides.
- The decision is written with its why. An overrule is written as such, so the next reader knows it was a choice and not an oversight.

## Owners and approval

The repository names a default owner in its README, under Merge rules. A living file with no owner in its header is owned by the default owner, and a decision file by the owner of what it sits beside. A person is written by name with their git username: `Aivars (aivarsak)`.

A change to a living file is approved twice. Before the edit, as a proposal, by the person doing the work. Before the merge, as the change itself, by the reviewers of every living file it touches.

A file's reviewers are its owner, unless its header names others. Where it names several it also says how many must approve: any of them, all of them, or a number of them. Nothing said means any one. So by default every review goes to the default owner, and a file that needs more says so itself.

The author's own approval does not count, except in a team of one. In a team of one the second approval is the same person with a fresh mind: a day later, where the work allows.

@open how this is enforced is a decision.

## How we know it works

1. An agent that has read only the living files can say what a feature does, and the code agrees.
2. The implementation is rewritten and no rule changes.
3. A team that did not invent the method adopts it from a one-hour read and keeps using it.
4. Two features are shaped in parallel by people who do not talk to each other, and the whys above them still read as one product.
5. A change that removes behaviour leaves no rule behind.
6. A signal that did not move led to a why being rewritten or a feature being dropped.

## Later

Named so they are not forgotten.

Each is written in full when a feature needs it, and not before.

- **Tailoring.** Ten customers may run ten variants; a rule that holds for one names that customer among its conditions. What is common is found by reading rules across conditions and proposing merges, not declared upfront. How proof runs under every named condition and stays cheap.
- **Proof where conditions must change** and the customer's own tenant may not be touched: proven on a copy of their settings, never on their data.
- **Proof that two views agree.** Compare both; neither alone proves it.
- **Proof that something is absent.** Check what leaves the system, not a screen that hides it.
- **Team and personal method.** What a team shares and what each person keeps for themselves, and where each lives. First try: `example.method.md` shared, `my.method.md` ignored.