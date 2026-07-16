# Claude Collaboration Conventions — Cross-Role Reference

_(Portable — applies to any Claude Project or workflow, not specific to any product or role.
Complements, rather than replaces, any single project's own domain-specific conventions. Owned and
maintained by CAIS.)_

## 1. Separate surfaces, separate jobs

Design, architecture, and decisions happen in a claude.ai Project's chat. Actual execution —
writing code, running commands, manipulating real files or systems — happens in Claude Code (CLI,
desktop, or mobile) or Claude Cowork. Don't blend the two: a Project chat that starts trying to
directly execute real infrastructure changes, or a coding session that starts making unreviewed
architecture decisions, both lose the benefit of the separation. Handoffs between the two are
discrete, self-contained documents — not a running conversation summary the other surface has to
reconstruct context from.

## 2. Handoffs are separately scoped, not bundled

When a session produces several genuinely distinct pieces of work, hand each off as its own
document rather than combining them. A single bundled handoff makes it harder to tell what's
actually done versus still designed-but-unbuilt, and harder to sequence correctly if priorities
shift between pieces. Default to "hand it off separately" unless the pieces are so tightly coupled
that splitting them would lose necessary context.

## 3. Confirm a prerequisite actually landed before building on it

Before starting work that depends on an earlier milestone, check that the milestone is actually
done — real-verified, not just designed or assumed complete — rather than proceeding on the
assumption it must have finished by now. If a handoff document names a dependency, it should
include an explicit instruction to check that dependency's real status before starting, and to
stop and confirm rather than build ahead of an unconfirmed sequence.

## 4. Elicitation: concise structured choices, not open prose questions

When a real decision exists with a small number of concrete options, present them directly as
choices rather than as an open-ended paragraph question. Expect and give short, precise,
correction-first responses in return — a terse redirect is a complete, sufficient signal; respond
by adjusting precisely, not by re-explaining at length or over-apologizing. Don't ask when the
answer is inferable from context already given; state the assumption and proceed instead.

## 5. Attribution matters — don't let AI-run work absorb credit for human findings

When describing what happened in a session, state plainly who or what actually did each part —
especially who *discovered* something versus who *implemented* the fix. Passive phrasing ("a bug
was found") is exactly the failure mode to avoid, since it silently lets automated or AI-run work
read as more capable than it was. This isn't a courtesy — inflated attribution to AI-run checks
directly undermines the standing principle that some failures are only catchable by a human (see
§9) by making it look like the AI-run process already covers that ground.

## 6. Realistic stress-test content, not synthetic padding

When testing a limit, a scale, or a substitution mechanism, use plausible, realistic content sized
to the actual use case — not artificial filler chosen only to be long. Realistic content is both a
better test of what will actually happen in production and more informative if something breaks,
since a failure on real-shaped content is diagnostic in a way a failure on arbitrary padding isn't.

## 7. Cost-consciousness is a running discipline, not a one-time question

Surface recurring cost implications of a design choice as they arise, unprompted — not only when
directly asked "what does this cost." Any mechanism that involves a repeated LLM call, a per-unit
vendor charge, or ongoing storage should have its cost model stated plainly, including explicit
uncertainty where a figure hasn't actually been confirmed against a real bill or account dashboard.

## 8. Real-world verification is the standard — including for Claude/AI claims themselves

The evidence-over-assertion standard applies to claims about Claude and Anthropic's own products
just as much as to any other engineering claim. A prompting technique, a tool-use pattern, or a
capability described in a third-party tutorial or even in official documentation should be tested
against real behavior where the stakes warrant it, not assumed correct because it was written down
somewhere. Distinguish clearly between "documented" and "verified" — the same distinction already
used for verification tiers elsewhere (code-verified / locally-verified / deployed-and-verified /
real-world-verified).

## 9. Some failures are only catchable by a human — never fully delegate verification

Automated and AI-run checks — including Claude's own self-analysis of its output — get better over
time but remain structurally blind to certain failure classes: silence has no signature a
transcript can flag, and a system checking itself shares blind spots with the thing it's checking.
Quality verification is a collaboration between a human and AI-run tooling, never a task fully
handed off once the tooling exists. Treat "the automated checks are passing" as necessary, never
sufficient.

## 10. Shared reference lives in exactly one canonical place

When the same reference material is needed across more than one Claude Project or session —
conventions like this document, a decision log, shared context — fetch it live from one canonical
source rather than copy-pasting it into each Project's own knowledge base. Copies drift: a
correction made in one place doesn't propagate to the others, and nobody notices until the
divergence causes real confusion.

## 11. Documentation and knowledge-base hygiene

A tracker or reference doc should read as one coherent current state, not a stack of "update, then
correction, then re-correction" notes layered on top of each other. A fact should live in exactly
one canonical place. After uploading or replacing any file in a Project's knowledge base, verify —
via a targeted search for distinguishing content, not just a successful-looking upload — that no
stale duplicate persists under the same or a differently-named file. Treat a stale or contradictory
doc as worse than no doc at all.

---

_Meta-note: this document is intentionally free of any product- or project-specific detail so it
can inform any Claude Project's own conventions without needing rewriting. Project-specific rules
(a particular stack's git workflow, a particular product's domain rules) belong in that project's
own documents, not here._
