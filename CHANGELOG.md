# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] — 2026-03-15

### Added
- `/learn` command: full 6-stage Socratic tutoring session for any codebase
  - Stage 1: What problem does this project solve?
  - Stage 2: High-level architecture and folder structure
  - Stage 3: Core concepts and patterns used
  - Stage 4: Key files and their responsibilities
  - Stage 5: Data flow end to end
  - Stage 6: How to extend or modify the project
- `/learn-topic [topic]` command: focused deep-dive into any specific concept
  - 5-layer teaching structure (why → what → how → where it fits → pitfalls)
  - Optional hands-on practical exercise at the end
- Session commands: `skip`, `hint`, `back`, `summary`, `exit`, `related`
- Plugin metadata in `.claude-plugin/plugin.json`
- MIT License
- Full README with installation instructions and usage examples
