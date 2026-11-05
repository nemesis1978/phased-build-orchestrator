# Changelog

All notable changes to this project are documented in this file.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).
The version in `SKILL.md` is the authoritative one.

## [Unreleased]

## [1.0.3] - 2026-11-05

### Added

- **Fase 0 — Stato del progetto**: prima di qualsiasi fase, tre comandi e uno stato dichiarato con le sue evidenze (vuoto / idea / scaffold / in corso / rotto). Se esiste `docs/HANDOFF.md`, si legge prima di ogni altra cosa.
- Regola esplicita: chiedere conferma solo quando le evidenze si contraddicono, mai quando un comando può rispondere.
- Il diagramma del flusso ora parte da STATO, non da DISCOVERY.
- Validatore: controlla la presenza della Fase 0.

## [1.0.2] - 2026-11-05

### Fixed

- `SKILL.md`: the `description` was unquoted and contained `": "`, which makes the YAML frontmatter unparseable by a strict parser — the skill would not load on hosts that validate the frontmatter. Quoted it. Found by `skill-doctor` against five real hosts.

## [1.0.1] - 2026-11-05

### Added

- `references/execution.md`: any addition beyond the planned scope must be recorded in the checkpoint with its reason; if it changes the value or the criteria of the phase, stop and ask.
- Gate `PASS` gains a fifth condition: no undeclared scope.
- `SKILL.md`: the checkpoint format gains a `### Scope` block, so scope drift becomes visible instead of implicit.

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

[Unreleased]: https://github.com/nemesis1978/phased-build-orchestrator/compare/v1.0.3...HEAD
[1.0.3]: https://github.com/nemesis1978/phased-build-orchestrator/compare/v1.0.2...v1.0.3
[1.0.2]: https://github.com/nemesis1978/phased-build-orchestrator/compare/v1.0.1...v1.0.2
[1.0.1]: https://github.com/nemesis1978/phased-build-orchestrator/compare/v1.0.0...v1.0.1
[1.0.0]: https://github.com/nemesis1978/phased-build-orchestrator/releases/tag/v1.0.0
