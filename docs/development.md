# Development

## Building

The codex CLI is a Rust workspace. From this repo's root:

```bash
cd codex-rs
cargo build --release
```

The binary lands at `codex-rs/target/release/codex`.

## Sync from upstream

```bash
git remote add upstream https://github.com/openai/codex.git    # one-time
git fetch upstream
git checkout dev
git merge upstream/main                                          # or rebase
git push origin dev
```

## Contribute back

For dappcore patches that should go upstream:

```bash
git checkout -b patch/<short-name> upstream/main
# cherry-pick the dappcore commits
gh pr create --repo openai/codex --base main --head patch/<short-name> --title "..."
```

## Audit

The dappco.re Go audit (`audit.sh`) flags this repo's `docs-gaps`
dimension only — there is no Go code here. Once `CLAUDE.md`, `AGENTS.md`,
`README.md`, and `docs/{index,architecture,development}.md` exist, the
audit reports `verdict: COMPLIANT`. No further v0.9.0 contract work
applies.
