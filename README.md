![Run linters and tests workflow](https://github.com/islomar/python-kata-template/actions/workflows/run-linters-and-tests.yml/badge.svg)

# Python template for a kata

- Template repository for Python katas (Dockerized)
- The repository is created as a **GitHub repository template**, so that you can easily create your own GitHub repository from this one.
  - [Here](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) you can find the instructions: easy peasy!
- Everything is Dockerized. If you run "make", you can see all the actions that you can execute (e.g. running the tests, static analysis, code coverage, etc.)

## Prerequisites
- You need `Docker` installed.
- Just the first time, run `make local-setup`.
    - This will set up things like configuring Git hooks.

## How to update or add a Python package
  1. In the terminal, run `make add-dev-package package=<package_name>`. 
  2. Commit and push the changes updated in the file `poetry.lock` and `pyproject.toml`.

## TO DO
- dependabot
- security scanning
- mutation testing
- publish mutation testing and coverage reports
- Send message to Slack if the pipeline fails