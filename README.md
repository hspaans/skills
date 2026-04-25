# Skills for GitHub Copilot

> [!WARNING]
> This repository is a work in progress and may contain incomplete or experimental skills. The skills provided here are for testing and development purposes only and may not be stable or fully functional. Use with caution and always review the skill's code and documentation before using it in any production environment.

## What is a Skill?

A skill is a reusable component that encapsulates specific functionality or behavior. It can be thought of as a modular piece of code that can be easily integrated into larger applications or systems. Skills are designed to be flexible and adaptable, allowing developers to quickly add new features or capabilities without having to rewrite existing code.

## Skill Formatting

```markdown
---
name: skill-name
description: Brief description of the skill
---

# Skill Title

Guidelines and instructions...
```

## Installation

From version 2.90.0 of the [GitHub CLI](https://github.com/cli/cli), you can install skills directly from this repository using the following command:

```bash
gh skill install <owner>/<repo> <skill-name>
```

An example to install a Python skill with GitHub CLI command:

```bash
gh skill install hspaans/skills python
```

Updating **all** skills can be done with:

```bash
gh skill update
```

Or only a specific skill with:

```bash
gh skill update <skill-name>
```

## Available Skills

### Language-Specific Skills

- [python](python/SKILL.md) for code generation, refactoring, and debugging
