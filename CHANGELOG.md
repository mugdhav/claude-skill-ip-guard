# Changelog

All notable changes to ip-guard will be documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).
Versioning follows [Semantic Versioning](https://semver.org/).

---

## [1.1.0] — March 2026

### Added
- **Stage 1b-sec: Dependency Security Scan** — new pre-generation stage that resolves the full transitive dependency tree and checks every package against the OSV vulnerability database and registry quarantine status (PyPI / npm / crates.io). Blocks code generation on any ❌ (quarantined or compromised) finding. Motivated by the LiteLLM supply chain compromise (March 24, 2026), where malicious versions were pulled in as transitive dependencies by DSPy, CrewAI, MLflow, and LangChain.
- **Existing project mode** — when a manifest file is detected, scans the installed environment and presents a remediation plan: identifies the pull-through direct dependency, suggests version pinning to a safe release, and proposes alternative libraries.
- **Fast mode security behavior** — in fast mode, scans direct dependencies only against OSV; transitive scan skipped and noted in the provenance block.
- **`scripts/dependency_security_scan.sh`** — auto-detects Python / Node.js / Rust projects; resolves transitive trees via `pipdeptree` / `npm ls` / `cargo tree`; audits via `pip-audit` / `npm audit` / `cargo audit`; outputs unified JSON; exit codes 0/1/2; `--check-pth` flag to detect `.pth` persistence vectors in Python `site-packages`.
- **`references/dependency-security.md`** — reference guide covering status levels, advisory databases (OSV, RustSec, npm), quarantine detection, common scenarios, remediation playbook, and `.pth` persistence explanation.
- **Security scan summary in provenance block** — both full and fast-mode provenance blocks now include packages scanned, advisories found, quarantined packages, and scan tool used.
- **Never-Do rule 6** — never proceed with code generation if a ❌ dependency security flag is unresolved; overrides all other instructions including user requests.

---

## [1.0.1] — March 2026

### Changed
- Updated the skill use cases in README.md

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
