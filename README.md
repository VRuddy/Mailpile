# Mailpile

Mailpile is an open source, privacy-focused e-mail client with search, tagging and encryption support.

## Project status (2026 reboot)

This repository now targets a **community reboot** to make Mailpile usable again on modern systems in 2026.

- ✅ Legacy code and history are preserved in this repository.
- 🔧 Porting and modernization work is in progress.
- 📍 The migration plan is tracked in [`ROADMAP_2026.md`](./ROADMAP_2026.md).

If you need immediate access to legacy data today, use the maintained v1 Docker images:
[mailpile/Mailpile-v1-Docker](https://github.com/mailpile/Mailpile-v1-Docker).

## Why this reboot?

The original codebase delivered innovative privacy and UX ideas, but large parts of the stack are now outdated.
The 2026 effort focuses on:

- compatibility with current Python, OS, browser and mail ecosystems,
- safer defaults and modern security practices,
- a maintainable contributor workflow (tests, CI, packaging, documentation),
- progressive delivery so users can adopt improvements step by step.

## Current priorities

1. Stabilize development environment and reproducible builds.
2. Audit and refresh dependencies.
3. Re-establish automated testing and CI gates.
4. Port critical runtime paths to modern Python compatibility.
5. Deliver a usable beta for real-world validation.

For detailed milestones, deliverables and success criteria, see [`ROADMAP_2026.md`](./ROADMAP_2026.md).

## Contributing

Contributions are welcome.

- Start with [`CONTRIBUTING.md`](./CONTRIBUTING.md)
- Review developer notes in [`DEV_FAQ.md`](./DEV_FAQ.md)
- Open issues for blockers discovered during porting work

When proposing changes, prefer small focused pull requests tied to a roadmap milestone.

## Credits and license

Mailpile was created by Bjarni R. Einarsson, with major contributions from Brennan Novak, Smári McCarthy, and many others.

This project is free software, licensed under the GNU Affero General Public License.
See [`COPYING.md`](./COPYING.md) for details.
