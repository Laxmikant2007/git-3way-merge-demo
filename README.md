# Git 3-Way Merge Conflict Demo

## Introduction

This project demonstrates how Git handles a 3-way merge conflict when two branches make different changes to the same line of code.

A simple Python calculator is used to demonstrate branching, merging, conflict generation, manual conflict resolution, and the final merge commit.

## Project File

The repository contains one Python file:

- `calculator.py` - Simple calculator used to demonstrate the merge conflict.

## Branches

The repository contains the following branches:

- `main` - Final version after resolving the merge conflict.
- `feature-add` - Adds a bonus value of 10 to the addition operation.
- `feature-multiply` - Changes the calculation from addition to multiplication.
- `backup-before-identity-change` - Backup branch created during the project.

## Initial Code

The initial version of `calculator.py` performs addition:

```python
def calculate(a, b):
    return a + b


if __name__ == "__main__":
    print(calculate(10, 5))
