## Scan for Dead Code

### Prerequisites
Apply: `_Base.Context`

Scan for unused or dead logic that can be safely removed.

## Scanning Strategy

### 1. Exports & Public APIs
- Search for imports of each exported function/class/constant
- Check for unused exports
- Verify re-exports are actually used downstream

### 2. Internal Functions
- Search for calls to internal/private functions
- Check for functions only called by other dead code

### 3. Types & Interfaces
- Search for usage of exported types
- Check for types only used by dead code

### 4. Dependencies
- Cross-reference packages with actual imports
- Flag packages only used by dead code
- Check for dev dependencies used in production code

### 5. Configuration & Assets
- Check for unused config files
- Flag orphaned assets (images, fonts, etc.)
- Identify unused environment variables

## Classification

**Definite Dead Code** — Zero references, safe to delete
**Legacy/Duplicated Code** — Superseded or redundant
**Questionable** — Needs verification (dynamic usage, test-only, feature flags)

## Output Format

## Summary
<count of items by category>

## Definite Dead Code
- [ ] `path/file` — <reason> — Safe to delete

## Legacy/Duplicated Code
- [ ] `path/file:functionName` — <what it duplicates> — Consider removing

## Questionable
- [ ] `path/file` — <concern> — Needs verification

## Dependencies to Remove
- [ ] `package-name` — Only used by dead code

## Recommended Actions
<prioritized cleanup tasks>

## Last Step
Ask if I would like to: 1) Remove all definite dead code, 2) Review each item one by one, 3) Start with a specific category
