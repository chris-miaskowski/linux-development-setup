# Environment Setup and Configuration for Developing on Linux

I plan to document some of the usual & repetitive configuration I'm quite fed up with memorizing :)

Hence this repo.

## Visual Studio Code

### Plugins

- [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [IntelliJ IDEA Keybindings](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings)
- [TSLint](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-typescript-tslint-plugin)
- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
- [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
- [Highlight Matching Tag](https://marketplace.visualstudio.com/items?itemName=vincaslt.highlight-matching-tag)

### Fixes (Ubuntu 19.02)

### Ctrl + Alt + Left broken

```bash
gsettings set org.gnome.desktop.wm.keybindings switch-to-workspace-left "[]"
gsettings set org.gnome.desktop.wm.keybindings switch-to-workspace-right "[]"
```

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

## X1C1 Tweaks

### Trackpoint not working after rebook

Add the following script to this file (note it does not fix the issue completely but seems to break less often...) `/usr/lib/pm-utils/sleep.d/99restart-touchpad`

```sh
#!/bin/sh
# Custom script I (chrism) added to resolve the x1c6 issues with reconnecting touchpad after waking up from deep sleep
# See reference here: https://forums.lenovo.com/t5/Other-Linux-Discussions/Troubles-with-X1-Carbon-2018-X1C6-TouchPad-and-TrackPoint-under/td-p/4004815

case "$1" in
	thaw|resume) 
		echo -n none > /sys/devices/platfrom/i8042/serio1/drvctl
		echo -n reconnect > /sys/devices/platform/i8042/serio1/drvctl
		;;
	*) exit $NA
		;;
esac

exit 0
```

## Power Management & Performance Tools

- [powertop](https://www.youtube.com/watch?v=Ku0491LfhR4)
- [tlp](https://www.youtube.com/watch?v=Ku0491LfhR4)
- `iotop`
- `sensors`
- `htop`
- `sysbench`
