# Python template for a kata

- Template repository for Python katas (Dockerized)
- Everything is Dockerized. If you run "make", you can see all the actions that you can execute (e.g. running the tests, static analysis, code coverage, etc.)

## Prerequisites
- You need `Docker` installed.
- Just the first time, run `make local-setup`.
    - This will set up things like configuring Git hooks.

## How to update or add a Python package
  1. In the terminal, run `make add-dev-package package=<package_name>`. 
2Commit and push the changes updated in the file `poetry.lock` and `pyproject.toml`.
