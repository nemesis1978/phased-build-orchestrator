# Changelog

All notable changes to this project are documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).
The version in `SKILL.md` is the authoritative one.

## [Unreleased]

## [1.0.0] - 2026-11-04

### Added

- Initial release. An orchestrator skill for phased software development: discovery → spec → build phases → gated execution → handoff.
- Eight non-negotiable principles, including "never invent tests, results, commits, links, or available tools".
- Four gate states with explicit semantics: `PASS`, `FAILED`, `BLOCKED`, `NOT RUN`. A test that could not be executed is `NOT RUN`, never `PASS`.
- Seven phases (A–G) documented in eight reference files, loaded on demand.
- Templates for `SPEC.md`, `BUILD_PHASES.md` (`BP-00X` schema), `PROJECT_STATE.md`, and `HANDOFF.md`.
- `references/integrations.md`: mapped third-party skills (Matt Pocock's `wayfinder`, `to-spec`, `to-tickets`, `tdd`, `handoff`) with verified repository paths, plus the explicit rule not to assume they are installed.
- `scripts/validate-skill.sh`: executable format contract — name/directory match, referenced and orphaned files, absolute paths, all four gate states documented, `SKILL.md` length, obvious secrets, changelog section.
- Compatibility note explaining how the skill delegates to `handoff`, `wayfinder`, `plan`, and `groundwork` instead of duplicating them.

[Unreleased]: https://github.com/nemesis1978/phased-build-orchestrator/compare/v1.0.0...HEAD
[1.0.0]: https://github.com/nemesis1978/phased-build-orchestrator/releases/tag/v1.0.0
