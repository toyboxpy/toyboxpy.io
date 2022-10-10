---
title: Installing Python
author: DidierMalenfant
redirect_from: /blog/installing-python
---
**toybox.py** requires at least [**Python**](https://python.org){:target="_blank"} 3.7 and you need access to [**pip**](https://pypi.org/project/pip/){:target="_blank"}, the **Python** package manager. You can check which version you currently have, if any, with:

<div class="copyable"> {%- highlight bash -%}
python --version
{%- endhighlight -%} </div><p></p>

On **macOS** or **Linux** is this returns a 2.x version, try this instead:

<div class="copyable"> {%- highlight bash -%}
python3 --version
{%- endhighlight -%} </div><p></p>

To check if you have **pip** installed you can do this:

<div class="copyable"> {%- highlight bash -%}
pip --version
{%- endhighlight -%} </div><p></p>

Here's how you can install a newer/supported version of **Python** and **pip**:

- [Installing on macOS](#installing-python-on-macos)
- [Installing on Linux](#installing-python-on-linux)
- [Installing on Windows](#installing-python-on-windows)

<br>

### Installing on macOS
<p></p>

Open a terminal window. All the commands listed here will be typed directly there.

First, make sure that you have the developer tools installed on your machine.

<div class="copyable">{%- highlight bash -%}
git --version
{%- endhighlight -%}</div><p></p>

If running this command offers to you install the developer tools, say yes.

If the command returns the current version for **git**, make sure you also have **Python** installed:

<div class="copyable">{%- highlight bash -%}
python3 --version
{%- endhighlight -%}</div><p></p>

This should also report the current version of **Python** which should be higher or equal to `3.7`.

Finally make sure you're running the latest version of **Python**'s package manager **pip**:

<div class="copyable">{%- highlight bash -%}
python -m pip install --upgrade pip
{%- endhighlight -%}</div><p></p>

If you get a message like this one:

```
WARNING: The scripts pip, pip3 and pip3.9 are installed in '/Users/admin/Library/Python/3.9/bin' which is not on PATH.
```

Then do the following, keeping in mind you may need to replace the version number for **Python** with the one given in your warning message.

If the top of your terminal window has `bash` in it (older **macOS** versions before **Catalina**), do:

<div class="copyable">{%- highlight bash -%}
echo "# Add Python to path" >> .bashrc
{%- endhighlight -%}</div><p></p>
<div class="copyable">{%- highlight bash -%}
echo 'export PATH=$PATH:/Users/admin/Library/Python/3.9/bin' >> .bashrc
{%- endhighlight -%}</div><p></p>

and if the top of your terminal Window has `zsh` in it (**macOS Catalina** and later), do:

<div class="copyable">{%- highlight bash -%}
echo "# Add Python to path" >> .zshrc
{%- endhighlight -%}</div><p></p>
<div class="copyable">{%- highlight bash -%}
echo 'export PATH=$PATH:/Users/admin/Library/Python/3.9/bin' >> .zshrc
{%- endhighlight -%}</div><p></p>

Then close the terminal window and re-open it for the changed to take effect.

<br>

### Installing on Linux
<p></p>

Since on **Linux** many services rely on the installed version of **Python**, you have to be careful when trying to upgrade to a newer version and do it in a way that doesn't affect any other versions.

The instructions below apply to **Ubuntu Linux** 18.04 and 20.04. You may need to tweak them for other distributions. You can find a detailed guide on installing Python 3 and pip over at [RealPython](https://realpython.com/installing-python/){:target="_blank"}.

Open a terminal window. All the commands listed here will be typed directly there.

First make sure your list of packages is up to date:

<div class="copyable">{%- highlight bash -%}
sudo apt-get update
{%- endhighlight -%}</div><p></p>

Install **Python** 3.8 (If you're running **Ubuntu Linux** 20.04 you already have it and you can skip this step):

<div class="copyable">{%- highlight bash -%}
sudo apt-get install python3.8
{%- endhighlight -%}</div><p></p>

Then install the **Python** package manager `pip`:

<div class="copyable">{%- highlight bash -%}
sudo apt-get install python3-pip
{%- endhighlight -%}</div><p></p>

And finally make sure you're running the latest version of **Python**'s package manager **pip**:

<div class="copyable">{%- highlight bash -%}
python3.8 -m pip install --upgrade pip
{%- endhighlight -%}</div><p></p>

If you get a warning about the scripts pip, pip3 and pip3.8 not being in your PATH you can safely ignore it.

Close the terminal and reopen it for the changes to take effect.

<br>

### Installing on Windows
<p></p>

First, make sure that you have [**Git**](https://git-scm.com/download/win){:target="_blank"} installed on your machine. Then install the latest release of [**Python 3**](https://www.python.org/downloads/windows/){:target="_blank"}. Note that with **Windows** 7 you may not be able to install any version beyond **Python** 3.7.

**Make sure to check** `Add Python <version> to path` at the beginning and `Disable Path length limit` at the end of the installation.

Finally open a **Windows Terminal** or **Powershell** and make sure you're running the latest version of **Python**'s package manager **pip**:

<div class="copyable-windows">{%- highlight bash -%}
python -m pip install --upgrade pip
{%- endhighlight -%}</div><p></p>
