# Living Requirements

A way for people and AI to build aligned products together.

Code is cheap now. Knowing what the product should do, and knowing it still does, is not.

Nobody can say what they want on the first try. We find it by shaping: describe, prototype, try, learn, again. What we learn and want to keep becomes a rule with a proof. A proof is how we know what we wanted to keep stayed, iteration after iteration, long after anyone remembers why.

"We" is whoever works this way: the people and the AI on one product.

Think big, act small. The why may be as large as the vision. Every step is the smallest thing a real person can try, and every solution the simplest one that passes the proof.

We keep three things:

**The why** — the problem, for whom, what success looks like, and how we will know. Humans lead. AI helps write it. This is where someone takes responsibility.

**The rules and their proof** — what the product does. Rules are written so a person can read them, each with a test a machine runs again and again. Green means the product does what we said. AI leads. Humans check that the rules say what they meant.

**The code** — how. Whatever makes the proof pass. AI writes and reviews most of it. Humans may write some too, when an edit is faster than asking. Humans may set the direction — architecture, stack, constraints — or leave that to AI too.

What people and AI agree on lives in the repo, apart from the code, in **living files**: a product file for the why, a feature file for what each feature does, and decision files wherever how had to be chosen.

## Rules

1. **No proof, no feature.** Until a rule runs, it is an idea.

2. Rules describe behaviour a customer can observe, through any door: a screen, an API, a message, a file, an agent. Never a function, a table or a mock.

3. What no rule says is not promised. It may change. So may the code under any rule, without asking, as long as the proof stays green.

4. A rule holds only under the conditions it names. A rule whose conditions are not stated is a coin flip.

5. Removing behaviour removes its rule and its proof. A change that replaces behaviour and only adds has not finished.

6. A prototype is not the product until every behaviour it has is a rule and every rule is proven. Keep it or rebuild it; either is fine.

7. Behaviour that is not deterministic is scored, not asserted.

8. Proof is not success. Success is a signal, measured from the product's own data over time and read weekly. Signals steer the why; they never gate a build.

9. Every feature file has the same shape, so a stranger finds their way in any of them. What that shape is, the team decides.

10. Every change to a living file is approved by a human. AI proposes it and says what it conflicts with. How is negotiated: AI owes a better plan or a case for the human's, the human decides, and the decision is written with its why, overrules included.

11. Nothing else is fixed. Process, tools and layout are the team's.

## Build for the customers you can reach

Building is cheap, so build for the few customers you have, and build what they need.

Tailoring used to be a maintenance nightmare because a human had to hold every combination in their head. An AI can hold them, as long as every tailored rule is written down with the conditions it holds under.

What is common across customers is found by reading the rules, not decided in advance. Ten variants are fine. The eleventh customer shows which parts were the product all along.

## Living files and the documents that feed them

A PRD, a ticket, a customer call: each is about a change. It has a beginning and an end, it records who asked and why now, and it closes when the change ships. It is right that it then goes out of date.

A living file is about state. It says what we intend, what the product does today, or what we decided and why. It has no end. Every change that touches that truth updates it, including changes that take behaviour away.

So the documents that start work are inputs. They are named by the living files they feed, and they are not maintained.

A feature change entry is one of them: it carries the why and the findings of one change, and closes when that change is live.

Living files describe current truth. Change documents describe transitions.

## The method

This manifesto says what we believe.

**The Living Product Method**, kept beside it in `method.md`, says how we work: the loop of describe, prototype, try, learn and build, and the shape the living files take.

The method is shaped the same way the product is. AI reviews the manifesto and the method as it works, and proposes changes when something gets in the way or is missing. A human approves every change.

Nothing here is final.

## The bet

An agent can keep the three in sync for as long as the product lives.

We test this. We do not assume it.