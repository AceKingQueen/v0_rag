
# VSCode and Python

## Python
We'll be setting up a python environment for the lessons. We use version 3.11.

Note that there is no such thing as a default Python installation. Depending the OS you're using you'll have different options.

### MacOS
** System python **
MacOS has python pre-installed. But it is an older version. So we have to install a more recent version.

```
/usr/bin/python3 --version
Python 3.9.6
```

There are several ways to install a more recent version:

** Via Homebrew (less recommended) **
A popular way to install a more recent version is to use `brew` to install `python`.
While you specify the version you want to install, it's not easy to switch between versions. 

See <https://mac.install.guide/python/brew>

** Use pyenv to install different versions (recommended)**
A popular option option to install different versions is to use `pyenv` (<https://github.com/pyenv/pyenv>)
```
brew install pyenv
pyenv install 3.11
```

Now you can select the python version you want to use.
Either globally or per project.

```
pyenv global 3.11 # globally
pyenv local 3.11 # per project , will use .python-version file
```

** Use uv to install python **
The new hotness is to use uv, a very fast package manager rewrittten in Requirements

It's a crossing between installing different pythons and a package manager.
See (<https://docs.astral.sh/uv/getting-started/installation/>)

```
brew install uv
```

## Windows
On Windows it's common to download and install python. This might work if you use one python on your machine.
If you need different versions use py-env or uv. (recommended)

** Download and install python **
Download it from <https://www.python.org/downloads/windows/>

Install via `chocolatey` (<https://chocolatey.org/>)
```
choco install python
```

** Use pyenv-win to install different versions **
You can use `pyenv-win` (<https://github.com/pyenv-win/pyenv-win>) to install different versions. And the install the version you want to use.
```
pyenv-win install 3.11
```

## VSCode
In case you haven't installed VSCode yet, you can download it from <https://code.visualstudio.com/>.
Please take some time to familiarize yourself with the editor.

### Extensions in vscode

To use python in vscode you need to install the following extensions.
Click the link and they should open in VSCode.

- Python extension: https://marketplace.visualstudio.com/items?itemName=ms-python.python
- Jupyter extension: https://marketplace.cursorapi.com/items?itemName=ms-toolsai.jupyter
- Jupyter keymap: https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter-keymap
- Jupyter renderers: https://marketplace.cursorapi.com/items?itemName=ms-toolsai.jupyter-renderers

### Reload the window
After installing the extensions you need to reload the window.

Got to the command palette (Ctrl+Shift+P or View > Command Palette) and select `Reload Window`.

### Set the python interpreter
We need to tell vscode which python interpreter to use.

- Open the command palette (Ctrl+Shift+P or View > Command Palette)
- Search for `Python: Select Interpreter`
- Select the python interpreter you want to use.

Now reload the window again.

Next up open a terminal in VSCode.

- Open the terminal in VSCode: Ctrl+Shift+P and select `Terminal: Create New Integrated Terminal`
- Check the python version: `python --version`

If this show something like `Python 3.11.x` then we can move to the next step.
If not check the previous steps again.

### Setup a virtual environment
To avoid polluting your global python installation with the dependencies for the lessons, we'll setup a virtual environment.
For more information see: <https://code.visualstudio.com/docs/python/environments>

Creating a new virtual environment: use the command palette and search for `Python: Create Environment`. Choose .venv to create a new environment in the current workspace.

If you prefer to do it via the terminal:

```
python -m venv .venv
. ./.venv/bin/activate # To load it
```

### Select the virtual environment by default
Instead of having to activate the environment manually, we can select the python interpreter to use by default.

- Open the command palette (Ctrl+Shift+P or View > Command Palette)
- Search for `Python: Select Interpreter`
- Select the python interpreter you want to use.
- This time select the python interpreter in the .venv folder.


### Next steps
Congratulations! You have setup a python environment in VSCode and activated it.