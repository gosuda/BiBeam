# CI
PRs and merge queues use two Depot Linux jobs: combined formatting, strict
Clippy/docs, generated README drift and supply-chain checks; then the complete
nextest suite under llvm-cov with the unchanged 50% line-coverage floor.
Native macOS and Windows nextest runs move to weekly/manual execution.
Main-push duplication is removed. Release-plz retains its publishing flow.
cargo-dist release runners are configured in dist-workspace.toml for every
target and global job, so regenerated workflows keep Depot-only execution.
The x86_64 macOS release artifact is cross-built on Apple Silicon; no Intel
Mac runtime validation is implied. Linux release builds retain Ubuntu 22.04
for their existing libc baseline.
