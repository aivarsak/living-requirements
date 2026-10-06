# The Living Product Method

How we practice Living Requirements.

The manifesto says what we believe. This method says what we do.

## Keep four things aligned

Every product has four things that must agree:

| | Thing | Says | Accountable |
| --- | --- | --- | --- |
| **Why** | Problem and outcome | Who has the problem, why now, and the outcome we want | Product |
| **What** | Capabilities and rules | What a person or another system can do, and what the product promises | Product |
| **What** | Proof | What we prove, for each promise, to know it holds | QA |
| **How** | Code and tests | How those promises are implemented, and the tests that show they hold | Engineering |

AI works across all four. Humans remain accountable.

The why and the what describe the product independently of its implementation. Code may be replaced without changing them.

When these disagree, we do not automatically trust either side. We find what is wrong and align them again.

## Keep product truth alive

The current why and what are kept as **living files**.

They live with the product and change as our understanding changes. They describe what we believe now, not the history of how we got there.

Evidence, requests, conversations, proposals and other working material describe changes. They may become historical.

**Change documents describe transitions. Living files describe state.**

Choices about how that a person settled are kept with the living files too, at the narrowest scope they apply to: the product, a part of it, or a feature. Broader ones apply together with narrower ones. A narrower choice may refine a broader one, but never silently contradicts it.

## Two loops, two gates

A feature is learned while it is shaped and while it is built. After it is released, its signals feed the next change.

**Shape and learn ↔ commit gate ↔ Build and prove ↔ release gate → Live → signals → the next change.**

It is not a waterfall. Each loop learns. Each gate is a decision people make. What we learn may send work back across a gate.

Three accountabilities are held, each by a human, even when AI does the work. Each has a title. The title means the accountability, not a job or a department. One person may hold more than one.

- **Product** is accountable for intent. Product decides any change of intent after the commit gate.
- **QA** is accountable for proof: how each rule is shown to hold. QA makes sure the tests do what the proof describes, and looks for what both miss. Where the team allows it, QA is not the person who built the feature.
- **Engineering** is accountable for delivery. Engineering decides how the commitment is kept: its approach and its pace. Engineering is accountable for the tests existing and passing.

Accountable means making sure it is done and saying when it is, not doing it alone. Who writes the why, the rules, the proof, the code or the tests is the team's choice. AI helps at every step: shaping and prototyping, writing feature files, capturing decisions, building, verifying, and reading signals.

A gate passes only when Product, QA and Engineering are each satisfied that their part holds, and have said so. A person who holds more than one is satisfied for each. Any of them can hold a gate; none can force it: a feature whose tests fail is not released, whoever is satisfied.

How they say so, by a pull request approval, a word in conversation or a step in an agent's workflow, is the project's choice.

A gate is passed by a feature, or by a change to a Live feature's promises. A fix that makes the code keep an existing rule passes no gate; its tests must pass.

## Shape and learn

A feature starts uncertain.

**Shape → Try → Learn → Repeat.**

Describe the problem and who has it. Make the smallest thing a real person can experience: a prototype, a sketch, a walk-through. Put it in front of a real person. Learn from what happens.

A prototype is a tool for learning, not a requirement.

Do not turn guesses into requirements too early.

What we learn and want the product to keep doing becomes a rule.

If something is too large to understand or try, break it along behaviour a person can observe and shape the smaller parts.

Shaping does not find everything. It finds enough to commit.

## Turn promises into rules

A rule describes observable product behaviour or a quality we want to preserve, not its implementation.

Humans own the rules. AI helps discover, express, challenge and maintain them.

Every rule has a proof: how we show that it holds, in one or more cases, observed in one or more places. The proof is implemented as tests. Here a test is any executable check that shows a rule holds: an end-to-end or unit test, an assertion, or an eval with a passing threshold. At the commit gate, we know the proof of each known rule. At the release gate, its tests exist and pass.

A rule's tests observe its behaviour from outside, wherever the rule says it is observed, not through the code that implements it. They still hold when the implementation is replaced.

If behaviour changes, its rule and proof change.

If behaviour disappears, its rule and proof disappear.

Behaviour not promised by a rule is free to change.

## Pass the commit gate

The commit gate asks: **do we understand what we intend to build well enough to commit to building it?**

A feature passes when:

- its problem and intended outcome are understood well enough to commit
- its capabilities and known rules describe what we now believe we are building
- its success is defined, where it can be
- for every known rule, we know how we will prove it
- Product, QA and Engineering are each satisfied

Tests do not need to exist yet. No prototype or UI is required. The known rules do not need to be all the rules there will be.

Committing is a promise to build, not a claim that learning is done.

## Build and prove

**Build → Prove → Learn → Repeat.**

Code and its tests grow together. Here known rules gain their tests.

Tests are built with the implementation. Whoever writes the implementation also writes the tests that prove it against the agreed proof. Others, including QA, may add or improve tests.

Building may reveal new rules, change existing ones, show edge cases, or reveal capabilities shaping missed. Each new rule is captured in the living files, given a way to be proved, implemented and proved, and approved like any other rule. Finding them is the loop working, not shaping failing.

A capability needed to keep what we committed to is not a change of intent. A change of intent is learning that materially changes the problem, the intended outcome, or the scope of the commitment. Product decides, in the open and not inside the code, whether it belongs in the current change or returns to shaping.

## Pass the release gate

The release gate asks: **can we prove that what we are about to release keeps the promises we now intend to keep?**

A feature becomes Live when:

- every behaviour and quality we intend to preserve is described by a rule
- for every rule, its tests exist and pass
- the code and the living files agree
- Product, QA and Engineering are each satisfied

A fresh agent should be able to read the living files, inspect the implementation, and find behaviour that is promised but missing, or present but not described.

The implementation may then evolve or be replaced as long as the promises continue to pass their tests.

## Keep learning after release

Release does not end the loop.

People use the product. We observe what happens. We learn. The why or rules change, and the change goes round the loops again.

Proof tells us:

**Did we build what we intended?**

Signals tell us:

**Was our intention right?**

Proof and its tests protect the product's promises. Signals challenge the assumptions behind them.

A defect found in use is triaged by where the gap was:

- **In the capabilities or rules** goes to Product.
- **In the proof** goes to QA.
- **In the implementation**, meaning the code or its tests, goes to Engineering.

Each is closed so that a rule, its proof and its tests cover it, and it cannot return unseen. Behaviour that keeps every promise but disappoints a person is not a defect. It is a signal.

## Let AI maintain alignment

AI helps shape the rules, write their proof, implement and test them, and looks for drift across the living files, code and tests.

It proposes changes and explains conflicts and consequences.

Humans own the why and the what and approve changes to product truth.

AI can increasingly own the work. Humans remain accountable for the product.

## Improve the method too

Living Requirements applies to itself.

When part of the method creates friction, adds no value or stops working, change it.

Keep what proves useful. Remove what does not.

The method is living too.

We know it works when:

1. A fresh agent can read the living files and correctly explain what a feature should do.
2. An implementation can be replaced without changing its rules.
3. Removing behaviour removes its obsolete rules and proof.
4. Independently shaped features still agree with the product above them.
5. Product signals cause assumptions to be reconsidered when reality disagrees with them.
6. Another team can understand and adopt the method without depending on its original authors.

## Layers

Everything else is implementation. It comes in layers:

| File | Says |
| --- | --- |
| `manifesto.md` | What we believe |
| `method.md` | What must be true to practice it |
| `default.method.md` | One good way to do it |
| `project.method.md` | How we do it here |
| `my.method.md` | How I personally work |

Each layer only chooses or adds. It never restates the layer above.

A lower layer may replace a choice made by the default, and says so with its why. None contradicts this file; if one needs to, it proposes a change here.

Where the project and a person disagree, the project wins, because the team shares it.