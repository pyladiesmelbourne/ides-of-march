# PyCharm demo

Here's a quick demo of using some of the functionality that PyCharm has for python development.

## Make directories to checkout the code

```shell
mkdir -p ~/pyladies/ides-of-march-xkcd
```

## Get the IDE

Install PyCharm community Edition, and run it

## Create a project from the git repo.

Click on 'VCS' in top menu

Select 'Checkout from Version Control'

Select 'Git'

For URL enter https://github.com/redacted/XKCD-password-generator.git

Browse to the created directory above ~/pyladies/ides-of-march-xkcd 

Click on + on the browse menu and add a subfolder called 'XKCD-password-generator'  Click on 'OK'

Click on 'Clone' and choose to open the folder.


## Use the environment python interpreter

Go to File > Settings or use Ctrl-Alt-S to open the Settings panel

Go to 'Project XKCD-password-generator' then 'Project Interpreter'

In the dropdown should be environments that have been previously created.

Click on flower/cog icon on the right of the dropdown and choose Add

Choose New environment and choose the base interpreter.

Click on 'Ok' It will take a little while.

You can now add packages.

Click on the + icon. Then find and add pytest, pytest-cov, pylint

## Git blame

PyCharm comes with built in source control functionality to help you see modified changes, add and commit changes and push.

You can access these in the top right git toolbar or the VCS top menu.

You can easily see what branch you are on, create or change branches in the bottom corner (see master)

Ctrl-A opens the git history panel.

PyCharm allows you to add things to the .gitignore file

Go to Settings Panel tab, choose 'Version Control' then 'Ignore Files'.  You can add Files and pattern matching here.

You can figure out who introduced which changes to a file by using VCS annotations which is the equivalent of git blame.

Right Click on a line in a file and select Annotate. 

## Code quality

PyCharm has it’s own built-in linting, which is already useful and nicely integrated.

There is a plugin for PyCharm to use pylint since the built-in does not catch everything. https://plugins.jetbrains.com/plugin/11084-pylint

Go to File > Settings or use Ctrl-Alt-S to open the Settings menu

Go to Pylint

Check that it has autodetected pylint since installed in its virtualenv

Go to 'Editor' then 'Inspections'

Click on 'PyLint' then 'Pylint real-time scan' Click the checkbox beside to activate.  Then choose options.

## Run unit tests

Right click on the folder containing the tests.

There are several options

Run with pytest in 'tests'

Debug with pytest in 'tests'

Run with pytest in 'tests' with coverage


## Running the code

Open up the XKCD-password-generator/xkcdpass/xkcd_password.py file

Click the green play button or Run > Run.


## How are we doing?

The IDE smackdown listed this as areas to cover in the "competition".

* [x]  Open the codebase in the IDE (configure virtualenv if needed)
* [x]  Open a file (say main.py), show syntax highlighting
* [x]  Show code autocomplete e.g. `os.path.isfile`
* [x]  Refactoring - rename a variable (context menu > rename symbol or F2)
* [x]  Jump to function/method definition (Go menu, context menu, ...)
* [x]  Show git blame for a file
* [x]  Search in codebase (Search tab) - also has neat search and replace functionality here
* [x]  Run the code 
* [x]  Run the tests
* [x]  Bonus feature (presenter's choice) - TBA
