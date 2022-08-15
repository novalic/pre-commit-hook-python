# pre-commit-hook-python

This is the pre commit hook configuration usual configuration that I used in all my **Python 3.X** projects.
To use this configuration in **Python 2.X**, the flake8 plugins must be removed. 

## Description, installation, usage

The file that defines the hook is `.pre-commit-config.yaml` and hook must be installed manually in our computer for each repository, as it’s stored in our `.git` folder.

**Steps to install the hooks (as done in Ubuntu):**

1. Install **pre-commit**:

This is the library used to install, uninstall the hooks, run checks, etc, in a project.

In bash run:

```bash
$ pip install pre-commit
```


2. Install the hooks:

Navigate to the project’s root folder and run:

```bash
$ pre-commit install
```

You will see a message that confirms the hoooks were installed correctly. From now on everytime you run `git commit`, the pre commit hooks will be run. If one of them fails, the commit will not be done.

**Useful notes:**

- Beware! When you modify a file, flake8 will check the whole file, not only the diff.
- It is possible to bypass the hooks by adding the command `-n` . i.e. `git commit -n`
- We can make use of the `pre-commit` library to run the hooks in all our files by running the command `pre-commit run --all-files` in a terminal, in the project’s root folder.
- Installing `pre-commit` at a global level in our computer can be undesirable. We can opt for installing it in a virtual environment, or uninstalling it after installing the hook: `pip uninstall pre-commit` .
