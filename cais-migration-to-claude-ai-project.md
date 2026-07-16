# Migrating CAIS from Claude Code CLI to a claude.ai Project

CAIS currently runs as a Claude Code CLI project: `CLAUDE.md` plus three reference files live as
plain files on disk in this directory, read directly by the CLI. This guide walks through
standing up the equivalent as an actual claude.ai **Project** (Settings → Projects, or
claude.ai/projects → "+ New Project"), and flags the handful of places where the two platforms
don't map 1:1.

Verified against current claude.ai documentation as of this writing (support.claude.com); reconfirm
before migrating if it's been a while — this is exactly the kind of claim CAIS itself is supposed to
re-check rather than trust to memory.

## Concept map

| Claude Code CLI (this repo) | claude.ai Project equivalent | Notes |
|---|---|---|
| `CLAUDE.md` | Project **custom instructions** field | Paste content in, with the two edits below |
| `cais-*.md` reference files | Project **knowledge base** panel | Upload as files; see file list below |
| `.gitignore`, git history, GitHub repo | *(no equivalent)* | claude.ai has no version control on knowledge base docs — keep this repo as source of truth, re-upload on change |
| Read tool re-reading files on demand | Knowledge base retrieval | Different retrieval mechanics — see "Retrieval discipline" edit below |
| `~/.claude/projects/.../memory/` (auto-memory files) | Settings → Memory, project-scoped memory | Automatic, not user-authored files — see Memory section below |
| `README.md` | *(not uploaded)* | This is for human GitHub visitors, not for Claude to read — leave it out of the knowledge base |

## Step 1 — Create the Project

1. In claude.ai, go to Projects → **+ New Project**.
2. Name it (e.g. "CAIS — Chief AI Science Officer") and give it a short description.

## Step 2 — Set custom instructions from `CLAUDE.md`

Paste the full contents of `CLAUDE.md` into the Project's instructions field, **with two edits**:

### Edit 1 — "Local reference files" section

The current text asserts CAIS has no knowledge base panel — that's only true in the CLI. Replace:

> CAIS has no claude.ai "knowledge base" panel — its reference material is plain files living
> alongside this CLAUDE.md, read directly from disk rather than searched via a Project's knowledge
> base feature:

with something like:

> CAIS's reference material lives in this Project's knowledge base panel, not inline in these
> instructions:

The three bullet points listing the files stay as-is (the filenames are unchanged).

### Edit 2 — "Retrieval discipline" section

The current text's first sentence ("read only when relevant... not reloaded in full every
session") describes on-demand file reads via the CLI's Read tool — a mechanic that doesn't exist
the same way against a Project's knowledge base, which is available to every chat in the Project
automatically. Replace the opening sentence:

> These local files should be read only when relevant to the task at hand, not reloaded in full
> every session.

with:

> These knowledge base documents are available automatically in every chat in this Project — no
> separate retrieval step needed.

Everything after that sentence (search current documentation before asserting product-capability
claims, don't trust training-data memory) is platform-agnostic and should carry over unchanged —
it's the single most important paragraph in the whole file and has nothing to do with CLI vs.
claude.ai.

## Step 3 — Upload the knowledge base files

Upload these three files as-is (no edits needed to their content):

- `cais-claude-collaboration-conventions.md`
- `cais-claude-product-tracking-process.md`
- `cais-knowledge-base-plan.md`

Do **not** upload `README.md` (written for GitHub visitors, not for Claude) or `.gitignore`.

## Step 4 — Handle the auto-memory files

The CLI accumulates a separate memory store outside this repo
(`~/.claude/projects/.../memory/`, indexed by `MEMORY.md`). claude.ai Projects have their own
memory mechanism (Settings → Memory), but it's **automatic and built from conversations** — there's
no file store to copy over, and a new Project starts with an empty memory space.

Before considering the migration complete:

1. Open `MEMORY.md` in the CLI memory directory and review each entry.
2. For anything that should apply on **every** chat regardless of what Claude has "learned" so
   far (durable rules, not situational context) — fold it into the custom instructions or one of
   the knowledge base docs, the same way the collaboration-conventions doc already captures
   standing working-style rules.
3. For anything more like ambient context that's fine to let claude.ai's memory rebuild
   naturally over the first few conversations — leave it; there's no action needed.

## Step 5 — Keep the two in sync going forward

There is no automatic sync between this git repo and the claude.ai Project. Whenever `CLAUDE.md`
or a reference file changes here:

1. Re-paste the updated `CLAUDE.md` into the Project's custom instructions.
2. Re-upload the changed reference file(s) to the knowledge base (delete the old version first —
   claude.ai doesn't diff/replace-in-place).

Treat this repo as the canonical source; the claude.ai Project is a downstream copy.

## Post-migration checklist

- [ ] Custom instructions field contains the edited `CLAUDE.md` (both edits applied)
- [ ] All three `cais-*.md` reference files (excluding README) are in the knowledge base
- [ ] `README.md` and `.gitignore` are **not** in the knowledge base
- [ ] Reviewed `MEMORY.md` from the CLI's memory store and decided what (if anything) to fold in
- [ ] Ran one test conversation in the new Project checking a product-capability question, to
      confirm it still checks live docs rather than answering from memory
