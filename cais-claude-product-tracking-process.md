# Claude Product & Capability Tracking — Process

This is a **process document, not a snapshot.** Anthropic's product surface changes continuously;
a static file listing "current capabilities" would itself become exactly the kind of stale artifact
these conventions warn against. What's captured here is *how* CAIS stays current, not a point-in-time
list of what's current.

## What to track

- New models and meaningful changes to existing ones (capability, pricing, availability)
- New product surfaces or features (e.g., a new agentic tool, a new connector type, a new
  interface)
- Deprecations or removals that could affect anything the user relies on
- Policy or access changes (e.g., regional availability, export controls, usage limits)

## How to check

- Search docs.claude.com and support.claude.com directly rather than relying on training-data
  memory — this applies to CAIS itself as much as to any claim it evaluates from a third party.
- Check anthropic.com/news for announcements not yet reflected in documentation.
- Do this at the start of any session where a product-capability question comes up. There is no
  automatic or scheduled monitoring in place today — this check is session-triggered only, not run
  on an independent cadence.

## What to do with a finding

Checking the live docs to answer a question is automatic and needs no prompting — that's just
giving the user an accurate answer. There is no persistent tracking file for capability findings;
CAIS re-checks live documentation each time rather than maintaining a log.

1. State what changed and cite the source (a docs page or news post), not a recollection.
2. Assess relevance — does this affect how the user currently works with Claude, or open up a new
   capability worth adopting?
3. If relevant, package it as a clear recommendation — adopt / adapt / not applicable, with
   reasoning.
4. If the finding is significant enough to change how the user works, deliver it directly to the
   user as a standalone recommendation (see the collaboration conventions on handoffs) rather than
   storing it anywhere in CAIS's own knowledge base.

## What not to do

Don't build a comprehensive internal encyclopedia of Claude's capabilities — that duplicates
Anthropic's own documentation, will drift out of sync with it, and recreates the exact stale-copy
problem these conventions exist to prevent. Point to the real documentation; track only the *delta*
relevant to the user's actual usage.
