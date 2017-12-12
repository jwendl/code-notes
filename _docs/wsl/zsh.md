---
title: Run ZSH
category: Windows Subsystem for Linux
order: 3
---

## Azure Command Line
``` bash
sudo apt-get install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
chsh -s /usr/bin/zsh
git clone https://github.com/powerline/fonts.git --depth=1
cd fonts
./install.sh
git clone https://github.com/seebi/dircolors-solarized.git
cd colors/dircolors-solarized
vi dircolors.256dark
```

> Be sure to change the theme to "agnostic" inside the ~/.zshrc file

> Modify ~/.zshrc to add eval `dircolors ~/colors/dircolors-solarized/dircolors.256dark`

> Replace EXEC 00;38;5;64 with EXEC 00;38;5;244

> Install the proper .ttf under DejaVuSansMono by double clicking and selecting install
> Then add it to the terminal window fonts (properties -> Edit)