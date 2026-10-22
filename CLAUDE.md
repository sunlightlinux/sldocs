# CLAUDE.md

Guidance for LLM-assisted work in **sldocs**, the documentation
repository for Sunlight Linux.

This repository is unusual among the Sunlight repositories: it has no
code, no build and no tests. Nothing here fails loudly. A wrong document
is indistinguishable from a right one until somebody acts on it, which
makes the usual safety net — "run it and see" — unavailable.

Everything below follows from that.

## 1. A claim you cannot check does not go in

Before writing a number, a version, a count or a behaviour, establish
it. Run the command, read the source, measure the thing. Then put the
method in the document beside the result.

This is not pedantry. Across this project, documented figures have
drifted from reality repeatedly: a directive count stated as "~250" when
it was 304, a journalctl parity claim written as "65/65 flags" when the
project's own manual said "65-of-65 **short-alias** parity", a project
count that was stale in five files at once. Each was plausible and
unverified.

If you cannot establish a claim, say that in the document. "Not
verified" is information. A confident sentence is not.

## 2. Say what is not true yet

A requirement that is unmet, a spec describing an intention, a
configuration that is aspirational — all belong here, provided the
document says so in its opening lines. The templates ask for a status
for exactly this reason.

The failure mode to avoid is a document that reads as finished because
nothing in it admits otherwise.

## 3. One source per fact

Do not copy a number from another document. Link to it. Two copies of a
figure are two figures that will disagree, and the reader cannot tell
which is current.

This applies across repositories too: slinit's own documentation,
`CLAUDE.md` files and commit messages hold a great deal of reasoning.
Prefer linking to restating.

## 4. Do not silently correct the record

If a recorded measurement turns out to be wrong, the document says it
was wrong and what it is now. Someone acted on the old value. Replacing
it quietly removes the evidence that the project's numbers can drift,
which is itself worth knowing.

The same applies to a reversed decision: record why it reversed, in the
document that holds the decision.

## 5. Findings are about what hid the bug

`findings/` is not a changelog. Its most valuable section is *why it was
not caught earlier* — a test that pinned the broken behaviour, an
environment where the defect could not appear, a diagnostic silenced by
a default setting. The patch is the least transferable part.

Record the wrong hypotheses too, with what disproved each. A reader who
holds the same wrong theory is saved the detour.

## 6. Surgical changes

- Edit the document the request is about. Do not improve neighbours.
- Do not reorganise directories as a side effect of adding a file.
- A seventh directory is a decision to raise, not to make.
- If you notice an unrelated document is stale, say so; do not fix it in
  the same change.

## 7. What this repository is not for

- Not a mirror of code comments. If the explanation belongs beside the
  code, it belongs in the code.
- Not a place for a finding about an unfixed defect. Check the fix has
  shipped.
- Not a substitute for `git log`. A document that only restates what
  commits already say will go stale and be believed anyway.
