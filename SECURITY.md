# Security Policy

## Scope of this repository

`sldocs` contains no executable code. What it contains is
**descriptions of how Sunlight Linux is built and configured**, which
makes it security-relevant in two specific ways:

- **A known-good configuration that is wrong is acted on.** A document
  in `config/` that recommends a weaker setting than intended — a
  permissive service directive, a disabled hardening option, a service
  running with more privilege than it needs — becomes the setting that
  ships, because that is what the directory is for.
- **A specification that misstates a security property invites a
  reimplementation that is unsafe.** A spec in `specs/` claiming an
  input is validated, or that a path is opened without following
  symlinks, is something someone else will build against.

## Reporting a Vulnerability

If you find a vulnerability **in Sunlight Linux itself**, report it
against the repository that holds the code —
[slinit](https://github.com/sunlightlinux/slinit),
[slpam](https://github.com/sunlightlinux/slpam),
[slpkgs](https://github.com/sunlightlinux/slpkgs) — not here.

If you find a **document** that recommends or describes something
insecure:

**Do NOT open a public GitHub issue if the document reveals an
unfixed weakness in the shipped system.** In that case, email
ionut_n2001@yahoo.com.

If the document is simply wrong and the system is not affected, a public
issue is fine and preferable — it gets fixed faster.

Include:

- The file and the claim
- Why it is unsafe, or what it understates
- Whether the shipped system follows the document today
- What it should say

You should receive a response within 48 hours.

## A note on findings

`findings/` records defects that have been fixed, including security
ones, with their causes. That is deliberate: a fixed vulnerability whose
cause is written down is how the next one gets caught earlier.

A finding for a defect that is **not** fixed does not belong here yet.
If you are writing one, check the fix has shipped first.
