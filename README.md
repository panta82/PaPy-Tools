# PaPy Tools

#### Tiny bash utilities to better manage [pyvenv](https://docs.python.org/3/library/venv.html)

##### (In other words, NIH version of [virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/))


## Usage

```sh
cd ~/project/proj1

pp-mk Project1 3.5.2           # Create a new virtualenv with the name "Project1"
                               # Equivalent to: pyvenv ~/.pyvenv/Project1
                               # In this case, we will base the new venv on Python 3.5.2
                               # (previously installed through pyenv)

source pp-activate             # Project1 is activated
                               # Equivalent to: source ~/.pyvenv/Project1/bin/activate
                               # Note that the project name is automatically
                               # detected using a hidden file in current directory

#... work on Project1

deactivate                     # Same as with pyvenv
```

## Commands

### `pp-mk [env_name] [python_version]`
Create a new environment with the given name. All argument switches are passed along to `pyvenv`.
If no name is provided, we will use the name of the current directory.

If provided `env_name` differs from current directory, it is stored in a hidden local file `.papy`.

If you use [pyenv](https://github.com/yyuu/pyenv), you can also specify the python version to use.
PaPy will also work with the usual shim.

### `pp-activate [env_name]`
Activate an environment with the given name. If name is not provided, the environment is detected
based on the current directory.

### `pp-list`
List available environments from `~/.pyvenv`

## Configuration

You can set environmental variables to change some of the settings. You can find what's available
in `pp-common`.

## Requirements

Linux or Mac, reasonably recent bash.

## Installation

1. Clone this repository
2. Add cloned directory to PATH

You can also copy the files into your bin folder. Example (from inside the cloned repository):

```sh
sudo cp ./pp-* /usr/local/bin/
```

## Stability

Tested on Mac, homebrew bash. Seems to be working fine.
Use at your own risk.

## Licence

MIT
