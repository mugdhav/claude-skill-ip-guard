# Contributing to ip-guard

Thank you for your interest in improving ip-guard. Contributions are welcome and credited.

## What's welcome

- Additions or corrections to the license compatibility matrix (`references/license-compatibility.md`)
- Support for additional package managers in `scripts/license_audit.sh` (Ruby, PHP, .NET, etc.)
- Bug fixes and edge case handling in the SKILL.md logic
- Improvements to the provenance block format
- Real-world examples that improve triggering accuracy

## What to do

1. Fork the repository
2. Create a branch: `git checkout -b your-feature-name`
3. Make your change
4. Open a pull request with a clear description of what changed and why

## What to keep in mind

- Do not modify the `name` or `description` fields in `SKILL.md` frontmatter without opening a discussion first — these control how and when the skill triggers
- Keep SKILL.md under 500 lines (progressive disclosure architecture)
- The compatibility matrix provides guidance, not legal advice — keep that disclaimer intact
- All contributions fall under the Apache 2.0 license
- Credit for contributions will be noted in `CHANGELOG.md`

## Questions

Open an issue. No question is too small.

---

*ip-guard is created and maintained by [Mugdha Vairagade](https://github.com/mugdhav).*
