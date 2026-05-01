# Architecture

## Repo shape

This repo is a **straight tracking fork** of `github.com/openai/codex`. The
codebase is upstream Rust:

- `codex-rs/`         — Rust workspace, the actual CLI (cargo build target)
- `codex-cli/`        — JS thin wrapper around the Rust binary
- `docs/` (upstream)  — upstream documentation
- `BUILD.bazel`       — Bazel build descriptor

## Dappcore overlay

Beyond the upstream tracking, dappcore adds:

- `CLAUDE.md` + `AGENTS.md` + `docs/{index,architecture,development}.md`
  to satisfy dappcore's docs-gaps audit dimension as a paperwork formality
- Conventions for cherry-picking commits between the dappcore fork and
  upstream main

That is the full overlay surface. The Rust source is left untouched.

## Why a fork (not just a dependency)

- We need control over release cadence — upstream's release tempo can
  diverge from dappcore tooling needs
- We need a place to land dappcore-specific patches before (or instead of)
  upstreaming them
- Forge.lthn.ai mirrors the github fork so dappcore's offline build surface
  has access to the source even when github is unreachable
