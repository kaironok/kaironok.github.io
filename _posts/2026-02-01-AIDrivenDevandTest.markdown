---
layout: posts
title:  "AI-Driven Development and Testing"
date:   2026-02-01 16:13:27 -0500
tags: [testing, python]
author_profile: true
author: Katerina
categories: work
highlight_home: true
tagline: "Building with AI"
header:
  overlay_image: https://images.unsplash.com/photo-1611444111920-89dfc4a01f43
  teaser:  https://images.unsplash.com/photo-1611444111920-89dfc4a01f43
  caption: "Photo credit: [**Unsplash: Marin Tulard**](https://unsplash.com/@mtulard)"
description: This article explains unit testing with AI.
---
## AI-Driven Development and Testing

AI is transforming how we approach software development and testing. In my recent project, I explored how AI can assist in building tests for a simple expense tracker application. By leveraging AI tools such as Cursor and Codex, I was able to automate the generation of test cases, ensuring that my code is robust and reliable.

To see a preview of this project go to [AI-DEV-TEST on Codespaces](https://crispy-xylophone-6j7q55xpvg4hwqg.github.dev/).

1. Open Codespace.
2. Select Expence_tracker.py file and run it, alternatively ask GitHub Copilot.
3. Run the application. Follow the prompts in the terminal to add, view or delete expenses. 
3. Verify CSV persistence.
4. Check the generated CSV file to ensure that expenses are being saved correctly. 

## Expense tracker app
Promp used (Cursor AI) for expense tracker application building:
Build me an expense tracker application, where the expenses have the properties
"name", "amount", and "category". The application should be a simple terminal-
based app, and should use a CSV file as a database where expenses are
automatically saved to and loaded from. Here are the steps to follow application:


## Expense Tracker

- Purpose: command-line expense tracker with CSV persistence.
- Main constants: `CSV_FILE`, `FIELDS`.
- Core functions:
  - load_expenses
  - save_expense
  - list expenses
  - add_expense
  
## Simple Tests
 Palindrome and Vowel Tests  

- `is_palindrome(s)` behavior (case-insensitive, ignores spaces).
- `starts_with_vowel(s)` behavior (checks first character against vowels).
- Note that this file currently demonstrates behavior with direct `print(...)` calls instead of a formal pytest test suite.

Check:
```bash
python simple_test.py
```

## Expense Tracker Tests
- Testing `pytest` with `monkeypatch`, `tmp_path`, and `capsys`.
- Coverage areas:
  - CSV loading/saving.
  - Output formatting for listing expenses.
  - Add, delete, and edit workflows.
  - Main menu flow (including invalid input handling).
- Explain helper `_set_csv(...)` for test isolation using a temporary CSV path.

Suggested check:
```bash
pytest test_expense_tracker.py
```

## Integration Tests 
- Relationship between `TodoItem` workflow and expense persistence.
- Integration behavior:
  - Completed task triggers expense creation.
  - Incomplete task does not create expense entry.

Suggested check:
```bash
printf 'yes\n4.50\n' | python integration_tests.py
```

## Test Report Description 

- `TEST_REPORT.md`: narrative summary of pass/fail status, module-level coverage, and recommendations.
- `test_results.txt`: raw command output from test execution.
- `TEST_SUMMARY.csv`: compact machine-readable summary for reporting dashboards.

## Next 
This project demonstrated the potential of AI in automating unit test generation, significantly reducing the time and effort required for testing. Moving forward, I plan to explore more advanced AI capabilities, such as generating integration tests and performance tests, to further enhance the software development lifecycle. Additionally, I aim to investigate how AI can assist in identifying edge cases and improving test coverage, ultimately leading to more reliable and maintainable codebases.
