# Contributing to jalali-data

First off, thank you for considering contributing to `jalali-data`! We welcome any form of contribution, from reporting bugs and suggesting features to submitting code changes. Your help is essential for keeping it great.

This document provides guidelines for contributing to this project. Please read it carefully to ensure a smooth and effective collaboration.

## Table of Contents

-   [How Can I Contribute?](#how-can-i-contribute)
    -   [Reporting Bugs](#reporting-bugs)
    -   [Suggesting Enhancements](#suggesting-enhancements)
    -   [Your First Code Contribution](#your-first-code-contribution)
    -   [Pull Requests](#pull-requests)
-   [Development Setup](#development-setup)
-   [Coding Standards](#coding-standards)
    -   [Code Formatting](#code-formatting)
    -   [Linting](#linting)
    -   [Type Hinting](#type-hinting)
    -   [Docstrings](#docstrings)
    -   [Testing](#testing)
-   [Git Commit Messages](#git-commit-messages) (Recommended)
-   [Code of Conduct](#code-of-conduct)

## How Can I Contribute?

### Reporting Bugs

If you find a bug, please ensure the bug was not already reported by searching on GitHub under [Issues](https://github.com/sajjadeakbari/jalali-data/issues).

If you're unable to find an open issue addressing the problem, [open a new one](https://github.com/sajjadeakbari/jalali-data/issues/new/choose). Be sure to include:

*   A **clear and descriptive title** for the issue.
*   A **detailed description** of the problem.
*   **Steps to reproduce** the bug, including any relevant code snippets.
*   The **version of `jalali-data`** you are using (e.g., from `pip show jalali-data` or `jalali_data.__version__`).
*   Your **Python version** (e.g., `python --version`) and **Operating System**.
*   Any **relevant error messages or full tracebacks**.

### Suggesting Enhancements

If you have an idea for a new feature or an improvement to an existing one:

1.  Check the [Issues](https://github.com/sajjadeakbari/jalali-data/issues) to see if your idea has already been discussed or is being worked on.
2.  If not, [open a new issue](https://github.com/sajjadeakbari/jalali-data/issues/new/choose) to propose your enhancement.
3.  Clearly outline your suggestion. Explain why this enhancement would be useful to `jalali-data` users and, if possible, provide examples of how it might be used or what problem it solves.

### Your First Code Contribution

Unsure where to begin contributing to `jalali-data`? You can start by looking through issues tagged `good first issue` or `help wanted`:

*   [Good first issues](https://github.com/sajjadeakbari/jalali-data/labels/good%20first%20issue) - Typically require a few lines of code and a test or two. Great for getting familiar with the codebase.
*   [Help wanted issues](https://github.com/sajjadeakbari/jalali-data/labels/help%20wanted) - Might be a bit more involved but are well-defined tasks.

(Note: These labels will be used more actively as the project matures and issues are created.)

### Pull Requests

We actively welcome your pull requests.

1.  **Fork** the repository on GitHub to your personal account.
2.  **Clone** your fork locally:
    ```bash
    git clone git@github.com:YOUR_USERNAME/jalali-data.git
    cd jalali-data
    ```
3.  **Create a new branch** for your changes, based off the `main` branch:
    ```bash
    # For new features:
    git checkout -b feature/describe-your-feature 
    # Example: git checkout -b feature/hijri-ummalqura-algorithm

    # For bug fixes:
    git checkout -b bugfix/describe-the-fix
    # Example: git checkout -b bugfix/jalali-conversion-off-by-one-for-leap-years
    ```
    Please use descriptive branch names (e.g., `feature/add-moon-sighting-option`, `bugfix/gregorian-to-jalali-feb29-error`).
4.  Make your changes in the new branch.
5.  **Test your changes thoroughly.** (See [Testing](#testing) section).
6.  Ensure your code adheres to our [Coding Standards](#coding-standards). Run formatters and linters (see [Development Setup](#development-setup) for how).
7.  **Add or update documentation** as needed. This includes docstrings for new/modified code and any relevant files in the `docs/` directory if API changes or new features are introduced.
8.  **Commit your changes** with clear and descriptive commit messages. (See [Git Commit Messages](#git-commit-messages) section).
    ```bash
    git add .
    git commit -m "feat: Add support for Hijri Umm al-Qura calendar algorithm" 
    ```
9.  **Push** your branch to your fork on GitHub:
    ```bash
    git push origin feature/describe-your-feature
    ```
10. **Open a Pull Request (PR)** from your branch on your fork to the `main` branch of the `sajjadeakbari/jalali-data` repository.
11. Provide a clear title and a detailed description for your PR. Explain the changes you've made and why. Link to any relevant issues (e.g., "Closes #123", "Fixes #456"). If your PR is a work in progress, consider creating a [Draft Pull Request](https://github.blog/2019-02-14-introducing-draft-pull-requests/).

## Development Setup

To set up `jalali-data` for local development:

1.  **Fork and clone** the repository (as described in the [Pull Requests](#pull-requests) section).
2.  Navigate into the project directory: `cd jalali-data`
3.  **Create and activate a virtual environment** (recommended):
    ```bash
    python -m venv .venv
    # On macOS/Linux:
    source .venv/bin/activate
    # On Windows (Git Bash or WSL):
    # source .venv/bin/activate 
    # On Windows (Command Prompt or PowerShell):
    # .venv\Scripts\activate
    ```
4.  **Install dependencies**, including all development tools:
    ```bash
    pip install -e ".[dev,test,docs]"
    ```
5.  **Set up pre-commit hooks** (highly recommended):
    This will automatically run linters and formatters before each commit, helping to ensure consistency.
    ```bash
    pre-commit install
    ```
    If you choose not to use `pre-commit`, you'll need to run the tools manually before pushing your changes. You can do this with:
    ```bash
    black .
    isort .
    flake8 jalali_data tests
    mypy jalali_data tests
    ```
    (See [Coding Standards](#coding-standards) for more details on each tool).

## Coding Standards

Please ensure your contributions adhere to the following standards. Our `pre-commit` hooks (if installed) and CI pipeline will help enforce these. All configurations for these tools are primarily in the [**`pyproject.toml`**](../pyproject.toml) file.

### Code Formatting

*   We use [**Black**](https://github.com/psf/black) for opinionated code formatting.
*   We use [**isort**](https://pycqa.github.io/isort/) for sorting imports alphabetically and automatically separating them into sections.
    (Configuration is in [pyproject.toml](../pyproject.toml))

### Linting

*   We use [**Flake8**](https://flake8.pycqa.org/en/latest/) for linting to catch style issues (PEP 8), logical errors, and code complexity problems.
    (Configuration is in [pyproject.toml](../pyproject.toml))

### Type Hinting

*   All new Python code should include [**Type Hints**](https://docs.python.org/3/library/typing.html) (as per PEP 484).
*   We use [**Mypy**](http://mypy-lang.org/) for static type checking to catch type errors before runtime.
    (Configuration is in [pyproject.toml](../pyproject.toml))

### Docstrings

*   All public modules, classes, functions, and methods should have clear, concise, and informative docstrings.
*   Please follow [**Google Style Docstrings**](https://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings).
    Example:
    ```python
    def example_function(param1: int, param2: str) -> bool:
        """Summarizes what the function does in one line.

        A more detailed explanation can follow here if necessary,
        describing the function's behavior, purpose, or any
        nuances.

        Args:
            param1: Description of the first parameter, including its type.
            param2: Description of the second parameter.

        Returns:
            A boolean indicating some result. True if successful, False otherwise.

        Raises:
            ValueError: If `param1` is negative, as an example.
            TypeError: If `param2` is not a string.
        """
        if not isinstance(param2, str):
            raise TypeError("param2 must be a string")
        if param1 < 0:
            raise ValueError("param1 cannot be negative")
        return len(param2) > param1
    ```

### Testing

*   All new features and bug fixes **must** include comprehensive tests.
*   We use [**Pytest**](https://docs.pytest.org/) as our testing framework.
*   Tests should be placed in the `tests/` directory, generally mirroring the structure of the `jalali_data/` package (e.g., tests for `jalali_data/calendars/jalali.py` would be in `tests/unit/calendars/test_jalali.py`).
*   Aim for high test coverage (ideally >90%). You can check coverage locally by running:
    ```bash
    pytest --cov=jalali_data --cov-report=term-missing
    ```
*   Consider using [**Hypothesis**](https://hypothesis.readthedocs.io/) for property-based testing, especially for complex algorithms, conversion logic, and boundary conditions.

## Git Commit Messages (Recommended)

While not strictly enforced for all commits yet, we strongly encourage following the [**Conventional Commits**](https://www.conventionalcommits.org/en/v1.0.0/) specification for commit messages, especially for PR titles. This makes the commit history more readable, helps automate changelog generation, and clearly communicates the nature of changes.

**Format:** `<type>[optional scope]: <description>`

Common types:
*   `feat`: A new feature
*   `fix`: A bug fix
*   `docs`: Documentation only changes
*   `style`: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
*   `refactor`: A code change that neither fixes a bug nor adds a feature
*   `perf`: A code change that improves performance
*   `test`: Adding missing tests or correcting existing tests
*   `build`: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
*   `ci`: Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs)
*   `chore`: Other changes that don't modify src or test files (e.g., updating dependencies)

Examples:
*   `feat: Add Hijri Umm al-Qura calendar calculation`
*   `fix(jalali): Correct off-by-one error in Jalali to Gregorian conversion for March`
*   `docs: Update README with installation and quick start guides`
*   `style(core): Apply black and isort formatting to algorithms.py`
*   `refactor(validation): Simplify date input validation logic`
*   `test(hijri): Add property-based tests for Hijri date arithmetic`

## Code of Conduct

All contributors are expected to adhere to a basic standard of respectful and constructive communication. While a formal Code of Conduct (like the [Contributor Covenant](https://www.contributor-covenant.org/)) is not yet in place, we may adopt one if the community grows. For now, please:
*   Be respectful of differing viewpoints and experiences.
*   Give and gracefully accept constructive feedback.
*   Focus on what is best for the community and the project.

---

Thank you for your interest in contributing to `jalali-data`! We look forward to your contributions.
