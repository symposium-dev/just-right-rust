---
name: run-rust-tests
description: Run the project's tests to verify a Rust change. Use whenever you finish, verify, or report on a change to Rust code, before saying the work is done or that it passes.
---

# Run the tests

Run the project's tests before saying a Rust change is done. Code that compiles is not code that works, and only the test output tells them apart.

## Find how this project runs its tests

Do not assume `cargo test`. Many projects need a specific runner, feature set, or setup, and a bare `cargo test` can skip most of the suite or fail for unrelated reasons. Look for:

- documented commands in `README`, `CONTRIBUTING`, `AGENTS.md`, or `CLAUDE.md`;
- a `justfile` or `Makefile` with a test recipe;
- `cargo nextest` configuration (`.config/nextest.toml`);
- the workspace layout and feature flags: whether tests need `--workspace`, `--all-features`, or a specific feature set;
- the CI workflow, which shows the commands the project itself trusts.

Use the command the project uses. Fall back to `cargo test` only when nothing else is specified.

## Run narrow, then full

- While iterating, run the tests closest to the change: one test, one module, or one package (`cargo test -p <crate> <filter>`).
- Before saying the work is done, run the full suite the way CI does.
- Rerun after every later edit. An earlier pass says nothing about the current code.

## Report what happened

- Report failures with their output. Never claim success the output does not show.
- If a failure predates your change, say so and show how you know.
- If the tests could not be run (missing toolchain, network, services, time), say so plainly and name what was not verified.

## Never weaken a test to get green

- Do not delete a failing test, mark it `#[ignore]`, or loosen its assertions to make it pass.
- Fix the code. Change a test only when the test itself is wrong or the intended behavior changed, and say that you did.
