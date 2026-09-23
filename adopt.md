# Adopt Living Requirements

For an agent asked to make a project work by Living Requirements.
Read `manifesto.md`, `method.md` and `default.method.md` first. They
are at https://github.com/aivarsak/living-requirements.

## In the project

1. Copy `manifesto.md`, `method.md` and `default.method.md` from the
   latest commit on `main` into `living-requirements/` at the project
   root. Note the commit.
2. Create `living-requirements/project.method.md`. Ask the owner only
   what this project or team does differently from
   `default.method.md`, and write each difference with its why. If
   nothing differs, the file is just:

   ```md
   # Project method

   How this project works inside `default.method.md`: only what
   differs, each with its why.

   ## Proposals
   ```

3. Add the block below to the project's `CLAUDE.md`, or to
   `AGENTS.md` if the project uses that. Create `CLAUDE.md` if there
   is neither. Put the commit in place of `<commit>`.
4. Documents the project already has, a PRD, notes, tickets, are
   inputs. Do not convert them now. The living files grow from them as
   the work begins.

```md
## Living requirements

We work by Living Requirements. Read these before anything else:

@living-requirements/manifesto.md
@living-requirements/method.md
@living-requirements/default.method.md
@living-requirements/project.method.md

The first three came from
https://github.com/aivarsak/living-requirements at `<commit>`.

- Never edit the three copied files. What this project does
  differently goes in `project.method.md`, with its why.
- Watch the method while you work. When a convention gets in the way
  or something is missing, add a proposal to the file it belongs to,
  as `default.method.md` "Tailoring and proposals" says. An approved
  Upstream proposal becomes a pull request to the repository above.
- "Update the method" means: fetch the latest, show what changed and
  what it conflicts with here, and on approval replace the copies and
  the commit above.
```

## For the person, once

5. If the person has no `my.method.md` yet, ask a few questions about
   how they like to work with an agent: how they review, how they
   approve, where they work. Write their answers as `my.method.md`
   where their agent reads its user instructions. For Claude Code that
   is `~/.claude/my.method.md`, with `@~/.claude/my.method.md` added
   to `~/.claude/CLAUDE.md`. Start it as:

   ```md
   # My method

   How I work inside Living Requirements, in every project. Where it
   and a project's method disagree, the project wins or gets a
   proposal.

   ## Proposals
   ```

## Then

6. Tell the owner what was created. Nothing else needs setting up: the
   product file, features and proof come as the work begins, as
   `default.method.md` describes.
