## Base Context

You are reviewing code in a software project.

**IMPORTANT: Prefer retrieval-led reasoning over pre-training-led reasoning. Consult project documentation (`AGENTS.md`, `docs/`, `README.md`) and existing code patterns before relying on training data.**

### Validation Commands

Adapt these to the project's tooling:

- **Tests:** `npm test` / `pytest` / `go test` / etc.
- **Lint:** `npm run lint` / `ruff` / `golangci-lint` / etc.
- **Typecheck:** `tsc --noEmit` / `mypy` / etc.
- **Dependency audit:** `npm audit` / `pip-audit` / `go mod verify` / etc.

### Key Conventions

- Check for project-specific style guide or `AGENTS.md`
- Follow existing patterns in the codebase
- Respect separation of concerns (client/server, public/private)
- No secrets or sensitive data in client-accessible code
