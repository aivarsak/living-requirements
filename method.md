# The Living Product Method

How we practice Living Requirements.

The manifesto says what we believe. This method says what we do.

## Keep four things aligned

Every product has four things that must agree:

| | Says | Led by |
| --- | --- | --- |
| **Why** | Why this should exist and for whom | Human |
| **Rules** | What the product promises | Human |
| **Proof** | How we know those promises hold | AI |
| **Code** | How those promises are implemented | AI |

Humans own what should be true. AI helps discover, express and challenge it.

AI leads how we prove and implement it.

The why and rules describe the product independently of its implementation. Code may be replaced without changing them.

When these disagree, we do not automatically trust either side. We find what is wrong and align them again.

## Keep product truth alive

The current why and rules are kept as **living files**.

They live with the product and change as our understanding changes. They describe what we believe now, not the history of how we got there.

Evidence, requests, conversations, proposals and other working material describe changes. They may become historical.

**Change documents describe transitions. Living files describe state.**

Choices about how that a person settled are kept with the living files too, at the narrowest scope they apply to: the product, a part of it, or a feature. Broader ones apply together with narrower ones. A narrower choice may refine a broader one, but never silently contradicts it.

## Two loops, two gates

A feature is learned while it is shaped and while it is built. After it is released, its signals feed the next change.

**Shape and learn ↔ commit gate ↔ Build and prove ↔ release gate → Live → signals → the next change.**

It is not a waterfall. Each loop learns. Each gate is a decision a person makes. What we learn may send work back across a gate.

Each loop has a person accountable for it:

- **Shape and learn**, up to the commit gate: the person accountable for product intent. They decide whether we commit, and any change of intent after it.
- **Build and prove**, up to the release gate: the person accountable for delivery. They decide how the commitment is kept: its approach, its pace, and when it passes the release gate.

One person may be both. Both are humans, even when AI does the work.

## Shape and learn

A feature starts uncertain.

**Shape → Try → Learn → Repeat.**

Describe the problem and who has it. Try the smallest thing that can teach us: a prototype, a sketch, a conversation, a walk-through. Put it in front of a real person where one can be reached. Learn from what happens.

A prototype is a tool for learning, not a requirement.

Do not turn guesses into requirements too early.

What we learn and want the product to keep doing becomes a rule.

If something is too large to understand or try, break it along behaviour a person can observe and shape the smaller parts.

Shaping does not find everything. It finds enough to commit.

## Turn promises into rules

A rule describes observable product behaviour or a quality we want to preserve, not its implementation.

Humans own the rules. AI helps discover, express, challenge and maintain them.

Every rule is proved by tests, assertions, evals or other executable checks that show whether it holds. At the commit gate, we know how we will prove each known rule. At the release gate, its executable proof exists and passes.

AI leads the proof.

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

Executable proof does not need to exist yet. No prototype or UI is required. The known rules do not need to be all the rules there will be.

Committing is a promise to build, not a claim that learning is done.

## Build and prove

**Build → Prove → Learn → Repeat.**

Code and its proof grow together. Here known rules gain their executable proof.

Building may reveal new rules, change existing ones, show edge cases, or reveal capabilities shaping missed. Each new rule is captured in the living files, given a way to be proved, implemented and proved, and approved like any other rule. Finding them is the loop working, not shaping failing.

A capability needed to keep what we committed to is not a change of intent. A change of intent is learning that materially changes the problem, the intended outcome, or the scope of the commitment. The person accountable for product intent decides, in the open and not inside the code, whether it belongs in the current change or returns to shaping.

## Pass the release gate

The release gate asks: **can we prove that what we are about to release keeps the promises we now intend to keep?**

A feature becomes Live when:

- every behaviour and quality we intend to preserve is described by a rule
- for every rule we intend to preserve, the executable proof exists and passes
- the code and the living files agree

A fresh agent should be able to read the living files, inspect the implementation, and find behaviour that is promised but missing, or present but not described.

The implementation may then evolve or be replaced as long as the promises continue to pass their proof.

## Keep learning after release

Release does not end the loop.

People use the product. We observe what happens. We learn. The why or rules change, and the change goes round the loops again.

Proof tells us:

**Did we build what we intended?**

Signals tell us:

**Was our intention right?**

Proof protects the product's promises. Signals challenge the assumptions behind them.

## Let AI maintain alignment

AI helps shape the rules, creates their proof, implements them, and looks for drift across the living files, proof and code.

It proposes changes and explains conflicts and consequences.

Humans own the why and rules and approve changes to product truth.

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