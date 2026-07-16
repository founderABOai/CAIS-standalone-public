# CAIS-standalone

A standalone Claude Project acting as a "Chief AI Science Officer" (CAIS) — an advisor focused
entirely on the effective use of Claude and Anthropic's tools, not on any product, business, or
domain decision itself.

This is a company-agnostic fork of a CAIS Project originally built as one of several peer
"officer" Projects in a multi-project company structure. This copy has been decoupled from that
structure: no references to other officer-Projects, no shared org-wide documents, no
founder/officer routing. It reports to "the user" and travels into any context.

## What CAIS does

- Advises on how to structure Claude Projects (instructions, knowledge bases, memory) for a given
  role or task
- Advises on effective use of Claude Code, Claude Cowork, Claude in Chrome/Excel/PowerPoint, the
  API, MCP connectors, artifacts, and other Anthropic product surfaces
- Advises on prompting technique, agentic workflow design, and general "how to get good results
  from Claude" practice
- Stays current on Claude/Anthropic product capabilities via live documentation checks, rather
  than relying on training-data memory
- Maintains a portable "how the user works with Claude" conventions reference

CAIS does not do the underlying engineering, business, or domain work itself, and does not set
strategy, pricing, or roadmap priorities — it recommends tools and methods, the user (or another
project) executes.

## Files

- `CLAUDE.md` — the Project's operating instructions: scope, decision authority, working style,
  and how the reference files below are used.
- `cais-claude-collaboration-conventions.md` — portable Claude-collaboration conventions (evidence
  over assertion, verification tiers, handoff discipline, knowledge-base hygiene, etc.).
- `cais-claude-product-tracking-process.md` — the process (not a snapshot) for staying current on
  Claude/Anthropic product changes.
- `cais-knowledge-base-plan.md` — how CAIS's own reference material is structured.

## Deploying this

**Claude Code (CLI)** — the native fit. Clone this repo and run `claude` from inside it; CLAUDE.md
auto-loads, and the reference files are read directly from disk as instructed. Auto memory
(`~/.claude/projects/<project>/memory/`) is machine-local and starts empty for each new clone — it
does not travel with the repo.

**Claude.ai Project** — requires adaptation. Paste `CLAUDE.md`'s contents into the Project's
custom instructions field, and upload the reference `.md` files to the Project's knowledge base
panel. The "Local reference files" and "Retrieval discipline" sections of `CLAUDE.md` currently
describe a read-from-disk model specific to Claude Code; on claude.ai, files are retrieved via the
built-in knowledge-base search instead, so those sections would need rewriting to match.
