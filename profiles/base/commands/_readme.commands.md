# Base Commands

Universal commands that work across any tech stack.

## Structure

Commands are organized into two types:

### Callable Commands

Invoke directly via `@CommandName` in chat.

| Command | Purpose |
| ------- | ------- |
| `Review.Thorough` | Full code review with all checklists |
| `Review.Fast` | Quick review for small changes |
| `Review.Security` | Security-focused review |
| `Review.Performance` | Performance-focused review |
| `Scan.DeadCode` | Find unused code |
| `Scan.DuplicateLogic` | Find DRY violations |

### Fragments (prefix `_`)

Reusable pieces that commands reference. Not meant to be called directly.

| Fragment | Contains |
| -------- | -------- |
| `_Base.Context` | Generic context, validation commands |
| `_Context.CodeReview` | Diff-only review scope instruction |
| `_Checklist.Security` | Input validation, injection, authz, sensitive data |
| `_Checklist.Performance` | Database, resources, concurrency, caching |
| `_Output.ReviewFormat` | Standard review output template |
| `_LastStep.Interactive` | Interactive review workflow prompt |

## Composition Pattern

Commands reference fragments via `Apply: _FragmentName`. The LLM loads and applies the fragment content.

Example:

```markdown
### Prerequisites

Apply: `_Base.Context`

### Checklists

Apply all:

- `_Checklist.Security`
- `_Checklist.Performance`
```

## Naming Conventions

- `_` prefix = fragment (composition building block)
- `Review.*` = code review commands
- `Scan.*` = codebase scanning commands

## Extending Base Commands

Stack-specific profiles can:
1. Add their own fragments (e.g., `_Checklist.React`, `_Checklist.Django`)
2. Create stack-specific commands that reference both base and custom fragments
3. Override base commands with stack-specific versions
