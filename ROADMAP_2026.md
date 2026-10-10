# Mailpile Roadmap 2026

This roadmap defines a practical modernization path to make Mailpile usable and maintainable in 2026.

## Objectives

- Restore reliable day-to-day usability on modern platforms.
- Reduce technical risk by stabilizing dependencies and runtime behavior.
- Rebuild confidence with automated quality and security checks.
- Enable contributors to ship incremental improvements safely.

## Guiding principles

1. **Ship in slices**: prioritize small, testable increments over long rewrites.
2. **Preserve user data**: no migration step should risk mailbox/index integrity.
3. **Security first**: treat dependency hygiene, crypto correctness and secret handling as release blockers.
4. **Operational clarity**: every milestone needs explicit acceptance criteria.

## Workstreams

### A) Platform and runtime modernization

- Audit Python/runtime compatibility gaps.
- Remove deprecated APIs and legacy assumptions.
- Standardize local setup for Linux/macOS/Windows (where feasible).
- Define a supported-version policy and deprecation window.

### B) Dependency and supply-chain hardening

- Inventory direct and transitive dependencies.
- Replace or pin vulnerable/unmaintained components.
- Add reproducible dependency installation guidance.
- Document upgrade strategy and ownership per dependency area.

### C) Test and CI rehabilitation

- Restore fast local smoke tests for core flows.
- Re-enable CI checks with deterministic outcomes.
- Add regression coverage around indexing, search, tagging and encryption-sensitive paths.
- Gate merges on core test + lint + security checks.

### D) UX and product viability

- Confirm critical user journeys: first run, account setup, indexing, search, compose/send, decrypt/verify.
- Fix high-impact breakages and obvious UX blockers.
- Improve error diagnostics to make bug reports actionable.
- Track usability debt separately from infra debt.

### E) Packaging and release operations

- Rebuild release process (tagging, artifacts, changelog discipline).
- Validate Docker/devcontainer and local install parity.
- Define release channels: alpha, beta, stable.
- Prepare rollback and known-issues process for early releases.

### F) Documentation and contributor experience

- Rewrite top-level docs for current setup reality.
- Add architecture notes for critical subsystems.
- Document triage policy and roadmap labels.
- Maintain a living migration log for major compatibility decisions.

## Milestones

## M0 — Baseline recovery (Weeks 1-4)

**Goal:** Make the project buildable and diagnosable again.

Deliverables:
- Clean setup instructions that work from scratch.
- Dependency inventory with risk classification.
- Initial CI workflow producing clear pass/fail signals.
- Known issues register opened and prioritized.

Exit criteria:
- New contributor can run the app in dev mode using documented steps.
- CI executes at least lint + smoke tests on default branch.

## M1 — Core functionality stabilization (Weeks 5-10)

**Goal:** Recover reliability of core mail workflows.

Deliverables:
- Fixes for top-priority runtime and compatibility bugs.
- Regression tests for indexing/search/tagging basics.
- Improved error handling in critical paths.

Exit criteria:
- Core workflows complete without critical errors on supported environments.
- Test coverage includes high-risk legacy modules touched during fixes.

## M2 — Security and maintainability uplift (Weeks 11-16)

**Goal:** Reduce long-term risk and raise merge quality.

Deliverables:
- Vulnerable dependencies remediated or isolated.
- Security checks integrated into CI.
- Contributor standards documented (branching, review, release notes).

Exit criteria:
- No known high-severity dependency vulnerabilities in supported path.
- Every PR passes mandatory quality gates.

## M3 — Public beta readiness (Weeks 17-24)

**Goal:** Publish a beta usable by early adopters.

Deliverables:
- Beta release checklist and signed release notes.
- Migration guidance for legacy users.
- Issue triage SLA and beta feedback loop.

Exit criteria:
- Beta artifacts available with reproducible install path.
- Early adopters can complete primary workflows with documented limitations.

## M4 — Stable release candidate (Post-beta)

**Goal:** Prepare stable 2026 release with confidence.

Deliverables:
- Final blocker burn-down.
- Documentation freeze for release branch.
- Support and maintenance plan for next cycle.

Exit criteria:
- Release criteria met across functionality, reliability and security.
- Post-release ownership and roadmap for 2027 defined.

## Tracking model

Use labels/milestones consistently:

- `roadmap:M0` ... `roadmap:M4`
- `type:bug`, `type:security`, `type:tech-debt`, `type:docs`
- `priority:P0` ... `priority:P3`
- `status:blocked`, `status:needs-repro`, `status:ready`

Suggested issue fields:
- Impacted user flow
- Regression risk
- Test evidence
- Security impact
- Docs required

## Definition of done (cross-milestone)

A roadmap task is done when:

1. Implementation is merged.
2. Tests/validation are updated and passing.
3. User/developer documentation is updated.
4. Security implications are reviewed.
5. Follow-up debt is captured as explicit issues.

## Risks and mitigations

- **Legacy complexity** → isolate risky modules and add tests before refactors.
- **Maintainer bandwidth** → enforce small PR scope and milestone discipline.
- **Dependency churn** → pin versions + schedule regular upgrade windows.
- **Hidden data edge cases** → test against representative legacy datasets.

## First backlog candidates

1. Reproduce current startup path on modern Python and document blockers.
2. Re-enable one deterministic smoke test in CI.
3. Remove or replace one high-risk deprecated dependency.
4. Verify mailbox indexing round-trip on sample data.
5. Document architecture of search/index pipeline.
