# ZSH + Oh-My-Zsh

## LINUX Based
Ref: 
* https://www.youtube.com/watch?v=su0h5StEZ6A
* https://github.com/zsh-users/zsh-autosuggestions/blob/master/INSTALL.md#oh-my-zsh

### Install ZSH
* From package manager
```
sudo apt install zsh
```
* Make your default shell
```
chsh -s $(which zsh)
```
* Check the shell
```
echo $SHELL
# Should print `/urs/bin/zsh`, otherwise we need to restart to activate
```

### Install OhMyZsh
* Run command
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### Themes + Plugins
* PowerLevel10k Themes
```
git clone https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/themes/powerlevel10k
```
=> Initially we can set up all configuration for the theme. We can reset the configuration by run `p10k configure`.
* Download and install system font with `NERD Fonts` - Prefer `FiraMono Nerd Font`
* Auto suggestion plugin
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
* Syntax Highlighting plugin
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

### Update ZSH Configuration
* Open the file
```
vim ~/.zshrc
```
* From the opened file, we will replace the following configurations with
```
ZSH_THEME="powerlevel10k/powerlevel10k"
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

### Integration
* Update system font, with `gnome tweak`, we update all default fonts (or at least the mono option) to `FiraMono Font` before setting up the zsh `powerlevel10k` theme.
* When we use `Visual Studio Code`, find `terminal:font` and update the font with `FuraMono Nerd Font`.