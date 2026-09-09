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
```

The output is:

```text
15
```

## Feature 1: Addition with Bonus

The `feature-add` branch changes the calculation to:

```python
def calculate(a, b):
    return a + b + 10
```

For the values `10` and `5`, the output is:

```text
25
```

## Feature 2: Multiplication

The `feature-multiply` branch changes the same line to:

```python
def calculate(a, b):
    return a * b
```

For the values `10` and `5`, the output is:

```text
50
```

## 3-Way Merge Conflict

Both feature branches modified the same line in different ways.

When `feature-multiply` was merged into `main`, Git could not automatically combine the changes, so a merge conflict occurred.

The conflicting code was:

```text
<<<<<<< HEAD
return a + b + 10
=======
return a * b
>>>>>>> feature-multiply
```

The conflict was resolved manually by combining both operations:

```python
def calculate(a, b):
    return (a * b) + 10
```

## Final Result

The final `main` branch contains:

```python
def calculate(a, b):
    return (a * b) + 10


if __name__ == "__main__":
    print(calculate(10, 5))
```

The final output is:

```text
60
```

## Git Workflow

The following steps were performed:

1. Created the Git repository.
2. Added the initial `calculator.py`.
3. Created the `feature-add` branch.
4. Modified the calculator to add a bonus of 10.
5. Created the `feature-multiply` branch from the original version.
6. Modified the same line to perform multiplication.
7. Merged `feature-add` into `main`.
8. Merged `feature-multiply` into `main`.
9. Git generated a merge conflict.
10. Resolved the conflict manually.
11. Tested the final program.
12. Created the merge commit.
13. Pushed the branches to GitHub.

## Merge Commit

The final merge commit has two parents:

- `feature-add`
- `feature-multiply`

The merge commit combines the changes from both branches after the conflict was manually resolved.

## Conclusion

This project demonstrates how Git handles conflicting changes made on separate branches and how a developer can manually resolve the conflict before creating the final merge commit.
