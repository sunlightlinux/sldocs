# <topic>

## What agents are given

Which context, which tools, which repositories. Be specific: an agent
with shell access to a machine that is reachable only over SSH is a
different proposition from one editing files in a scratch checkout.

## What they are trusted to do alone

The actions that need no confirmation. Keep this list short and
concrete.

## What they must not do without a human

The actions that are hard to reverse or outward-facing — pushing,
tagging, publishing, touching a remote machine's boot path, anything
that can lock a system out.

## What went wrong, and what it cost

The honest part, and the reason this directory exists. An agent that
asserted something plausible and unverified, or measured through a
broken path and reported a clean negative, is more instructive than one
that worked. Record the mistake and the signal that would have caught
it earlier.
