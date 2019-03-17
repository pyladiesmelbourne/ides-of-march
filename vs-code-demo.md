# VS Code demo

Here's a quick demo of using some of the functionality that VS Code has for python development.

This was me making sure I could tick all the boxes easily for the IDE smackdown for PyLadies March 2019.

## Make directories to checkout the code and create the virtualenv

```shell
mkdir -p ~/pyladies/ides-of-march-xkcd
mkdir ~/envs
cd ~/pyladies/ides-of-march-xkcd
git clone https://github.com/redacted/XKCD-password-generator.git
```

## Create the virtualenv

Note that normally I'd use conda envs, but this demo was asking about virtualenv. Pipenv is another alternative.

```shell
pip install virtualenv
virtualenv ~/envs/xkcd
source ~/envs/xkcd/bin/activate
pip install pytest
pip install pytest-cov
pip install pylint
```

## Get the IDE and install the Python extension

Note that if you are using Anaconda, VS Code is installed at the final step of its installation process.

Install VS code, and run it

Install the python extension from the Welcome page

Also set key bindings if you like

## Create a workspace

Open folder: ~/pyladies/ides-of-march-xkcd

Save workspace as ~/pyladies/ides-of-march-xkcd.code-workspace

## Use the environment python interpreter

Cmd-Shift-P to open the command palette and enter `Python: Select Interpreter`

Select the `xkcd virtualenv: ~/envs/xkcd/bin/python`

Environment selection should also show up in the bottom bar, you can click on this to change envs

## Git blame

VS Code comes with built in source control functionality to help you see modified changes, create or change branches, add and commit changes and push.

You can easily see what branch you are on, create or change branches in the bottom corner (see master)

However, for better visibility on git history, you can install the Gitlens extension

Cmd-Shift-P `Extensions: install`

Search for `gitlens` and install

This provides useful git blame information!

## Code quality

Cmd-Shift-P `Python: Select Linter`

Choose a linter from the list e.g. `pylint` used in this example.

I'd generally go for something like `propsector`

See also: https://code.visualstudio.com/docs/python/linting

## Run unit tests

Cmd-Shift-P `Python: Configure unit tests`

Select `pytest` and select root directory XKCD-password-generator

Create a new file in XKCD-password-generator directory, `pytest.ini`
```ini
[pytest]
addopts = -p no:warnings --cov-report xml:cov.xml --cov-report term-missing --cov=XKCD-password-generator XKCD-password-generator/tests
```

Cmd-Shift-P `Python: Discover unit tests`

Cmd-Shift-P `Python: Run Tests`

See also bottom bar with the lightning bolt. You can also discover and run tests from here, including rerunning failed tests.

See also https://code.visualstudio.com/docs/python/unit-testing

As an aside, lets demonstrate how VS Code allows you to add things to the .gitignore file

Go to the Source Control tab and if you right click on one of the pytest cache files you can see it has a Add file to .gitignore, a handy way to configure files that shouldn't get checked in.

## Easily see test coverage

Tests are great but the real value is when you can demonstrate that your code has good code coverage.

Cmd-Shift-P `Extensions: install`

Search `Coverage gutters` and install

See also https://marketplace.visualstudio.com/items?itemName=ryanluker.vscode-coverage-gutters

In particular https://github.com/ryanluker/vscode-coverage-gutters/tree/master/example/python

See also https://pytest-cov.readthedocs.io/en/latest/

Cmd-Shift-P `Coverage Gutters: Display gutters`

You'll now see green and red gutters next to code. Green means it is covered, and red means it is code that probably has bugs (i.e. no test coverage)!

You can also set watches on a file to monitor code coverage as you work.

You can see the report by Cmd-Shift-P `Coverage Gutters: Show coverage report`

## How are we doing?

The IDE smackdown listed this as areas to cover in the "competition".

* [x]  Open the codebase in the IDE (configure virtualenv if needed)
* [x]  Open a file (say main.py), show syntax highlighting
* [x]  Show code autocomplete e.g. `os.path.isfile`
* [x]  Refactoring - rename a variable (context menu > rename symbol or F2)
* [x]  Jump to function/method definition (Go menu, context menu, ...)
* [x]  Show git blame for a file (Extension: gitlens)
* [x]  Search in codebase (Search tab) - also has neat search and replace functionality here
* [x]  Run the code (Terminal > Run active file, shift+enter to run selected)
* [x]  Run the tests
* [x]  Bonus feature (presenter's choice) - coverage gutters
