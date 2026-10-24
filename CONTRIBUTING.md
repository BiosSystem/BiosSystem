# Contributing to BiosSystem

Thank you for contributing to BiosSystem. To maintain high code quality and clean git history across the BiosSystem ecosystem, all contributors must adhere to these guidelines.

---

## Commit Guidelines

### 1. Plain Imperative Messages
- Write commit subjects as concise, direct English imperatives describing what changed and why.

**Examples:**
- `Add cash-out feature to bet slip`
- `Fix odds conversion for fractional display`
- `Update telemetry data schema and verify pipeline`

### 2. Author Identity
Every commit must be authored by `BiosSystem` with email `63607038+BiosSystem@users.noreply.github.com`.

---

## Code Quality & Verification

Before staging or committing any changes:
1. Run local test suites and verify 100 percent pass rate.
2. Run linters and type checkers (`npm run lint`, `tsc --noEmit`, `flake8`, `mypy`).
3. Ensure zero plaintext credentials, private IP addresses, or internal tokens exist in the codebase.
