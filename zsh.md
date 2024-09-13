# Comfort in the Terminal

Compare the two images below:

![bash-vs-zsh](https://i.imgur.com/2edKk11.png)

If you'd be more comfortable working in the terminal on the left, feel free to stop reading.

In this section, we'll look at how to install `zsh`, set up its functionality, and customize its appearance.

## Installation

### zsh

The official instructions can be found [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH), here, but in short:
* macOS: 
  ```shell script
  brew install zsh
  ```
* Ubuntu, Debian, Windows 10 WSL and alike:
  ```shell script
  sudo apt install zsh
  ```
* Arch, Monjaro:
  ```shell script
  pacman -S zsh
  ```

Right after installation, things don't look much better (left: `bash`, right: `zsh`, both on Ubuntu):

![after-install](https://i.imgur.com/Zc674oc.png)

You can work with plain `zsh`, but to configure it properly, we'll need the `Oh My Zsh` framework.

### Oh My Zsh

You can find the full description [here](https://github.com/ohmyzsh/ohmyzsh), but for those in a hurry (make sure `git` is installed):
* curl:
  ```shell script
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```
* wget:
  ```shell script
  sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

Now it's a bit prettier:

![after-oh-my-zsh](https://i.imgur.com/peWryj6.png)

Here's what `git` autocomplete looks like:

![git-autocomplete](https://i.imgur.com/l8BUuJk.png)

## Customization

The main settings for `zsh` are located at `~/.zshrc`:

![zshrc](https://i.imgur.com/mIOkVTW.png)

We will cover a few of these (mainly plugins and themes), and you can explore the rest on your own.

### Plugins

You can find the full list of plugins [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins). 

We'll start with [syntax highlighting](https://github.com/zsh-users/zsh-syntax-highlighting):
1. Clone the repository into the `Oh My Zsh` folder:
   ```shell script
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
   ```
2. In the `~/.zshrc` settings file, add `zsh-syntax-highlighting` to the list of plugins: 
   ![syntax-highlighting](https://i.imgur.com/73uJoUh.png)
   
In the next session or after running source `~/.zshrc`, you will see the result: 
![after-syntax-highlighting](https://i.imgur.com/P8UGiGp.png)

Next up is [autosuggestions](https://github.com/zsh-users/zsh-autosuggestions), with the same steps:
1. First, clone the repository:
   ```shell script
   git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
   ```
2. Then register the `zsh-autosuggestions` plugin: 
   ![autosuggestions](https://i.imgur.com/DRu2POE.png)

After restarting the terminal, starting a new session, or running `source ~/.zshrc`, you'll see suggestions: 
![after-autosuggestions](https://i.imgur.com/qeLbjoD.png)

If the suggestion color is too similar to the regular text (e.g., white), try experimenting with the `TERM` variable, like so: `export TERM=xterm-256color`.

One more plugin for quick navigation – [`z`](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/z):
1. Simply add it to the list of plugins:
   ![z](https://i.imgur.com/cETwJ27.png)

Now you can jump to any directory you've previously visited with `cd` by typing just part of its name: 
![after-z](https://i.imgur.com/fBrE289.png)

### Themes

You can find the full list of themes [here](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes).

There are plenty of themes for every style and preference, but one that stands out is `Powerlevel10k`:
1. First, you need to [install the recommended font.](https://github.com/romkatv/powerlevel10k#meslo-nerd-font-patched-for-powerlevel10k)
2. Next, clone the repository:
   ```shell script
   git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
   ```
3. Specify the theme `powerlevel10k/powerlevel10k` in your `~/.zshrc`:
   ![powerlevel10k](https://i.imgur.com/L9enCUq.png)

After restarting, you'll be taken straight to the configuration window. Read the prompts carefully, customize everything to your liking, and voilà: 
![after-powerlevel10k](https://i.imgur.com/ZdkmcrC.png)

### Terminal

You can unlock even more customization options by installing a new terminal instead of using the default one.
* macOS: The clear choice is [iTerm2](https://www.iterm2.com/) (this is the terminal shown on the top right image).
* Linux-based systems: You can try [Guake](http://guake-project.org/), [Tilda](https://github.com/lanoxx/tilda), 
[Yakuake](https://github.com/KDE/yakuake).
