# **Setting up my work platform**

- [**Setting up my work platform**](#setting-up-my-work-platform)
  - [**Xcode CommandLine Tools**](#xcode-commandline-tools)
  - [**Keyboard**](#keyboard)
    - [**Increasing the key repeat speed**](#increasing-the-key-repeat-speed)
  - [**Package Manager: Homebrew**](#package-manager-homebrew)
  - [**Terminal: iTerm2**](#terminal-iterm2)
    - [**Installing iTerm2**](#installing-iterm2)
    - [**Setting up a color theme for iTerm2**](#setting-up-a-color-theme-for-iterm2)
      - [My Personal Color Theme Recommendations](#my-personal-color-theme-recommendations)
      - [Optional: Bulk-removing color themes from iTerm2](#optional-bulk-removing-color-themes-from-iterm2)
  - [**Shell: ZSH**](#shell-zsh)
    - [**Installing ZSH**](#installing-zsh)
  - [**Installing OH-MY-ZSH**](#installing-oh-my-zsh)
    - [Enabling autosuggestions and syntax highlighting on ZSH (through OH-MY-ZSH)](#enabling-autosuggestions-and-syntax-highlighting-on-zsh-through-oh-my-zsh)
    - [**Setting a theme for ZSH: Powerlevel10k**](#setting-a-theme-for-zsh-powerlevel10k)
      - [**Installing the Nerd Fonts**](#installing-the-nerd-fonts)
      - [**Enhancing Powerlevel10k**](#enhancing-powerlevel10k)
  - [**Python**](#python)
  - [**Text Editor: Visual Studio Code (VSCode)**](#text-editor-visual-studio-code-vscode)
    - [**Installing VSCode**](#installing-vscode)

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

## **Xcode CommandLine Tools**

If you are on a Mac, certain things will not work before you install the *xcode commandline tools*. To install them:

- Open your terminal;
- Run:

```bash
    xcode-select --install
```

To confirm that it worked, enter this on your terminal:

```bash
    xcode-select -p
```

You should see something like */Library/Developer/CommandLineTools*.

## **Keyboard**

We will be typing a lot, so we want to make the keyboard experience more pleasant.

### **Increasing the key repeat speed**

We will be pressing some keys often -- for instance, *delete* to erase parts of lines we type on the terminal. To make this process faster, click on the  icon on the top left, then:

-  ⟶ System Preferences ⟶ Keyboard ⟶ Keyboard
- Set *Key Repeat* to *Fast* and *Delay Until Repeat* to *Short*
  
## **Package Manager: Homebrew**

[Homebrew](https://brew.sh) is a package manager that will make our lives easier when it comes to... managing packages. Run this on the terminal to install it.

```bash
    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## **Terminal: iTerm2**

The standard terminal was useful so far, but in my opinion it feels pretty flat. I do not find much fun in spending time with it. Thanks to a co-worker, I came across [iTerm2](https://iterm2.com), which I believe is available on MacOS, but not on Windows, unfortunately. (It would be nice to know of an equally good alternative for Windows, as some of my work has to be done on that platform).

### **Installing iTerm2**

Run the following on your terminal:

```bash
    brew cask install iterm2
```

### **Setting up a color theme for iTerm2**

To make iTerm2 look more appealing, I like to have some color theme options. You can find a few [here](https://iterm2colorschemes.com).

The themes are encoded in *.itermcolor* files. To import a custom theme to iTerm2:

- Open iTerm2;
- iTerm2 ⟶ Preferences ⟶ Profiles ⟶ Colors;
- On the Colors tab, you will see *Color Presets* on your bottom right;
- Color Presets ⟶ Import ⟶ <file.itermcolor>

Hint: you can import multiple themes at once by having them on the same folder and pressing Shift + ↓ or Shift + ↑ after selecting a file. I do not suggest importing too many themes at once because iTerm2 does not have an official way to delete multiple themes at once.

#### My Personal Color Theme Recommendations

- [Ayu](https://github.com/hwyncho/ayu-iTerm)

#### Optional: Bulk-removing color themes from iTerm2

[Here](https://gist.github.com/kecebongsoft/11312110) is a way to get rid of too many color terms for iTerm2 at once. However, I found it easier to follow the instructions [here](https://iterm2.com/faq.html) and restore iTerm2 to its default settings by running:

```bash
defaults delete com.googlecode.iterm2
```

(I am not entirely sure whether this must be done while at *~/Library/Preferences/*, but you can double-check.)

## **Shell: ZSH**

In Unix, the shell is the command interpretor. A more powerful shell should make our experience with the terminal more pleasant. Though *Bash* seems to be the standard shell for many systems, I have been introduced to an alternative shell, *Z shell* (or *ZSH* for short) years ago. It is supposed to have extended capabilities over Bash, but I am not knowledgeable enough to defend the claim. That said, ZSH has worked fairly well for me, so I am going to cover it here.

### **Installing ZSH**

On your terminal, simply run:

```bash
brew cask install zsh
```

Confirm that it was installed by running:

```bash
ls -la /usr/local/bin/zs*
```

If you are using the most recent versions of MacOS, it is likely that you already have ZSH on your system, even before the installation. If you run *which zsh* before the installation by homebrew, the output will most likely be */bin/zsh*. That is the MacOS ZSH. If *zsh* is calling the Homebrew version, you should most likely see */usr/local/bin/zsh*.

After I installed zsh with homebrew, I am getting the path associated with homebrew. However, when running echo $SHELL, I am still getting */usr/bin* as the output. This suggests that the shell being used is still the standard MacOS zsh. That is further corroborated by inspecting the file */etc/shells* (you can run *cat /etc/shells* to do that). This file contains a list of possible shells that can be used by the OS. I do not see the Homebrew zsh listed there, so we need to fix that. 

To do that, I followed the method outlined in this [page](https://rick.cogley.info/post/use-homebrew-zsh-instead-of-the-osx-default/) and ran:

```bash
sudo dscl . -create /Users/$USER UserShell /usr/local/bin/zsh
```

After restarting the terminal, you should see that $SHELL now is */usr/local/bin/zsh* and that the command *which zsh* also prints */usr/local/bin/zsh*. That said, this method somehow does not include this path on the */etc/shell* file, so I am not entirely sure whether there is a downside to this method. However, the */etc/shells* file contains a comment that states that *Ftpd will not allow users using one of the listed shells to connect*. Thus, to be on the safe side I also added the Homebrew zsh path to */etc/shells*.)

(Another approach that would have achieved the same effect would be to edit */etc/shell* first to add */usr/local/bin/zsh*, and then running *chsh -s /usr/local/bin/zsh*. The command chsh is used for **ch**anging **sh**ells.)

In the end, make sure that the commands *which zsh* and *echo $SHELL* output the Homebrew zsh path, and that this path is */etc/shells*.

## **Installing OH-MY-ZSH**

To further leverage the capabilities of zsh, we now install ['Oh-My-Zsh'](https://github.com/ohmyzsh/ohmyzsh), a community-driven framework for managing our zsh configuration. To install it, I ran the following command on the terminal:

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

You should now have a folder with the path $HOME/.oh-my-zsh, and also a zsh configuration file, $HOME/.zshrc . This file should have a line that sets an environmental variable: *export ZSH="/Users/hudson/.oh-my-zsh"* The variable $ZSH$ is (presumably) the bridge between zsh and oh-my-zsh.

### Enabling autosuggestions and syntax highlighting on ZSH (through OH-MY-ZSH)

- Run the following lines to add the zsh-autosuggestions and zsh-syntax-highlighting packages to the set of plugins by oh-my-zsh:

```bash
    sudo git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestion
    sudo git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

- Add the plugins to the *.zshrc* file:
  plugins=(
      ...
      zsh-autosuggestions
      zsh-syntax-highlighting
      ...
  )

### **Setting a theme for ZSH: Powerlevel10k**

One of the things zsh supports is themes. Themes interact with our terminal, and will help make it more appealing, and also display *useful* information organically (here are a few possibilities: how much memory/CPU is being used; the current git branch in a local directory; whether files tracked by git have been changed).

My favourite theme is [Powerlevel10k](https://github.com/romkatv/powerlevel10k). It is actually possible to install it without OH-MY-ZSH (and in fact that is [how](https://github.com/romkatv/powerlevel10k#manual) I did it, at first). However, since oh-my-zsh is supposed to manage our configurations, we will take the path of using oh-my-zsh. Start with the command:

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
```

This adds the Powerlevel10k files to the oh-my-zsh custom themes folder. Now modify the config file *~/.zshrc* and set **ZSH_THEME="powerlevel10k/powerlevel10k**". Restart the terminal for this to take effect. You may be presented with the powerlevel10k configuration wizard. I am going to register my choices for it at a later date. If you are not presented with this wizard, or if you would like to run it again, simply type *p10k configure* on the terminal.

After running the configuration wizard, you should now have the file *~/.p10k.zsh*. This file contains configuration details regarding the theme itself, and can be customized directly (the configuration wizard presumably simply sets certain variables to specific values).

#### **Installing the Nerd Fonts**

If you follow the configuration wizard, a nerd font should be installed during the process. You can find more fonts [here](https://github.com/ryanoasis/nerd-fonts). The nerd fonts are fonts patched with a high number of glyphs, which are used by Powerlevel10k to enhance the terminal looks.

#### **Enhancing Powerlevel10k**

 The *~./p10k.zsh* file can be used to customized the prompts displayed on the left and on the right. Look up *POWERLEVEL9K_LEFT_PROMPT_ELEMENTS* and *POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS* and add or remove prompts as desired.

## **Python**

Python is a popular language for developing data science models. The Python version that comes with MacOS is quite obsolete, so we will install a newer one with Homebrew. To do so, run the folowing on your terminal:

```sh
brew install python
```

This should install python and pip, which is the package installer for python. Due to the MacOS python taking precedence over the Homebrew python, it is necessary to call the Homebrew python and pip with *python3* and *pip3* (this might not be enough if MacOS eventually makes python 3.x the default python). One way around that is to define an alias. For now, I am just going to use the suffix 3 explicitly.

## **Text Editor: Visual Studio Code (VSCode)**

One of the most important tools for a data scientist is the text editor. If using an editor remotely, you may not have much choice but to use whatever is available on the server. However, when working locally, I will go for the option that provides me the most comfort. There are many editors out there. In the context of data science work, I have had the chance ot use *Sublime*, *Atom* and *Visual Studio Code*. You can look up online for major differences between these editors -- and other options -- to make your call for an editor. I personally use VSCode because it has about the same features I have found in Sublime and Atom, but also comes with the unique feat of being able to run Jupyter notebooks inside the editor. I really enjoy this aspect, as it gives me the typical benefits of Jupyter coupled with any enhancements provided by the editor.

### **Installing VSCode**

Follow this [link](https://code.visualstudio.com/docs/setup/mac) for installing VSCode on MacOS.
