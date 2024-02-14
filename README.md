![Run linters and tests workflow](https://github.com/islomar/python-kata-template/actions/workflows/run-linters-and-tests.yml/badge.svg)

# Python template for a kata

- Template repository for Python katas (Dockerized)
- The repository is created as a **GitHub repository template**, so that you can easily create your own GitHub repository from this one.
  - [Here](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template#creating-a-repository-from-a-template) you can find the instructions: easy peasy!
  - There is a **GH project** associated with this repo, with some pending improvements.
- Everything is **Dockerized**. If you run `make` from the root folder of the project, you can see all the actions that you can execute (e.g. running the tests, static analysis, code coverage, etc.)


## HOW to use it
1. Generate a repo using this one as a template, following [these instructions](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template#creating-a-repository-from-a-template)
2. Replace the `python-kata-name` placeholder that appears in several files with your own name (e.g. `python-fizzbuzz`). 
   - For example, you can easily do it running `make rename-project new-name=python-fizzbuzz`


## Prerequisites
- You need `Docker` installed.
- **IMPORTANT**: just the first time, run `make local-setup`.
    - This will set up things like configuring Git hooks. The `pre-commit` hook will automatically run the linters and tests, rejecting the commit in case any of them fail.


## How to update or add a Python package
  1. In the terminal, run:
     - In case it's a development dependency: `make add-dev-package package=<package_name>` 
     - In case it's a "production" dependency: `make add-package package=<package_name>`
  2. Commit and push the changes updated in the file `poetry.lock` and `pyproject.toml`


## Functionalities included
- There is pipeline configured as a GitHub Action which runs all the linters, the tests and both the coverage and mutation testing
  - The artifacts with the HTML reports generated can be downloaded from the GitHub project tab "Actions" --> "Summary" --> "Artifacts"
- [**Dependabot**](https://docs.github.com/code-security/dependabot/dependabot-version-updates/configuration-options-for-the-dependabot.yml-file) is configured at GitHub repository level, in order to automatically update the dependencies weekly.
- A **badge** on top of this README file shows the status of the GH Action (passing or failing).
- I have used [**black**](https://github.com/psf/black) for both linting and formatting.
  - If the format check fails, you can automatically format whatever missing running `make reformat` 
- You can easily run the **test coverage** with `make test-coverage`
- You can easily run **mutation testing** with `make test-run-mutation`
  - Mutmut keeps a result cache in `.mutmut-cache` so if you want to make sure you run a full mutmut run just delete this file.


## More interesting info
- About mutation testing and coverage reports
  - https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-python
- [Caching dependencies to speed up workflows](https://docs.github.com/en/actions/using-workflows/caching-dependencies-to-speed-up-workflows)
- **Mutation testing**
  - https://github.com/boxed/mutmut
  - In case it were needed: make mutmut mutation faster using [Hammett](https://github.com/boxed/hammett)
  - https://opensource.com/article/20/7/mutmut-python
  - https://medium.com/poka-techblog/hunting-mutants-with-mutmut-5f575b625598
  - https://blog.stackademic.com/automating-mutation-testing-with-mutmut-and-github-actions-9767b4fc75b5
    - It talks about GitHub Actions Caching Strategy
  - Alternative: https://github.com/sixty-north/cosmic-ray
