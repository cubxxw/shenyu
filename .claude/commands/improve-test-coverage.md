---
name: improve-test-coverage
description: Workflow command scaffold for improve-test-coverage in shenyu.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /improve-test-coverage

Use this workflow when working on **improve-test-coverage** in `shenyu`.

## Goal

Increase test coverage for specific modules or packages by adding or enhancing test cases.

## Common Files

- `**/src/test/java/**/*.java`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify classes or packages with low or missing test coverage.
- Add new test files or enhance existing test files under the corresponding test directory.
- Commit changes with a message referencing improved test coverage for the targeted area.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.