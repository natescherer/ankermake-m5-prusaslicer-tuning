# Installing Python

There are many, many ways to install Python on every platform, but I recommend using a version management tool for your particular OS. Tools like these allow you to have multiple, side-by-side installations of different Python versions and to switch between then quickly and easily. If you eventually get serious about Python development, you'll probably want to install this way eventually, so I recommend everyone do it from the start.

## Choosing your Version

Version management tools let you have multiple Python versions installed side-by-side, but you still need to decide what version to use. I recommend choosing one of the "Active Support" versions [here](https://endoflife.date/python) based on whether you prefer tried-and-true or bleeding edge.

### Linux

[asdf](https://asdf-vm.com/) is a magical tool for easy, side-by-side installation of command line tools on Linux, Python included.

1. Install `asdf` via [their instructions](https://asdf-vm.com/guide/getting-started.html)
1. Run the following in your shell of choice, replacing, replacing `VERSIONHERE` with the three digit version number you found in *Choosing your Version* above:

    ``` bash
    asdf plugin add python
    asdf install python VERSIONHERE
    asdf global python VERSIONHERE
    ```

1. Confirm Python is properly installed by running `python --version`, which should return the same version you set above

### macOS

[asdf](https://asdf-vm.com/) is a magical tool for easy, side-by-side installation of command line tools on macOS, Python included.

These install instructions assume you are using the default [zsh](https://zsh.sourceforge.io/) Terminal shell included with macOS. (If you didn't specifically change it, you are using zsh in Terminal.)

1. `asdf` on macOS is best installed via [Homebrew](https://brew.sh/), the open-source package manager for macOS. If you don't already have it installed, run the following in Terminal to install:

    ``` bash
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```

1. After `Homebrew` is installed, run the following in Terminal to install `asdf`:

    ``` bash
    brew update
    brew install asdf
    echo -e "\n. $(brew --prefix asdf)/libexec/asdf.sh" >> ${ZDOTDIR:-~}/.zshrc
    ```

1. Close and reopen Terminal
1. Run the following to install Python, replacing `VERSIONHERE` with the three digit version number you found in *Choosing your Version* above:

    ``` bash
    asdf plugin add python
    asdf install python VERSIONHERE
    asdf global python VERSIONHERE
    ```

1. Confirm Python is properly installed by running `python --version`, which should return the same version you set above

### Windows

As asdf cannot (as of 2024) run on Windows, the best way to manage Python versions I'm aware of is [pyenv-win](https://github.com/pyenv-win/pyenv-win).

1. Install `pyenv-win` via [their instructions](https://pyenv-win.github.io/pyenv-win/#installation)
1. Run the following in PowerShell, replacing `VERSIONHERE` with the three digit version number you found in *Choosing your Version* above:

    ``` PowerShell
    pyenv update
    pyenv install VERSIONHERE
    pyenv global VERSIONHERE
    ```

1. Confirm Python is properly installed by running `python --version`, which should return the same version you set above
