# Contributing to sldocs

This repository holds the documentation for Sunlight Linux —
requirements, specifications, plans, the known-good configuration, how
AI agents are used on the codebase, and what has been learned from
things going wrong.

It contains no code. Contributions are Markdown.

## Where a document goes

`README.md` has the table. If a document does not obviously belong in
one of the six directories, that is worth raising in the issue tracker
before writing it — a seventh directory is a real decision, and so is
stretching one of the six.

Each directory has a `TEMPLATE.md`. They are not ceremony: the sections
exist because documents without them turn out to be unusable later.
`findings/TEMPLATE.md` in particular asks *why it was not caught
earlier*, which is the section that makes a finding worth more than a
changelog entry.

## What makes a document worth having

- **Checkable claims.** "Boot reaches a login prompt in under two
  seconds on the reference hardware" can be verified. "Boot is fast"
  cannot, and will be quietly untrue within a release.
- **The evidence, not only the conclusion.** A number with the command
  that produced it survives. A remembered number decays, and the next
  reader cannot tell which they are holding.
- **An honest status.** A requirement that is not met, a spec that
  describes an intention, a configuration that is aspirational — all
  fine, provided the document says so in its first lines.
- **One source for each fact.** A number copied into a second document
  is a number that will eventually disagree with itself. Link instead.

## Submitting Changes

1. Fork the repository
2. Create a branch (`git checkout -b docs/boot-requirements`)
3. Write the document, following the directory's template
4. Check your links resolve
5. Commit, push, open a Pull Request

## Updating an existing document

- **Do not silently correct a recorded measurement.** If a figure turns
  out to be wrong, say that it was wrong and what it is now. The
  previous value was acted on by somebody.
- **A document that is no longer true gets a status line, not a
  deletion.** `superseded by <link>` tells the next reader where to go;
  a missing file tells them nothing.
- **Changing a decision means recording why it changed**, in the
  document that holds the decision. A reversal with no reason gets
  reversed again.

## Reporting Issues

Use the issue tracker for a document that is wrong, missing, or
misleading — including one that overstates how finished something is.
Anything that would disclose a vulnerability in the system itself
belongs in `SECURITY.md`, not here.
