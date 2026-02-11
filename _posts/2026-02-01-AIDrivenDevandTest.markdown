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
description: This article is about development and testing with AI.
---
## AI-Driven Development and Testing

In this project I explored how AI can assist building and testing simple expense tracker application by leveraging AI tools such as Cursor AI and OpenAI Codex.

To see a preview of this project go to [AI-DEV-TEST on Codespaces](https://crispy-xylophone-6j7q55xpvg4hwqg.github.dev/).

## Expense tracker application 
The application is a simple terminal-based expense tracker that uses a CSV file as a database. The expenses have properties such as "name", "amount", and "category". The application allows users to add, view and delete expenses with all the data being automatically saved to and loaded from the CSV file.

Promp (Cursor AI): 
"Build me an expense tracker application, where the expenses have the properties
"name", "amount" and "category". The application should be a simple terminal-
based app, and should use a CSV file as a database where expenses are
automatically saved to and loaded from." 

## Steps

1. Open Codespace.
2. Run expence_tracker.py file or alternatively ask GitHub Copilot.
3. Follow the prompts in the terminal to list, add, delete or edit expenses. 
3. Verify CSV persistence.

![Command line](/assets/images/Extr.jpeg)


## Expense Tracker

- Purpose: command-line expense tracker with CSV persistence.
- Core features:
  - list expenses
  - add expenses
  - delete expenses
  - edit expenses
  - exit
  
## Simple Test
 Random Palindrome and Vowel Tests are for demo purposes. Coming soon: relevant update to expense tracker tests. 

- `is_palindrome(s)` behavior (case-insensitive, ignores spaces).
- `starts_with_vowel(s)` behavior (checks first character against vowels).
- Note that this file currently demonstrates behavior with direct `print(...)` calls instead of a formal pytest test suite.

Suggested check:
```bash
python simple_test.py
```

## Expense Tracker Tests
- Testing `pytest` with `monkeypatch`, `tmp_path`, and `capsys`.
- Core feautures tested:
  - CSV loading/saving.
  - Output formatting for listing expenses.
  - Add, delete and edit expenses.
  - Main features (including invalid input handling).
- Explain helper `_set_csv(...)` for test isolation using a temporary CSV path.

Suggested check:
```bash
pytest test_expense_tracker.py
```

## Integration Tests 
- Relationship between `To-do Item` workflow and expense persistence.
- Integration behavior:
  - Completed task triggers expense creation.
  - Incomplete task does not create expense entry.

Suggested check:
```bash
python integration_tests.py
```

## Test Report Description 

- `TEST_REPORT.md`: human-readable summary of test results, including pass/fail status and key insights.
- `test_results.txt`: raw output from test runs, useful for debugging and detailed analysis.
- `TEST_SUMMARY.csv`: compact machine-readable summary for reporting dashboards or further processing.

## Next 
Project demonstrates AI and human in the loop for code, test and documentation generation. Moving forward, I plan to explore more AI capabilities to further enhance the software development lifecycle. I plan to add soon new cases for creating an AI-powered agile tool and API design. Stay tuned for updates! 
