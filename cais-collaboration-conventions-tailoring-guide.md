# Tailoring the Collaboration Conventions File for Your Own Use

A guide for someone new adopting `cais-claude-collaboration-conventions.md` as a starting point
for their own Claude-collaboration conventions.

## What this file actually is

`cais-claude-collaboration-conventions.md` isn't a universal rulebook — it's one person's
accumulated conventions, each one written down because a real correction or a real confirmed
judgment call happened first. The numbered list reads as general principles, but several of them
encode a specific person's specific working style (how directly they want to be asked questions,
which surfaces they split work across). Adopting it wholesale means adopting someone else's
friction, not your own.

## Two starting points

**Option A — Start from scratch.** Begin with an empty conventions file and let entries accumulate
only from your own real sessions: a correction you gave Claude, or a non-obvious approach you
confirmed after the fact. This guarantees every rule reflects actual friction you've hit, and
nothing sits in the file that you haven't personally earned the need for.

- *Pros:* nothing borrowed that doesn't fit; the file stays lean and true to how you actually work.
- *Cons:* your early sessions have no accumulated guardrails — you'll re-hit some of the same
  friction the original author already worked through (terse question style, canonical-source
  drift, attribution blur) before you write your own version of the same rule.

**Option B — Clone the existing file as a scaffold.** Copy it in full, then go rule-by-rule and
decide keep-as-is / adapt / drop for each of the 11 conventions before treating it as adopted. This
gets you immediate coverage of practices that have held up across a wide range of work (evidence
over assertion, one-canonical-source discipline, separately-scoped handoffs) without waiting to
independently rediscover each one.

- *Pros:* faster to a useful baseline; several of these principles generalize well regardless of
  who's using Claude.
- *Cons:* a rule you didn't earn through your own friction is a rule you're less likely to have
  really internalized — it can quietly go stale or get ignored because it never mapped to something
  you actually lived through.

**Recommendation:** Option B as the mechanism, Option A as the discipline. Clone the file, do the
keep/adapt/drop pass below immediately rather than accepting it wholesale, and from that point on
treat it exactly like Option A — it only grows from your own real corrections and confirmations
going forward, regardless of which option you started from.

## Keep / adapt / drop pass — going section by section

| # | Convention | Likely portability | Ask yourself |
|---|---|---|---|
| 1 | Separate surfaces, separate jobs | Workflow-specific | Do you actually split design and execution across different Claude surfaces? If you only ever use one surface, drop or rewrite around your real split. |
| 2 | Handoffs separately scoped | Broadly portable | Does your work involve handing context between sessions or people at all? |
| 3 | Confirm a prerequisite landed | Broadly portable | Keep as-is for almost any multi-step work. |
| 4 | Elicitation: terse structured choices | **Personal style — likely replace** | This encodes one person's preference for how they want to be asked things. What's *your* actual preference — more explanation, more options, more back-and-forth? Write your own version. |
| 5 | Attribution matters | Broadly portable | Applies wherever AI-run and human-run work get reported on together. |
| 6 | Realistic stress-test content | Domain-specific | Only relevant if your work involves testing limits/scale/substitution mechanisms. Drop if not applicable. |
| 7 | Cost-consciousness | Conditionally portable | Applies if your work has recurring LLM-call or vendor costs. Drop or reframe if it doesn't. |
| 8 | Real-world verification for Claude/AI claims | Broadly portable, vocabulary specific | The principle generalizes; the four-tier verification vocabulary (code-verified / locally-verified / etc.) is engineering-flavored — translate the tiers to your own domain if needed. |
| 9 | Some failures only catchable by a human | Broadly portable | Keep as-is — close to a universal principle for AI-assisted work. |
| 10 | One canonical reference location | Broadly portable | Applies to anyone running more than one Claude Project or session that shares context. |
| 11 | Documentation/knowledge-base hygiene | Broadly portable | Applies to anyone maintaining a knowledge base or tracking doc at all. |

Rough read: **9, 10, 11, 3, 5** travel with minimal change; **2, 7, 8** travel with light
reframing; **1, 4, 6** are the ones most likely to need real rewriting or removal because they're
closest to the original author's specific workflow and personal style rather than general practice.

## Keeping the format once you've adopted it

Preserve two things about the structure, since they're what make the file useful rather than just
a list of assertions:

- **Every entry states its own "why."** Each numbered convention in the source file explains the
  reasoning or incident behind it in the same sentence, not just the rule. Do the same for your own
  entries — a rule without its reasoning is harder to judge later when deciding if it still applies.
- **New entries come from real moments, not anticipation.** The natural trigger is the same as any
  feedback-memory discipline: a correction given ("no, don't do X — here's why"), or a confirmation
  of a non-obvious approach that worked. Don't pre-write rules for situations you haven't hit yet —
  that's how you end up carrying someone else's friction again.

Keep the closing meta-note (or your own version of it) — the whole point of a document like this is
that it stays free of product- or project-specific detail so it can travel with you into any Claude
Project, not just the one it was written for.
