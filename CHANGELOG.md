# Changelog

All notable changes to ip-guard will be documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Versioning follows [Semantic Versioning](https://semver.org/).

---

## [1.0.0] — March 2026

### Added
- Three-stage IP compliance workflow: pre-generation, inline flagging, post-generation provenance block
- License target declaration — reads from `package.json`, `LICENSE`, or `CLAUDE.md`, or asks the user
- Dependency intent scan with compatibility status before any code is written
- Inline annotations during generation for OSS-derived patterns, unlisted imports, and patent-adjacent algorithms
- IP Provenance Block appended to every artifact (full and abbreviated fast-mode versions)
- Fast mode toggle for prototyping sessions
- Five hard "never do" rules, including: never create or commit LICENSE/COPYING files without explicit user instruction
- `references/license-compatibility.md` — compatibility matrix covering 12+ license types (MIT, Apache 2.0, BSD, GPL-2/3, AGPL, LGPL, MPL, ISC, CC0) and common asset licenses
- `scripts/license_audit.sh` — post-session dependency audit runner supporting Node.js, Python, Rust, and Go projects
- README with installation instructions, cost vs. benefit breakdown, and limitations
- Apache 2.0 license

### Creator
Mugdha Vairagade ([@mugdhav](https://github.com/mugdhav))
