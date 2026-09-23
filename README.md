# Living requirements

A way for people and AI to build aligned products together. This
repository is the one home of the method. Every project that works by
it reads it from here, so a change made here reaches all of them.

- `manifesto.md` — what we believe.
- `method.md` — how we work: the loop, the living files and their
  shape, proof, signals, the gate, who does what.
- `layout.md` — where things sit in a project, and how work moves
  through git.
- `decisions.md` — how the method and the layout were chosen, and why.
- `example.method.md` — how one person works inside `method.md`. Each
  person's own is `my.method.md`, which git ignores. It sits here once,
  and every project reads it from here.
- `project.CLAUDE.md` — what an agent is told in every project.

## Use in a project

A project's `CLAUDE.md` imports the method instead of copying it:

```markdown
@~/Code/living-requirements/project.CLAUDE.md
```

Then only what is the project's own: its name, where its living
files are, and anything it does differently from `layout.md`, with
the why in its `decisions.md`. Its README names its merge rules.

A project keeps no copy of `manifesto.md`, `method.md`,
`layout.md` or `my.method.md`.

## Changing the method

The method is shaped the way a product is. A change to it is proposed
here, says what it conflicts with in the method and in the projects
that use it, and is approved by the owner. The decision goes in
`decisions.md` with its why, declined proposals included. This
repository keeps no log; the projects do.

## Merge rules

Default owner: Aivars (aivarsak). A team of one: his approval before
the merge, a day after the hand-off where the work allows.
