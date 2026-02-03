## Scan for Duplicate Logic (DRY Violations)

### Prerequisites
Apply: `_Base.Context`

Scan for repeated logic patterns that could be consolidated into shared utilities.

## Duplication Criteria

- **Exact**: 90%+ identical (excluding variable names) — Always consolidate
- **Similar**: 60-90% identical structure, different data/fields — Usually consolidate
- **Pattern**: Same shape/flow, different domain — Consider shared abstraction

## Priority: Unused Existing Utilities

**SCAN THIS FIRST** — Higher value than finding new duplicates.

Look for places that should use existing consolidated utilities but don't:
1. Check `/lib`, `/utils`, `/helpers` for existing utilities
2. Search for inline implementations that duplicate these utilities
3. These are quick wins with zero abstraction design needed

## Scanning Strategy (ordered by typical yield)

### 1. Validation Logic
- Similar validation patterns across different validators
- Repeated regex patterns or validation rules
- Validation logic duplicated across files

### 2. Data Fetching / API Calls
- Similar fetch/request patterns
- Repeated error handling around data fetching
- Duplicate response transformation logic

### 3. Error Handling
- Similar try/catch patterns
- Repeated error message formatting
- Duplicated error logging patterns

### 4. Similar Function Implementations
- Functions with similar names/patterns (`validate*`, `format*`, `parse*`, `handle*`)
- Function bodies with similar logic flows (>10 lines)
- Functions that differ only by parameters or data types

### 5. Type Definitions
- Similar interfaces/types/schemas
- Types that could be generic or shared
- Repeated type patterns with minor variations

## Classification

**Highest Priority: Missed Utility Usage** — Existing utility available but not used
**High Priority Consolidation** — Exact or near-exact duplicates
**Medium Priority Consolidation** — Similar patterns with minor variations
**Low Priority Consolidation** — Similar but contextually different
**Pattern Opportunity** — Repeated patterns that could use a shared abstraction

## Output Format

## Summary
<count of items by category>

## Missed Utility Usage (Quick Wins)
- [ ] `path/file:L42` — Inline implementation → Use existing `utilityName()` from `path/to/util`

## High Priority Consolidation
- [ ] `path/file1:function1` + `path/file2:function2` — <description> — Extract to shared utility

## Medium Priority Consolidation
- [ ] `path/file1` + `path/file2` — <description> — Consider shared utility with parameters

## Pattern Opportunities
- [ ] `<pattern description>` — Found in N locations — Consider creating shared abstraction

## Recommended Actions
<prioritized consolidation tasks>

## Last Step
Ask if I would like to: 1) Extract all high-priority duplicates, 2) Review each item one by one, 3) Start with a specific category
