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

## Discover before you preserve

A feature starts uncertain.

**Shape → Try → Learn → Repeat.**

Describe the problem and who has it. Make the smallest thing someone can experience. Put it in front of a real person. Learn from what happens.

Do not turn guesses into requirements too early.

What we learn and want the product to keep doing becomes a rule.

If something is too large to understand or try, break it along behaviour a person can observe and shape the smaller parts.

## Turn promises into rules

A rule describes observable product behaviour or a quality we want to preserve, not its implementation.

Humans own the rules. AI helps discover, express, challenge and maintain them.

Every rule has proof: tests, assertions, evals or other executable checks that show whether it holds.

AI leads the proof.

If behaviour changes, its rule and proof change.

If behaviour disappears, its rule and proof disappear.

Behaviour not promised by a rule is free to change.

## Pass the gate

A prototype becomes product when:

- every behaviour and quality we intend to preserve is described by a rule
- every rule has proof
- the proof passes

A fresh agent should be able to read the living files, inspect the implementation, and find behaviour that is promised but missing, or present but not described.

The implementation may then evolve or be replaced as long as the promises continue to pass their proof.

## Keep learning after release

Release does not end the loop.

People use the product. We observe what happens. We learn. The why or rules change. Proof and code follow.

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