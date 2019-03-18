# Atom demo

Here's a demo of some of the functionality that Atom has for Python development, by a long-time Atom and vi(m) user and Python newbie. This demo mostly uses Atom's core editor functionality (with some packages), not the full-blown [Atom IDE](https://ide.atom.io/) which [requires Python language server](https://atom.io/packages/ide-python).

[Atom](https://atom.io/) was built by GitHub using the [Electron](https://electronjs.org/) framework which also powers VS Code and some other apps you may have heard of/used.

Atom ships with a few core packages (including git and GitHub integration) and there are thousands of contributed ones in the [Atom package repository](https://atom.io/packages). Atom configuration (for the core editor and for packages) can be done from the settings screen or directly using `.cson` (CoffeeScript Object Notation) files.

Assuming stock Atom is already installed and XKCD codebase already checked out.

## Running commands

Commands are run from the main or contextual menus, from the command palette (`cmd+shift+p` or `ctrl+shift+p`), or from other UI elements.

## Install python packages

[language-python](https://atom.io/packages/language-python) is a default package. We may also want the following:

* [atom-python-test](https://atom.io/packages/atom-python-test) -- requires `py.test`
* [autocomplete-python](https://atom.io/packages/autocomplete-python)
* [git-blame](https://atom.io/packages/git-blame)
* [linter-python](https://atom.io/packages/linter-python) -- requires `pylama`
* [python-tools](https://atom.io/packages/python-tools) -- useful for refactoring
* [script-runner](https://atom.io/packages/script-runner) -- run scripts in python and various other scripting languages, output to Atom console

## Open the codebase in the IDE (configure virtualenv if needed)

1. New window
2. Add project folder

## Open a file (say main.py), show syntax highlighting

✓

## Show code autocomplete

✓

## Refactoring - rename a variable

[python-tools] Show Usages.

## Jump to function/method definition

[python-tools] Goto Definition.

## Show git blame for a file

The `git-blame` package will show blame in the left column. Authors can be distinguished by colour of margin. Clicking in the blame column will open the commit in GitHub, Bitbucket, GitLab, or a custom remote, if available.

## Search in codebase

Find/Replace in Project.

## Run the code

[atom-python-run] `f5`

## Run the tests

[atom-python-test]

1. Run test under cursor
2. Run all tests on page
3. Run project tests
