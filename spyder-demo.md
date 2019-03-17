# Spyder demo

Here's a quick demo of using some of the functionality that Spyder has for 
python development.

This was me seeing if it could tick all the boxes easily for the IDE 
smackdown for PyLadies March 2019.

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

## Get the IDE 

Recommended installation is with Anaconda.

We also want to use some plugins, so once anaconda is installed, you'll need 
to add some things to the base conda environment

```shell
conda install -c spyder-ide spyder-terminal # (1)
conda install -c spyder-ide spyder-notebook # (2)
conda install -c spyder-ide spyder-unittest # (3)
conda install -c spyder-ide spyder-reports # (4)
```

(1) A plugin for displaying an OS independent virtual terminal 
inside the main Spyder window. Currently supports both Unix-like 
and Windows operating systems.

(2) A plugin to use Jupyter notebooks inside Spyder. Currently it 
supports basic functionality such as creating new notebooks, opening 
any notebook in your filesystem and saving notebooks at any location.

(3) A plugin that integrates popular unit test frameworks with Spyder, 
allowing you to run test suites and view the results in the IDE.

(4) A plugin to render Markdown reports

Now you can run Spyder: `spyder3`

## Create a project

Projects > New Project > existing directory

Open folder: `~/pyladies/ides-of-march-xkcd` and select Create.

You should now be able to see the Project Explorer on the left hand side 
of the IDE window. If you can't use Projects > Project explorer

## Use the environment python interpreter

Python > Preferences > Python interpreter. Browse to `~/envs/xkcd/bin/python`

## git integration

I couldn't find any? Couldn't find an easy way to have intergrated git blame.

Using a terminal plugin is the best I can see here.

## Code quality

Run > Run static code analysis

## Run unit tests

(A plugin was required for this, which we installed earlier.)

Run > Run unit tests

Select `nose` and select the folder `XKCD-password-generator`

An aside: I expect that selecting pytest will pick up the pytest.ini file 
which is  appears to do but I'm not sure pytest tests (which in our example are 
running unittest tests) are fully supported with this plugin yet as it runs 
into an some internal error. It discovers tests but doesn't report on them
properly and you have to go to the ouput to see what is up.

## Easily see test coverage

Tests are great but the real value is when you can demonstrate that your code 
has good code coverage.

Create a new file in XKCD-password-generator directory, `setup.cfg`
```ini
[nosetests]
verbosity=3
with-doctest=1
with-coverage=1
cover-html=1
cover-xml=1
```

Create a new file in XKCD-password-generator directory, `.coveragerc`
```
[report]
show_missing = True
```

Run the unit tests

By viewing output you can see the coverage report.

## Running the code

Open up the XKCD-password-generator/xkcdpass/xkcd_password.py file

Click the green play button or Run > Run.

## How are we doing?

The IDE smackdown listed this as areas to cover in the "competition".

* [x]  Open the codebase in the IDE (configure virtualenv if needed)
* [x]  Open a file (say main.py), show syntax highlighting
* [x]  Show code autocomplete e.g. `os.path.isfile`
* [ ]  Refactoring - rename a variable (context menu > rename symbol or F2)
* [x]  Jump to function/method definition (Go to definition)
* [ ]  Show git blame for a file (Extension: gitlens)
* [x]  Search in codebase (Search in files)
* [x]  Run the code (Green play button)
* [x]  Run the tests Unit testing tab after installed plugin
* [x]  Bonus feature (presenter's choice) - notebooks? run cell stuff?
