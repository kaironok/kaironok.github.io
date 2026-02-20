---
layout: posts
title:  "AI-Driven Development and Testing"
date:   2026-02-01 16:13:27 -0500
tags: [testing, python]
author_profile: true
author: Katerina
categories: AI
highlight_home: true
tagline: "Building with AI"
header:
  overlay_image: https://images.unsplash.com/photo-1611444111920-89dfc4a01f43
  teaser:  https://images.unsplash.com/photo-1611444111920-89dfc4a01f43
  caption: "Photo credit: [**Unsplash: Marin Tulard**](https://unsplash.com/@mtulard)"
description: This article is about development and testing with AI.
---
## AI-Driven Development and Testing

This repository demonstrates a command-line Expense Tracker application with comprehensive testing and CI/CD automation.

**Key Features:**

- Full CRUD operations for expense tracking
- CSV-based data persistence
- 15 comprehensive unit tests
- Automated CI/CD with GitHub Actions
- JUnit test reporting and dashboards
- Flake8 linting for code quality
- Integration tests for cross-module workflows

> [AI-DEV-TEST]( https://github.com/kaironok/AI-DEV-TEST/)
> [AI-DEV-TEST-Delivery](https://github.com/kaironok/AI-DEV-TEST-Delivery/)

### Development Goals

Build and evolve a small command-line Expense Tracker while practicing clean Python structure, maintainable CRUD workflows and practical testability.

- Keep the core app simple, readable and beginner-friendly.
- Preserve CSV-based persistence behavior.
- Make updates safe by documenting expected behavior before/alongside code changes.
- Encourage small, incremental improvements with quick validation.

### Testing Goals

Test to prove that core user flows (add/list/edit/delete expenses) stay reliable as code changes.

- Catch regressions in file handling, menu flow, and user input behavior.
- Validate both isolated logic (unit tests) and realistic behavior across modules (integration tests).
- Keep test outputs understandable.

### Extended Testing Goals

Use these as the “further” testing targets for ongoing quality:

- **Correctness goal:** 100% pass rate on required local checks before merge.
- **Coverage goal:** maintain tests for all existing CRUD paths and key error paths (missing files, empty data, invalid selections).
- **Stability goal:** tests should be deterministic and not depend on shared mutable state.
- **Isolation goal:** unit tests must use temporary files/mocking where appropriate to avoid side effects.
- **Integration goal:** verify at least one end-to-end scenario where external input causes expected persistence changes.
- **Reporting goal:** keep `TEST_REPORT.md`, `test_results.txt`, and `TEST_SUMMARY.csv` synchronized with current test outcomes.

---

## Expense Tracker (`Expense_tracker.py`)

- Purpose: command-line expense tracker with CSV persistence.
- Main constants: `CSV_FILE`, `FIELDS`.
- Core functions:
  - `load_expenses()` for reading CSV data (supports header and no-header files).
  - `save_expense(expense)` for appending records and writing header once.
  - `list_expenses(expenses)` for terminal table output.
  - `add_expense()`, `delete_expense()`, `edit_expense()` for CRUD workflows.
  - `main()` for interactive menu loop.
- Expected behavior for empty files, missing files, non-existent edit/delete targets, and invalid menu choices.

### Simple Tests - assume there are such business requirements

- `is_palindrome(s)` behavior (case-insensitive, ignores spaces).
- `starts_with_vowel(s)` behavior (checks first character against vowels).
- Note that this file currently demonstrates behavior with direct `print(...)` calls instead of a formal pytest test suite.

### Expense Tracker Tests

- Test framework: `pytest` with `monkeypatch`, `tmp_path`, and `capsys`.
- Coverage areas:
  - CSV loading/saving.
  - Output formatting for listing expenses.
  - Add, delete, and edit workflows.
  - Main menu flow (including invalid input handling).
- Explain helper `_set_csv(...)` for test isolation using a temporary CSV path.

### Integration Tests

- Relationship between `Todo-Item` workflow and expense persistence.
- Integration behavior:
  - Completed task can trigger expense creation.
  - Incomplete task does not create expense entry.
- Mention that this script is interactive and requests user input during execution.

### CI/CD Workflows

GitHub Actions workflows for continuous integration and deployment.

### Integration Workflow

**Name:** `Python application`

**Purpose:** Main integration workflow that runs on every push and pull request to the main branch.

**Triggers:**

- Push to `main` branch
- Pull requests targeting `main` branch

**Jobs:**

- **Linting with flake8:**
  - Checks for syntax errors and undefined names
  - Additional checks with warnings for complexity and line length
- **Testing with pytest:**
  - Runs all tests with verbose output
  - Generates JUnit XML report
- **Test Report Publishing:**
  - Uses `mikepenz/action-junit-report@v3` action
  - Creates detailed test summary dashboard in GitHub Actions
  - Shows both passed and failed tests
  - Runs even if tests fail

**Permissions:**

- `contents: read` - Read repository contents
- `checks: write` - Write test results

### Reusable Workflow

**Name:** `Python CI/CD Reusable Workflow`

**Purpose:** Reusable workflow that can be called from other workflows via `workflow_call` trigger.

**Triggers:**

- `workflow_call` - Can be invoked by other workflows

**Jobs:**

- **Linting with flake8:** Same as integration workflow
- **Testing with pytest:** Runs all tests

**Usage Example:**
Other workflows can call this reusable workflow using:

```yaml

jobs:
  integration:
    uses: ./.github/workflows/python-CICD.yml
```

### Test Report Description

- `TEST_REPORT.md`: narrative summary of pass/fail status, module-level coverage, and recommendations.
- `test_results.txt`: raw command output from test execution.
- `TEST_SUMMARY.csv`: compact machine-readable summary for reporting dashboards.
- Guidance: regenerate these artifacts after any meaningful code/test update to keep documentation accurate.

---

## Next

 Moving forward, I plan to explore more AI capabilities to further enhance the software development lifecycle. I plan to add soon new cases for creating an AI-powered agile tool and API design. Stay tuned for updates!
