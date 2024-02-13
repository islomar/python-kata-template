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
- Include Mutation Testing in the pipeline
- Better explain the libraries and GH repo configuration (e.g. dependabot, linters, rename-project, test coverage, mutation testing, etc.)
  - https://github.com/boxed/mutmut
  - https://opensource.com/article/20/7/mutmut-python
  - https://medium.com/poka-techblog/hunting-mutants-with-mutmut-5f575b625598
  - Mutmut keeps a result cache in `.mutmut-cache` so if you want to make sure you run a full mutmut run just delete this file.
  - Alternative: https://github.com/sixty-north/cosmic-ray
- https://docs.github.com/en/actions/using-workflows/caching-dependencies-to-speed-up-workflows
- Send message to Slack if the pipeline fails
- security scanning
- publish mutation testing and coverage reports
- Make mutmut mutation faster using [Hammett](https://github.com/boxed/hammett)
