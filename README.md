# sldocs

Documentation for [Sunlight Linux](https://github.com/sunlightlinux) —
what the system is required to do, how it is specified, what is planned,
the configuration known to work, and what has been learned from things
going wrong.

Checked out at `docs/` by the [repo
manifest](https://github.com/sunlightlinux/slmanifests), in a default
`repo sync`: these documents are meant to be read beside the code they
describe.

## Layout

| Directory | Holds |
|-----------|-------|
| `requirements/` | What the system must do, and for whom. Stated so that a reader can tell whether it is met. |
| `specs/` | How a requirement is met — interfaces, formats, protocols, state machines. |
| `plans/` | What is being done next and in what order, including release planning. |
| `config/` | The known-good distribution configuration — kernel config, package sets, service trees, and the reasoning behind the choices. |
| `ai/` | How AI agents are used on this codebase: what they are given, what they are trusted to do alone, and what they must not do. |
| `findings/` | One document per investigation: the bug, the fix, and what was learned. |

## Why `findings/` is one directory and not three

Bugs, fixes and discoveries were going to be separate places. They are
not separate things.

The soft-reboot state-loss defect is the example. One cause — injected
flags appended where argument parsing never reached them — produced four
symptoms, took four wrong hypotheses to find, and the most valuable
output was neither the bug nor the patch but a set of transferable
lessons: that the development VM was the only environment where the
defect could not appear, and that `quiet` on the kernel command line
silences the diagnostics you would reach for.

Split across three directories, that is three stubs and two
cross-references. As one document it is a thing someone can read.

Splitting later is a `git mv` if this turns out wrong.

## Conventions

- **Markdown, one topic per file**, named for the topic rather than a
  date or a ticket number.
- **Say when something is not true yet.** A requirement that is not met,
  a spec that describes an intention, a config that is aspirational —
  all fine, provided the document says so. Sunlight's repository
  descriptions do this (`Early development`, `Beta stopgap`), and the
  habit is worth more here than anywhere.
- **Record the evidence, not just the conclusion.** A measured number
  with the command that produced it survives; a remembered one decays.
- **Link rather than restate.** A number copied into a second document
  is a number that will disagree with itself.

## Status

Freshly seeded. The structure is settled; the content is not written.
