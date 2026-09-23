# Layout

Where things sit in a project that works by `method.md`, and how work
moves through git. The manifesto leaves layout to the team; this is
the one every project here shares. A project's own README names its
exceptions and its merge rules.

## The shape of a feature

The manifesto says every feature file has the same shape. This is it.

- One folder, `features/<slug>/`. A feature inside a feature is a
  folder inside its parent: `features/trip-brief/who-to-see/`. The
  folder tree is the feature tree, and the product file's map names
  every feature in it.
- `<slug>.feature.md` in the folder: the feature file as `method.md`
  describes it, its change log at the end. The name carries the slug
  so the file says what it is when opened alone.
- Ids are slugs, minted once in the feature file and never reused. A
  capability's heading carries its slug in code, and a rule starts
  with its own. Outside the file the feature's path goes in front,
  joined by dots: `morning-brief.receive.asked-first`. Tests, task
  files and feature change entries carry that. Inside one feature a
  capability does not take the slug of a smaller feature.
- `<slug>.decisions.md` beside it when the feature has how of its own.
- `changes/` in the folder: one entry per feature change, named
  `<date>-<slug>.md`, closed when the feature change is live.
- `tasks/` in the folder: one short file per open task branch, named
  by what the branch adds to its parent's name, `compose.md`,
  `receive.asked-first.md`, removed at the merge. Not a living file.
- Proof lives with the code, wherever the stack puts tests, never in
  `features/`. Each test carries its rule id, and the rule names
  where it is proven.
- Status is in the header. A feature with no green proof is not live,
  whatever the header says.
- While the feature is being shaped, its prototype sits at
  `prototypes/<same path>/`, never inside `features/`.
- `inputs/` at the root: the documents that fed the living files,
  named in them and not maintained.

## Working in parallel

- `main` holds living files, prototypes worth trying, and real code
  whose proof is green. Nothing red is on `main`.
- Nothing is shaped on `main`. Every piece of work takes its branch
  from the first day, so every change has a request and a second
  reading.
- A branch is one piece of work: a new feature, a feature change, or
  a task inside either. A task is what one person or one agent does
  in one go. It may have tasks. It is not a feature. Work committed
  straight to a feature's branch is not a task and needs nothing.
- A piece of work branches from what it belongs to and merges back
  there: a new feature and a feature change from `main`, a task from
  its feature, its feature change or its parent task. A task on a
  live feature with no feature change open, a bug mostly, branches
  from `main`.
- A branch is named by the id of what it works on: `morning-brief`
  the feature, `morning-brief.compose` that capability,
  `morning-brief.receive.asked-first` that rule. A second branch open
  on the same id takes the date it was opened at the end:
  `morning-brief.compose.2026-09-24`. Work that answers to no single
  capability or rule, a feature change, a bug across capabilities, a
  chore, is its parent's name, then the date it was opened and a
  slug: `trip-brief.who-to-see.2026-11-03-skip-paid-up`. A task's name
  starts with its parent's. What a branch adds to its parent's name
  is its file's name. Work that answers to no feature:
  `root.<date>-<slug>`.
- Every branch is described by one file: a feature by its feature
  file, a feature change by its entry in `changes/`, a task by
  its file in `tasks/` beside them: its name on top, then briefly
  what and why. A type only when it is a bug or a chore. No status.
  Work paused on purpose gets a Shelved line with the date and why,
  and its branch gets `.shelved` at the end of its name until it is
  picked up again. AI writes the task file when it creates the
  branch, and pushes at once so others can see it. At the merge AI
  reads the task file for anything worth keeping and proposes it
  where it belongs, a decision, a rule, an open question; then the
  file is removed and its text goes into the merge commit. One
  worktree per open branch.
- A branch from `main` merges back whenever a living file changes
  and is approved, whenever a prototype is ready for someone to try,
  and real code only when its proof is green. It takes `main` back as
  often. A task merges to its parent when the parent's owner wants
  it; red is allowed there.
- A branch is deleted once it is merged for good, with its worktree:
  a task when it merges, a feature change or a feature when it is
  live. Every branch that exists is open or shelved.
- Two branches that touch the same feature file will conflict on a few
  lines. That conflict is the coordination. Resolve it by hand and
  keep the file readable as one.
- There is no other tracker. What is in flight is the pushed
  branches: the name says what each belongs to, its file what it is
  for, its latest commit who and when, and whether it still exists
  whether it is open. Whose turn it is, is the state of its request,
  draft or ready. Where a feature or a feature
  change stands, and any date committed for it, is in its header.
  What we know we must revisit is every `@todo` and `@open`. Anyone
  gathering status, person or agent, reads these.

