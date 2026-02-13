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

### Overview
This repository demonstrates AI-assisted software development practices, featuring a Python-based expense tracker application. It showcases the integration of AI tools (like Cursor AI, GitHub Copilot, Codex OpenAI) in the software development lifecycle, from code generation to testing and documentation.

> To see a preview of this project go to [AI-DEV-TEST on Codespaces](https://miniature-fortnight-9p4r55gwpgwcpxv4.github.dev/).
In case codespace doesn't launch, repo is [here](https://github.com/kaironok/AI-DEV-TEST). 


## Expense Tracker Application
A command-line expense tracker with CSV file persistence. The application allows users to manage personal expenses through an interactive terminal interface.

### Features
- **List expenses**: View all recorded expenses in a formatted table
- **Add expenses**: Create new expense entries with name, amount, and category
- **Delete expenses**: Remove existing expenses by name
- **Edit expenses**: Modify existing expense details
- **CSV Persistence**: All data is automatically saved to and loaded from `expenses.csv`

### Original AI Prompt (Cursor AI)
> "Build me an expense tracker application, where the expenses have the properties 'name', 'amount' and 'category'. The application should be a simple terminal-based app, and should use a CSV file as a database where expenses are automatically saved to and loaded from." 

## Getting Started

### Prerequisites
- Python 3.10 or higher
- pip (Python package installer)

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/kaironok/AI-DEV-TEST.git
   cd AI-DEV-TEST
   ```

2. Install dependencies (optional, for testing):
   ```bash
   pip install pytest flake8
   ```

### Running the Application
Run the expense tracker from the command line:
```bash
python Expense_tracker.py
```

Follow the interactive prompts to:
1. List existing expenses
2. Add a new expense
3. Delete an expense
4. Edit an expense
5. Exit the application

Your expenses will be automatically saved to `expenses.csv` in the same directory.

![Command line interface](/assets/images/Extr.jpeg)

## Testing

This repository includes comprehensive test coverage demonstrating different testing approaches:

### Simple Tests (`simple_test.py`)
Random palindrome and vowel detection tests for demonstration purposes. These showcase basic Python testing with direct output validation.

**Run with:**
```bash
python simple_test.py
```

**Tests include:**
- `is_palindrome(s)`: Case-insensitive palindrome checking (ignores spaces)
- `starts_with_vowel(s)`: Checks if a string starts with a vowel

*Note: These are demonstration tests; future updates will include more relevant expense tracker validations.*

### Unit Tests (`test_expense_tracker.py`)
Comprehensive pytest suite testing the expense tracker functionality using `monkeypatch`, `tmp_path`, and `capsys` fixtures.

**Run with:**
```bash
pytest test_expense_tracker.py
```

**Features tested:**
- CSV loading and saving operations
- Expense listing with proper formatting
- Add, delete, and edit expense operations
- Invalid input handling
- Main menu functionality

The test suite uses helper functions like `_set_csv(...)` for test isolation with temporary CSV files.

### Integration Tests (`integration_tests.py`)
Tests demonstrating the integration between to-do item workflows and expense persistence.

**Run with:**
```bash
python integration_tests.py
```

**Integration scenarios:**
- Completed tasks trigger expense creation
- Incomplete tasks do not create expense entries

### Test Artifacts
- **`TEST_REPORT.md`**: Human-readable summary of test results with pass/fail status and insights
- **`test_results.txt`**: Raw test output for debugging and detailed analysis
- **`TEST_SUMMARY.csv`**: Machine-readable summary for dashboards and reporting

### Running All Tests
```bash
pytest
```

## Continuous Integration

This repository uses GitHub Actions for automated testing and code quality checks.

### Workflow: Python Application
- **Trigger**: Runs on push and pull requests to the `main` branch
- **Environment**: Ubuntu with Python 3.10
- **Steps**:
  1. Install dependencies (pytest, flake8)
  2. Lint code with flake8 (syntax errors and code quality)
  3. Run all tests with pytest

View the workflow configuration in `.github/workflows/python-app.yml`.

## Development Setup

### Using Codespaces or VS Code Dev Containers
This repository includes configuration for GitHub Codespaces and VS Code Dev Containers:
- `.devcontainer/`: Dev container configuration for consistent development environment
- `.vscode/`: VS Code workspace settings

Simply open the repository in a Codespace or use the "Reopen in Container" option in VS Code.

## Test Report Description 

- `TEST_REPORT.md`: human-readable summary of test results, including pass/fail status and key insights.
- `test_results.txt`: raw output from test runs, useful for debugging and detailed analysis.
- `TEST_SUMMARY.csv`: compact machine-readable summary for reporting dashboards or further processing.

## GitHub Actions
- Action is added.
## Next 
Project demonstrates AI and human in the loop for code, test and documentation generation. Moving forward, I plan to explore more AI capabilities to further enhance the software development lifecycle. I plan to add soon new cases for creating an AI-powered agile tool and API design. Stay tuned for updates! 
