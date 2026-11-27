# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.1.2](https://github.com/symposium-dev/just-right-rust/compare/v0.1.1...v0.1.2) - 2026-11-27

### Added

- give the rules at session start and check added lines at stop
- add an entry skill with the Rust rules
- add a skill for comments, commits and pull requests
- add a skill for ownership and allocation
- add a skill for simplicity and control flow
- add a skill for tests that can fail
- add a skill for error discipline
- add a skill for modelling domain data with types
- add a skill that tells the agent to run the project's tests
- add issue template for LLM-written Rust feedback

### Fixed

- stop registering the no-op hooks
- rename SYMPOSIUM.toml to Symposium.toml

### Other

- add release-plz workflow
- list the rules skill, the guides and the hooks
- bump version to 0.1.2
- point crate metadata at symposium-dev
