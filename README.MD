# Configuring just installed MacOS

## Install tools
- [Brew](https://brew.sh) package manager
- [zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH#macos) shell
- [oh-my-zsh](https://ohmyz.sh/#install) zsh package manager
- [fzf](https://github.com/junegunn/fzf#using-git) convinient recent files search

## Configuring shell
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
