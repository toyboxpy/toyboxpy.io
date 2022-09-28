---
title: Installing a better Python
author: DidierMalenfant
redirect_from: /blog/installing-python
---
**toybox.py** requires at least [**Python**](https://python.org) 3.7 and you need access to [**pip**](https://pypi.org/project/pip/), the **Python** package manager. Here's how to easily set this up:

- [Installing Python on macOS](#installing-python-on-macos)
- [Installing Python on Linux](#installing-python-on-linux)
- [Installing Python on Windows](#installing-python-on-windows)

<br>

### Installing Python on macOS
<p></p>
Open a terminal window. All the commands listed here will be typed directly there.

If you haven't already done so, start by installing [**Homebrew**](https://brew.sh) which will let us easily install the packages we need:

<div class="copyable"> {%- highlight bash -%}
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
{%- endhighlight -%} </div><p></p>

Then we need to install [**pyenv**](https://github.com/pyenv/pyenv) which will let us manage different version of **Python**:

<div class="copyable">{%- highlight bash -%}
    brew install pyenv
{%- endhighlight -%}</div><p></p>

In order to load **pyenv** automatically when opening a terminal window, you need to add the following line to your shell startup file (typically `~/.bashrc` or `~/.zshrc` depending on which shell is the default on your machine):

```bash
# -- pyenv Setup
eval "$(pyenv init -)"
```

Close this terminal window then re-open another one for the changes to take effect. You should now be able to list which versions of **Python** are available by typing:

<div class="copyable">{%- highlight bash -%}
    pyenv install --list | grep " 3\."
{%- endhighlight -%}</div><p></p>

This will give you a list such as:

```console
...
3.10.1
3.10.2
3.10.3
3.10.4
3.10.5
3.10.6
```

Now install and set as global version the latest stable version of **Python** from the list (your version may vary from this one if newer versions have been released):

<div class="copyable">{%- highlight bash -%}
    pyenv install -v 3.10.6
{%- endhighlight -%}</div><p></p>
<div class="copyable">{%- highlight bash -%}
    pyenv global 3.10.6
{%- endhighlight -%}</div><p></p>

And finally make sure you're running the latest version of **Python**'s package manager **pip**:

<div class="copyable">{%- highlight bash -%}
    python -m pip install --upgrade pip
{%- endhighlight -%}</div><p></p>

<br>

### Installing Python on Linux
<p></p>

The instructions below apply to **Ubuntu Linux** 18.04 and 20.04. You may need to tweak them for other distributions.

Open a terminal window. All the commands listed here will be typed directly there.

If you haven't already done so, start by installing [**Homebrew**](https://brew.sh) which will let us easily install the packages we need:

<div class="copyable"> {%- highlight bash -%}
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
{%- endhighlight -%} </div><p></p>

During installation, you'll need to select the option to install **Homebrew** in `/home/linuxbrew/.linuxbrew` which is the recommended location.

You then need to install some essential packages for building dependencies.

<div class="copyable"> {%- highlight bash -%}
    sudo apt-get install build-essential zlib1g-dev
{%- endhighlight -%} </div><p></p>

In order to setup **Homebrew** automatically when opening a terminal window, you need to add the following line to your shell startup file (for example `.profile`):

```bash
# set PATH, MANPATH, etc., for Homebrew.
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

Close this terminal window then re-open another one for the changes to take effect. You should now be able to install **pyenv**.

<div class="copyable"> {%- highlight bash -%}
    brew install pyenv
{%- endhighlight -%} </div><p></p>

In order to load **pyenv** automatically when opening a terminal window, you need to add the following line to your shell startup file (for example `.profile`)

```bash
# Init pyenv.
eval "$(pyenv init -)"
```

Once again close this terminal window then re-open another one for the changes to take effect. You should now be able to list which versions of **Python** are available by typing:

<div class="copyable">{%- highlight bash -%}
    pyenv install --list | grep " 3\."
{%- endhighlight -%}</div><p></p>

This will give you a list such as:

```console
...
3.10.1
3.10.2
3.10.3
3.10.4
3.10.5
3.10.6
```

Now install and set as global the latest stable version of **Python** from the list (your version may vary from this one if newer versions have been released):

<div class="copyable"> {%- highlight bash -%}
    pyenv install -v 3.10.6
{%- endhighlight -%} </div><p></p>

<div class="copyable"> {%- highlight bash -%}
pyenv global 3.10.6
{%- endhighlight -%} </div><p></p>

**Note:** Depending on your distribution, you can get some errors during installation. If so, you can check out <a href="https://code.luasoftware.com/tutorials/linux/ubuntu-pyenv-build-python-37-common-error/">this article</a> on common errors with **Ubuntu**.

And finally make sure you're running the latest version of **Python**'s package manager **pip**:

<div class="copyable">{%- highlight bash -%}
    python -m pip install --upgrade pip
{%- endhighlight -%}</div><p></p>

<br>

### Installing Python on Windows
<p></p>

The instructions below apply to **Windows** 7+ and some were originally found at [HGTP](https://docs.python-guide.org/starting/install3/win/).

First, make sure that you have [Git](https://git-scm.com/download/win) installed on your machine. Unless you know you need one, make sure you do **NOT** choose to use a credential helper during **Git**'s install.

Then you'll need to install **Chocolatey** which is very much like **Homebrew** on **macOS** and **Linux**.

You'll need an administrative **Powershell**. Click on the Windows/Start Menu and go to `Windows Powershell` section. Right click on `Windows Powershell` and select `More->Run as administrator` in the contextual menu.

Then type the following to install **Chocolatey**:

<div class="copyable-windows">{%- highlight bash -%}
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
{%- endhighlight -%}</div><p></p>

You can now close the **Powershell** administrative window and open a regular one.

Then install Python (**Chocolatey** installs **Python** 3 as the default):

<div class="copyable-windows">{%- highlight bash -%}
choco install python
{%- endhighlight -%}</div><p></p>

Close the **Powershell** window and open a new one for the changes to take effect.

And finally make sure you're running the latest version of **Python**'s package manager **pip**:

<div class="copyable-windows">{%- highlight bash -%}
    python -m pip install --upgrade pip
{%- endhighlight -%}</div><p></p>

