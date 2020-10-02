
# 1. Setting up my work platform

- [1. Setting up my work platform](#1-setting-up-my-work-platform)
- [2. **Xcode CommandLine Tools**](#2-xcode-commandline-tools)
- [3. **Keyboard**](#3-keyboard)
  - [3.1. **Increasing the key repeat speed**](#31-increasing-the-key-repeat-speed)
- [4. **Package Manager: Homebrew**](#4-package-manager-homebrew)
- [5. **Terminal: iTerm2**](#5-terminal-iterm2)
  - [5.1. **Installing iTerm2**](#51-installing-iterm2)
  - [5.2. **Setting up a color theme for iTerm2**](#52-setting-up-a-color-theme-for-iterm2)
    - [5.2.1. My Personal Color Theme Recommendations](#521-my-personal-color-theme-recommendations)
      - [5.2.1.1. Optional: Bulk-removing color themes from iTerm2](#5211-optional-bulk-removing-color-themes-from-iterm2)
- [6. **Shell: ZSH**](#6-shell-zsh)
  - [6.1. **Installing ZSH**](#61-installing-zsh)
    - [6.1.1. **Making MacOS use the Homebrew zsh**](#611-making-macos-use-the-homebrew-zsh)
- [7. **Version control: git**](#7-version-control-git)
  - [7.1. **Installing git (with Homebrew)**](#71-installing-git-with-homebrew)
  - [7.2. **Configuring git**](#72-configuring-git)
- [8. **Framework to manage ZSH: OH-MY-ZSH**](#8-framework-to-manage-zsh-oh-my-zsh)
  - [8.1. **Installing OH-MY-ZSH**](#81-installing-oh-my-zsh)
  - [8.2. **Enabling autosuggestions and syntax highlighting on ZSH (through OH-MY-ZSH)**](#82-enabling-autosuggestions-and-syntax-highlighting-on-zsh-through-oh-my-zsh)
- [9. **Setting a theme for ZSH with OH-MY-ZSH: Powerlevel10k (P10k)**](#9-setting-a-theme-for-zsh-with-oh-my-zsh-powerlevel10k-p10k)
  - [9.1. **Installing the Nerd Fonts**](#91-installing-the-nerd-fonts)
  - [9.2. **Enhancing Powerlevel10k**](#92-enhancing-powerlevel10k)
- [10. **Virtual Environments Manager: miniconda**](#10-virtual-environments-manager-miniconda)
  - [10.1. **Installing miniconda**](#101-installing-miniconda)
- [11. **Python**](#11-python)
  - [11.1. **Installing Python**](#111-installing-python)
  - [11.2. **Creating an environment from an environment file**](#112-creating-an-environment-from-an-environment-file)
  - [11.3. **Getting the list of all existing environments**](#113-getting-the-list-of-all-existing-environments)
  - [11.4. **Activating an environment**](#114-activating-an-environment)
  - [11.5. **Listing packages installed in an environment**](#115-listing-packages-installed-in-an-environment)
  - [11.6. Deactivating an environment](#116-deactivating-an-environment)
  - [11.7. Deleting an environment](#117-deleting-an-environment)
- [12. **Text Editor: Visual Studio Code (VSCode)**](#12-text-editor-visual-studio-code-vscode)
  - [12.1. **Installing VSCode**](#121-installing-vscode)
  - [12.2. **Calling VSCode via the command line**](#122-calling-vscode-via-the-command-line)
  - [12.3. **Integrating the VSCode terminal with ZSH**](#123-integrating-the-vscode-terminal-with-zsh)
  - [12.4. **Beautifying VSCode**](#124-beautifying-vscode)
  - [12.5. **Useful Extensions**](#125-useful-extensions)
- [13. **Controlling environments with VSCode**](#13-controlling-environments-with-vscode)
- [14. **Python Linters**](#14-python-linters)
  - [14.1. **Installing the Linters**](#141-installing-the-linters)
  - [14.2. **Using the Linters with VSCode**](#142-using-the-linters-with-vscode)
    - [14.2.1. **Enabling Linters on VSCode**](#1421-enabling-linters-on-vscode)
    - [14.2.2. **Adjusting the Linters verbosity in VSCode**](#1422-adjusting-the-linters-verbosity-in-vscode)

I put a lot of value on the user experience associated with the tools I use for work. The time spent on a project should be as fun as it can be, and, for me, that involves leveraging powerful existing resources to make coding or simply dealing with the machine in more general terms more pleasing. In my case, a more pleasing experience comes with things that allow me to (for instance):

- reduce the amount of memorization;
- have a more appealing and informative interface;
- reduce the amount of text I must type in order to achieve something;
- standardize my code on certain ways;
- enhance the functionality and usefulness of popular tools.

The list above is not exhaustive, but it serves to give you an idea of what the steps outlined here are trying to achieve. I keep in mind that a system may not always be as configurable as I would like, especially when it involves remote servers, but the truth is that a lot of my work is still local, so I still see a lot of value in setting up a more appealing local platform.

In my data science projects, I spend a lot of time with the following tools:

- a *terminal*, for navigation purposes;
- a *text editor*, for coding (mostly);
- a package manager.

In what follows, I outline how I like to setup these tools. I came to learn these setups through multiple blogs, and I hope to consolidate my own personal steps on this README.md file.I have tried my best to include some links to original sources whenever I can remember them. As a final introductory remark, these setups are not set in stone, I will be updating this file whenever new preferred steps are included or removed.

# 2. **Xcode CommandLine Tools**

If you are on a Mac, certain things will not work before you install the *xcode commandline tools*. To install them:

- Open your terminal;
- Run:

```bash
    xcode-select --install
```

To confirm that it worked, enter this on your terminal:
`xcode-select -p`

You should see something like `/Library/Developer/CommandLineTools`.

# 3. **Keyboard**

We will be typing a lot, so we want to make the keyboard experience more pleasant.

## 3.1. **Increasing the key repeat speed**

We will be pressing some keys often -- for instance, *delete* to erase parts of lines we type on the terminal. To make this process faster, click on the  icon on the top left, then:

-  ⟶ System Preferences ⟶ Keyboard ⟶ Keyboard
- Set *Key Repeat* to *Fast* and *Delay Until Repeat* to *Short*

# 4. **Package Manager: Homebrew**

[Homebrew](https://brew.sh) is a package manager that will make our lives easier when it comes to... managing packages. Run this on the terminal to install it.

```bash
    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Hint: this [link](https://osxdaily.com/2018/07/05/where-homebrew-packages-installed-location-mac/) has more details on how to find the Homebrew packages installed on Mac.

# 5. **Terminal: iTerm2**

The standard terminal was useful so far, but in my opinion it feels pretty flat. I do not find much fun in spending time with it. Thanks to a co-worker, I came across [iTerm2](https://iterm2.com), which I believe is available on MacOS, but not on Windows, unfortunately. (It would be nice to know of an equally good alternative for Windows, as some of my work has to be done on that platform).

## 5.1. **Installing iTerm2**

- Run the following on your terminal:

```bash
    brew cask install iterm2
```

## 5.2. **Setting up a color theme for iTerm2**

To make iTerm2 look more appealing, I like to have some color theme options. You can find a few [here](https://iterm2colorschemes.com).

The themes are encoded in *.itermcolor* files. To import a custom theme to iTerm2:

- Open iTerm2;
- iTerm2 ⟶ Preferences ⟶ Profiles ⟶ Colors;
- On the Colors tab, you will see *Color Presets* on your bottom right;
- Color Presets ⟶ Import ⟶ <file.itermcolor>

Hint: you can import multiple themes at once by having them on the same folder and pressing Shift + ↓ or Shift + ↑ after selecting a file. I do not suggest importing too many themes at once because iTerm2 does not have an official way to delete multiple themes at once.

### 5.2.1. My Personal Color Theme Recommendations

- [Ayu](https://github.com/hwyncho/ayu-iTerm)

#### 5.2.1.1. Optional: Bulk-removing color themes from iTerm2

[Here](https://gist.github.com/kecebongsoft/11312110) is a way to get rid of too many color terms for iTerm2 at once. However, I found it easier to follow the instructions [here](https://iterm2.com/faq.html) and restore iTerm2 to its default settings by running:

```bash
defaults delete com.googlecode.iterm2
```

(I am not entirely sure whether this must be done while at *~/Library/Preferences/*, but you can double-check.)

# 6. **Shell: ZSH**

In Unix, the shell is the command interpretor. A more powerful shell should make our experience with the terminal more pleasant. Though *Bash* seems to be the standard shell for many systems, I have been introduced to an alternative shell, *Z shell* (or *ZSH* for short) years ago. It is supposed to have extended capabilities over Bash, but I am not knowledgeable enough to defend the claim. That said, ZSH has worked fairly well for me, so I am going to cover it here.

## 6.1. **Installing ZSH**

- On your terminal, simply run:

```bash
brew install zsh
```

Confirm that it was installed by running: `ls -la /usr/local/bin/zs*`.

### 6.1.1. **Making MacOS use the Homebrew zsh**

If you are using the most recent versions of MacOS, it is likely that you already have ZSH on your system, even before the installation. If you run `which zsh` before the installation by homebrew, the output will most likely be `/bin/zsh`. That is the MacOS ZSH. If `zsh` is calling the Homebrew version, you should most likely see `/usr/local/bin/zsh`.

After I installed zsh with homebrew, `which zsh` gives me the path associated with homebrew. However, when running echo $SHELL, I still get `/usr/bin` as the output. This suggests that the shell used is still the standard MacOS zsh. That is further corroborated by inspecting the file `/etc/shells` (you can run `cat /etc/shells` to do that). This file contains a list of possible shells that can be used by the OS. I do not see the Homebrew zsh listed there, so we need to fix that.

To make the Homebrew zsh the default shell:

- Following this [page](https://rick.cogley.info/post/use-homebrew-zsh-instead-of-the-osx-default/), run:

```bash
sudo dscl . -create /Users/$USER UserShell /usr/local/bin/zsh
```

- Open the file `/etc/shells` (this file lists all shells available) and add `/usr/local/bin/zsh` to a new line at the end

(Another approach that would have achieved the same effect would be to edit `/etc/shells` first to add `/usr/local/bin/zsh`, and then running `chsh -s /usr/local/bin/zsh`. The command chsh is used for **ch**anging **sh**ells.)

- Restart your terminal

In the end, make sure that the commands `which zsh` and `echo $SHELL` output the Homebrew zsh path, and that this path is `/etc/shells`.

# 7. **Version control: git**

Though MacOS comes with a git, I am going to use the version provided by brew.

## 7.1. **Installing git (with Homebrew)**

- Run the command

```sh
brew install git
```

- Restart the terminal

To confirm that it worked, run `which git`. You should see `/usr/local/bin/git`.

## 7.2. **Configuring git**

To config your git username and email, run the following commands

- ```bash
  git config --global user.name [your name here]
  ```

- ```bash
  git config --global user.email [your email address here]
  ```

To check that the changes took effect, inspect the file `.gitconfig` in your home directory.

# 8. **Framework to manage ZSH: OH-MY-ZSH**

To further leverage the capabilities of zsh, we now install ['Oh-My-Zsh'](https://github.com/ohmyzsh/ohmyzsh), a community-driven framework for managing our zsh configuration.

## 8.1. **Installing OH-MY-ZSH**

- Run the following command on the terminal:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

You should now have a folder with the path `$HOME/.oh-my-zsh`, and also a zsh configuration file, `$HOME/.zshrc` . This file should have a line that sets an environmental variable: `export ZSH="/Users/hudson/.oh-my-zsh"` The variable $ZSH$ is (presumably) the bridge between zsh and oh-my-zsh.

## 8.2. **Enabling autosuggestions and syntax highlighting on ZSH (through OH-MY-ZSH)**

- Run the following lines to add the zsh-autosuggestions and zsh-syntax-highlighting packages to the set of plugins by oh-my-zsh:

```bash
    sudo git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
    sudo git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

- Add the plugins to the `.zshrc` file:
  plugins=(
      ...
      zsh-autosuggestions
      zsh-syntax-highlighting
      ...
  )

# 9. **Setting a theme for ZSH with OH-MY-ZSH: Powerlevel10k (P10k)**

One of the things zsh supports is themes. Themes interact with our terminal, and will help make it more appealing, and also display *useful* information organically (here are a few possibilities: how much memory/CPU is being used; the current git branch in a local directory; whether files tracked by git have been changed).

My favourite theme is [Powerlevel10k](https://github.com/romkatv/powerlevel10k). It is actually possible to install it without OH-MY-ZSH (and in fact that is [how](https://github.com/romkatv/powerlevel10k#manual) I did it, at first). However, since oh-my-zsh is supposed to manage our configurations, we will take the approach of using oh-my-zsh.

- Start with the command below (which adds the P10K files to the oh-my-zsh custom themes folder):

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

- Now modify the config file `~/.zshrc` and set `ZSH_THEME="powerlevel10k/powerlevel10k`";
- Restart the terminal for this to take effect.

You may be presented with the powerlevel10k configuration wizard. Here are my choices for it:
*nerdfont-complete + powerline, small icons, rainbow, unicode, 12h time, angled separators, sharp heads, flat tails, 2 lines, disconnected, no frame, sparse, many icons, concise, transient_prompt, instant_prompt=verbose*.

After running the configuration wizard, you should now have the file `~/.p10k.zsh`. This file contains configuration details regarding the theme itself, and can be customized directly.

Hint: you can trigger the configuration wizard with the command `p10k configure`. I believe that running this overwrites the config file `~/.p10k.zsh`, so make a copy of it if you customized it extensively (the wizard may do that already, but I do not remember for sure.)

## 9.1. **Installing the Nerd Fonts**

If you follow the Powerlevel10k configuration wizard, a nerd font should be installed during the process. You can find more fonts [here](https://github.com/ryanoasis/nerd-fonts). The nerd fonts are fonts patched with a high number of glyphs, which are used by Powerlevel10k to enhance the terminal looks. The font can be changed in the settings for iTerm2.

## 9.2. **Enhancing Powerlevel10k**

 The `~./p10k.zsh` file can be used to customized the prompts displayed on the left and on the right. Look up *POWERLEVEL9K_LEFT_PROMPT_ELEMENTS* and *POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS* and add or remove prompts as desired.

# 10. **Virtual Environments Manager: miniconda**

To execute our projects, we will have to install Python and other packages. One problem that quickly arises is that different projects may ask for different versions of the same package. The way around that is to create environments for each project. With miniconda, we can do just that.

Remark: there are few other tools to manage environments. For instance, we also have pyenv and virtualenv. Python3 also has a native module called [venv](https://docs.python.org/3/library/venv.html), whose purpose is to create virtual environments. We will stick to miniconda because it seems to be a popular option amongst data scientists. Miniconda can also be installed through Homebrew, but I am not completely sure whether the final result is equivalent.

## 10.1. **Installing miniconda**

To install miniconda, access this [page](https://docs.conda.io/projects/conda/en/latest/user-guide/install/macos.html) and follow the instructions. (There are some special steps at the end because of zsh.)

# 11. **Python**

Python is a popular language for developing data science models. The Python version that comes with MacOS is quite obsolete, so we will install a newer one with Homebrew.

## 11.1. **Installing Python**

It is simple to install python using Homebrew with the command `brew install python`. However, we do not recommend this approach, as different projects may ask for different python versions. Instead, we will manage Python and its packages through miniconda, following this [guide](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).

This is done essentially through a `.yml` file, which will contain instructions regarding the python version and required packages for a given environment. Here is what a minimum environment file would look like:

```yml
name: ml
channels:
- defaults
- conda-forge
dependencies:
- python=3.7
```

## 11.2. **Creating an environment from an environment file**

To create the environment from that file -- say its name is `environment.yaml` -- , run: `conda env create -f environment.yaml`
With this approach, an environment will be created at `~/miniconda/envs/ml`. It may be preferable to set the environment inside the project folder itself. To do so, change the command to

```sh
conda env create --prefix ./env -f environment.yaml
```

Remark: it seems like, whenever `--prefix` is used, that actually takes precedence over the environment. Thus, we cannot refer to the environment through `--name` in commands, and must stick to `--prefix` while passing the full environment path.

In this example, the steps above will create an environment with Python 3.7 in our project folder.

(A very minimal way of creating an environment that could be used by multiple projects with a given python version is to run `conda create --name py35 python=3.5`. The conda base environment should also come with python and pip, which is a python package manager)

## 11.3. **Getting the list of all existing environments**

- To display all existing environments, run the command:

```sh
  conda env list
```

## 11.4. **Activating an environment**

- To activate an environment inside, say, *./env*, run:

```sh
  conda activate ./env
```

You can double check that the environment was activated by running conda env list and checking which environment is singled out with a star (\*) symbol. If you installed Python with the environment file, you can also run `which python` to check that the environment path appears in the output.

## 11.5. **Listing packages installed in an environment**

- With an environment activated, run:

```sh
  conda list
```

- If the environment is not activated, you can still run

```sh
  conda list --prefix <path_to_environment>
```

## 11.6. Deactivating an environment

- To revert to the base environment, run:

```sh
  conda deactivate
```

## 11.7. Deleting an environment

- To completely remove an environment, run:

```sh
conda remove --prefix <environment_path> --all
```

# 12. **Text Editor: Visual Studio Code (VSCode)**

One of the most important tools for a data scientist is the text editor. If using an editor remotely, you may not have much choice but to use whatever is available on the server. However, when working locally, I will go for the option that provides me the most comfort. There are many editors out there. In the context of data science work, I have had the chance ot use *Sublime*, *Atom* and *Visual Studio Code*. You can look up online for major differences between these editors -- and other options -- to make your call for an editor. I personally use VSCode because it has about the same features I have found in Sublime and Atom, but also comes with the unique feat of being able to run Jupyter notebooks inside the editor. I really enjoy this aspect, as it gives me the typical benefits of Jupyter coupled with any enhancements provided by the editor.

## 12.1. **Installing VSCode**

Follow this [link](https://code.visualstudio.com/docs/setup/mac) for installing VSCode on MacOS.

## 12.2. **Calling VSCode via the command line**

- With VSCode open, type *Command + Shift + P* to call the command palette;
- Search for "Shell Command: Install 'code' command in PATH", and select it;
- Restart your terminal and you should now be able to open VSCode with the command *code*.

## 12.3. **Integrating the VSCode terminal with ZSH**

VSCode has an integrated terminal. To bring it up, press *Control + `. To integrate it with zsh and our previous configurations:

- call the command palette (*Command + Shift + P*) and look up for *Preferences: Open Settings (JSON)*
- add the following to the JSON:

  ```json
      "terminal.integrated.shell.osx": "/usr/local/bin/zsh",
      "terminal.integrated.fontFamily": "MesloLGS NF"
  ```

The first line contains the path to the zsh installed by Homebrew; the second line is the font type, which you can choose at your convenience (make sure it exists in your systems and that it supports the glyphs associated with P10k if you are using that theme).

## 12.4. **Beautifying VSCode**

We can rely on extensions to improve the looks of VSCode. Here are some extensions for improving visuals I recommend:

- Material Icon Theme
- Ayu

The icon theme can be changed through by command palette by looking up "File Icon Theme").

## 12.5. **Useful Extensions**

Here is a list of useful extensions and what to expect from them:

|Extension|Description|
|---|---|
|markdownlint|Linter for Markdown, to ensure some format standards (I used it to write this file!)|
|Markdown All in One|Provides various resources to enhance writing markdown content|
|Markdown Preview Enhanced|Enhances markdown preview functionality inside VSCode|
|Python|VSCode extension to support coding in Python|
|Visual Studio IntelliCode|AI-driven Intellisense for VSCode}|
|Trailing Spaces| Highlights trailing space for easy removal|
|Python Docstring Generator|Extension with docstring templates for python functions|
|Code Runner|Allows one to run code snippets for multiple languages|
|Better Comments|Helps with categorizing comments|
|GitLens|Allows one to visualize code authorship (and much more) inside VSCode|
|Path Intellisense|Completes filenames|

In the following links, you can find a few more sources:
<https://medium.com/issuehunt/10-visual-studio-code-extensions-for-python-development-de0be51bbeed>
<https://www.shopify.ca/partners/blog/best-visual-studio-code-extensions>

# 13. **Controlling environments with VSCode**

Just to recapitulate, you can set an environment folder named `env` inside your project folder by running `conda env create --prefix ./env -f environment.yaml`, where `environment.yaml` is the file with the required packages. (If something goes wrong, you can remove the environment by running `conda remove --prefix ./env --all`).

If the environment is already in place, you can select it in VSCode by calling the command palette and looking for *"Python: Select Interpreter"*. Then, assuming your environment is the *env* folder inside your project, find the path `./env/bin/pythonx.x`, where the python version will depend on what you have specified on the environment file (do not forget to include python!). You can further confirm that this has worked by examining the local settings JSON for the variable *python.linting.pythonPath*, which should specify the python of that particular environment.

# 14. **Python Linters**

A linter is a tool that analyzes code and flag errors and violations of certain stylistic conventions. They are helpful in spotting bugs and errors earlier on, and in ensuring that the code conforms to some standards, which may make it easier to read and follow by peers.

In Python, there are several linters. This [page](https://github.com/vintasoftware/python-linters-and-code-analysis) contains a very good summary of different linters and their functionalities in Python. Not all of them do the same thing, so I recommend using multiple linters. I have not yet figured out the ideal ones to have around, so I am currently combining *Pylint* and *Flake8*. I am also considering enabling *pydocstyle*, since it looks like its functionality is to inspect docstrings, as opposed to the code itself.

## 14.1. **Installing the Linters**

Since these linters are essentially python packages, they would be environment-dependent. We are going to install them at the conda base environment and discuss in the next sections how to configure VSCode to access these linters.

Disclaimer: I tried making the linters environment-agnostic, i.e., making environments use global linters, but it seems like VSCode does not support that (for example, it causes pylint to fail when checking for whether packages are present when being imported).

To install the linters on a given environment:

- Make sure that that environment is active by running `coda deactivate` and `coda activate <environment_path_or_name>`

- Confirm that the commands `which python` and `which pip` output paths are associated with that environment

- To install flake8, run `conda install -c conda-forge flake8`

- To install pylint, run `conda install -c conda-forge pylint`

- To install pydocstyle, run `conda install -c conda-forge pydocstyle`

To confirm that the packages have been installed, run `python` on your terminal and `import <linter_name>` to check that the packages are now available. You should also be able to see the packages at a folder named `bin` inside your environment folder

## 14.2. **Using the Linters with VSCode**

Though linters can be run directly (for example, to examine a file called `mycode.py` with Flake8, run `flake8 mycode.py`), I find them more useful when their functionality is coupled with a text editor that leverages their diagnosis and displays it on the code itself. To take advantage of that, we must enable linters on VSCode.

### 14.2.1. **Enabling Linters on VSCode**

- call the command palette (*Command + Shift + P*), look up *Python: Enable Linting* and click on it

Remark: if you do the above while having a folder/project already open in VSCode, this might modify the local settings (settings which are applicable only to that project). To make sure whether it was done globally, use the command palette to open the global JSON settings and make sure there is a line stating *"python.linting.enabled": true*.

- under the command palette again, look up for Python: Select Linter. You should see options like Pylint, Flake8 and others; pick one, which will apply this setting to the local settings JSON if a project is open. If you want that particular setting to be global, open the global JSON settings and make sure a line like *"python.linting.pylintEnabled": true* or *"python.linting.flake8Enabled": true* is around

- if you want to have multiple linters active, use the settings JSON (either global or local) directly; for example, to have pylint, flake8 and pydocstyle enabled, have the parameters *python.linting.pylintEnabled*, *python.linting.flake8Enabled* and *python.linting.pydocstyle* all set to true.

- Install pylint, flake8 and pydocstyle (see the previous section) in the environment associated with the chosen Python interpreter

### 14.2.2. **Adjusting the Linters verbosity in VSCode**

The verbosity of the linters Pylint, flake8 and pydocstyle use the following parameters on the settings JSON: *python.linting.pylintArgs*, *python.linting.flake8Args* and *python.pydocstyleArgs*", respectively (more info for additional linters can be found on the VSCode page). I usually set *python.linting.pylintArgs": ["--enable=F,E,W,C,R"]*, where the letters correspond to different kinds of messages pylint may display (F: fatal; E: error; W: warning; C: convention; R: refactoring). For flake8, the options are F, E and W. For pycodestyle, the options are E and W.

Here is a summary of what I currently have on my global config JSON in terms of linters:

```json
    "python.linting.enabled": true,
    "python.linting.pylintEnabled": true,
    "python.linting.flake8Enabled": true,
    "python.linting.pydocstyleEnabled": true,
    "python.linting.pylintArgs": ["--enable=F,E,W,C,R"],
    "python.linting.flake8Args": ["--enable=F,E,W"],
    "python.linting.pydocstyleArgs": ["--enable=E,W"]
  ```
