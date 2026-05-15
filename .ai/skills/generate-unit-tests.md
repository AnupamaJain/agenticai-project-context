---
name: generate-unit-tests
description: Automatically generate a comprehensive test suite for a specific module.
argument-hint: "[file-path]"
---

# Skill: Generate Unit Tests

## Goal
Ensure a specific module has 100% logic coverage with deterministic tests.

## Steps
1. **Analysis**: Read the target file and identify all exported functions/methods.
2. **Scaffolding**: Create a matching test file (e.g., `test_[original].py` or `[original].test.ts`).
3. **Mocks**: Set up mocks for any external dependencies (DB, APIs).
4. **Test Cases**:
    - Happy path (standard usage)
    - Edge cases (null, empty, extreme values)
    - Error cases (invalid input, service failure)
5. **Execution**: Run the generated tests and fix any issues discovered.

## Quality Rule
Refer to `.ai/rules/80-testing-quality.md` for mocking standards.
