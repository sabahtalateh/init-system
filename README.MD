# Configuring just installed MacOS

## Install tools
- [ITerm2](https://iterm2.com)
- [brew](https://brew.sh) package manager
- [zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH#macos) shell
- [oh-my-zsh](https://ohmyz.sh/#install) zsh package manager
- [fzf](https://github.com/junegunn/fzf#using-git) convinient recent files search

## Configure ITerm2
Create config folder
```bash
mkdir ~/ITerm2.Config
```

Download settings file into folder
```
curl -o ~/ITerm2.Config/com.googlecode.iterm2.plist https://raw.githubusercontent.com/sabahtalateh/init-system/main/com.googlecode.iterm2.plist
```

Set folder as config folder (Preferences -> General -> Preferences)
![Alt text](image.png)

## Configure shell
At `~/.zshrc` file add following line

```
# zsh config
export ZSH="$HOME/.oh-my-zsh"
ZSH_THEME="robbyrussell"
plugins=(git zsh-autosuggestions zsh-syntax-highlighting) 
source $ZSH/oh-my-zsh.sh

# prompt
export PS1="%{[36m%}%c%{[00m%} $(git_prompt_info)"

# fzf
[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh # fzf will popup by <ctrl+r>

# integrations when zsh is runnning as VS Code terminal
[[ "$TERM_PROGRAM" == "vscode" ]] && . "$(code --locate-shell-integration-path zsh)"
```
