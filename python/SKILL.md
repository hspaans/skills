---
name: python
description: Expert in Python development with best practices across web, data science, and automation
---

# Python

You are an expert in Python development across multiple domains including web development, data science, automation, and machine learning.

## Universal Principles

- PEP 8 compliance consistently emphasized
- Error handling via early returns and guard clauses
- Async/await for I/O-bound operations
- Type hints mandatory
- Modular, functional approaches preferred over classes

## Code Style

- Write concise, technical Python with accurate examples
- Use functional and declarative programming patterns where appropriate
- Prefer iteration and modularization over code duplication
- Use descriptive variable names with auxiliary verbs (e.g., `is_active`, `has_permission`)
- Use lowercase with underscores for file/directory naming
- Use docstrings for all public functions and classes, following PEP 257 conventions
- Use type hints for all function parameters and return types, adhering to PEP 484 standards
- Avoid global state; prefer function parameters and return values for data flow
- Use list comprehensions and generator expressions for concise and efficient data processing
- Use context managers for resource management (e.g., file handling, database connections)
- Use logging instead of print statements for better control over output and debugging

## Dependency Management
- Use virtual environments, the python `venv` module, for project isolation
- Use pip for package management, with `pyproject.toml` for project metadata and dependencies
  - The default build system should be set to `setuptools` in `pyproject.toml` and have the following structure:
    ```toml
    [build-system]
    requires = ["setuptools>=42", "wheel"]
    build-backend = "setuptools.build_meta"
    ```
  - Use the following dependency groups in `pyproject.toml`:
    ```toml
    [project]
    dependencies = [
    ]
    
    [dependency-groups]
    dev = [
        "tox>=4.30.0,<5.0.0",
        {include-group = "test"},
        {include-group = "lint"},
        {include-group = "docs"},
    ]
    test = [
        "pytest>=8.0.0,<9.0.0",
        "pytest-cov",
        "pytest-fixtures",
        "pytest-github-actions-annotate-failures",
        "pytest-randomly",
        "pytest-sphinx",
    ]
    lint = [
        "flake8>=7,<8",
        "flake8-black",
        "flake8-bugbear",
        "flake8-builtins",
        "flake8-comprehensions",
        "flake8-deprecated",
        "flake8-docstrings",
        "flake8-typing-imports",
        "flake8-print",
        "flake8-pylint",
        "flake8-pytest-style",
        "flake8-rst-docstrings",
        "flake8-isort",
        "pymarkdownlnt",
        "rstcheck",
        "yamllint",
        "mypy>=1.5.0,<2.0.0",
    ]
    docs = [
        "Sphinx~=9.1",
        "sphinx-autobuild",
        "sphinx-toolbox",
        "furo",
    ]
    ```
- Use `pylock.toml` for locking dependencies
- Avoid global installations; prefer project-specific environments

## Testing

- Use pytest for testing with comprehensive coverage
- Use fixtures for setup and teardown
- Use parameterized tests for multiple input scenarios
- Use pytest-cov for coverage reporting
- Use pytest-randomly to randomize test order and detect inter-test dependencies
- Use pytest-github-actions-annotate-failures for better CI feedback
- Use pytest-sphinx for testing documentation builds
- Use tox for testing across multiple Python versions and environments
- Use dependency groups in `pyproject.toml` to manage testing dependencies, ensuring that the `dev` group includes all necessary testing dependencies for seamless development and testing workflows

## Linting and Formatting

- Use flake8 with a comprehensive set of plugins for linting (e.g., flake8-black, flake8-bugbear, flake8-builtins, flake8-comprehensions, flake8-deprecated, flake8-docstrings, flake8-typing-imports, flake8-print, flake8-pylint, flake8-pytest-style, flake8-rst-docstrings, flake8-isort)
- Use black for code formatting
- Use bandit for security linting

## Data Analysis

- Use pandas, matplotlib, seaborn for data analysis
- Use vectorized operations over explicit loops for better performance
- Leverage NumPy for numerical computations

## Web Development

### Django
- Use class-based views (CBVs) for complex views
- Prefer function-based views (FBVs) for simpler logic
- Query optimization using select_related and prefetch_related
- Use Django's ORM; avoid raw SQL unless necessary

### FastAPI
- Use def for pure functions and async def for asynchronous operations
- Use Pydantic v2 for validation
- Implement the RORO pattern: Receive an Object, Return an Object

### Flask
- Use Blueprint-based organization
- Implement Flask application factories for modularity and testing

## Error Handling

- Handle edge cases at function entry points
- Employ early returns for error conditions
- Place happy path logic last
- Use guard clauses for preconditions
- Implement proper error logging with context

## Performance

- Use async/await for I/O-bound operations
- Implement caching where appropriate
- Use lazy loading for large datasets
- Profile code to identify bottlenecks