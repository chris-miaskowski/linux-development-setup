# Environment Setup and Configuration for Developing on Linux

I plan to document some of the usual & repetitive configuration I'm quite fed up with memorizing :)

Hence this repo.

## Visual Studio Code

### Plugins

- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [IntelliJ IDEA Keybindings](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings)
- [TSLint](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-tslint-plugin)

## Bash

.bashrc

```bash
# Variables
export PS1='\[\e[35m\]\u\[\e[m\]@\[\e[35m\]\h\[\e[m\]\w\[\e[33m\]$(__git_ps1 " (%s)")\[\e[m\]\n -> '

# Aliases
alias xcclip="xclip -selection clipboard"
```

**Stuff to install**

```bash
# git-extras adds support for cool gitflow features like `git feature`
# xclip is a handy util to copy stuff to clip board `echo "xyz" | xclip -selection clipboard`
sudo apt-get install git-extras xclip
```
