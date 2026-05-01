# CLAUDE.md — core-agent-ide

This repo is dappcore's **fork-and-rebrand** of OpenAI's Codex CLI
(github.com/openai/codex). The upstream is a Rust codebase implementing
the codex-as-IDE-companion runtime; we maintain a downstream tracking the
upstream main with light dappcore overlays.

## What this is NOT

- **Not a dappco.re/go module.** No go.mod, no /go/ subtree, no v0.9.0
  contract migration applies. The Go audit (`audit.sh`) reports `docs-gaps`
  as a paperwork formality only — there is no Go code to lint.
- **Not in the active sweep queue.** Mantis #1279 was auto-created during
  the org-wide v0.9.0 sweep. The remediation here is documentation-only:
  add the dappcore-required four docs files explaining the fork
  relationship, then leave the Rust source untouched.

## Where the work happens

- **Upstream tracking**: `git remote add upstream https://github.com/openai/codex.git`
  pulls upstream main; we cherry-pick or rebase as needed.
- **Dappcore overlay**: any dappcore-specific changes live as commits on
  `dev` in this repo, ready to PR upstream where appropriate.
- **Forge**: lives on github (no homelab fork yet — the codex CLI is large
  and sits adjacent to the dappcore sweep, not inside it).

See `docs/index.md`, `docs/architecture.md`, `docs/development.md` for
more on the fork-overlay shape.
