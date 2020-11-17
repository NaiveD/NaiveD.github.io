---
title: 设置 zsh
date: 2020-11-17 10:37:01
tags: tools
categories:
    - configuration
    - Shell
---

## 设置 zsh

### 安装 zsh

查看系统里已经安装的shell: `cat /etc/shells`.

```shell
# /etc/shells: valid login shells
/bin/sh
/bin/bash
/bin/rbash
/bin/dash
/usr/bin/tmux
/usr/bin/screen
```

Mac默认是安装zsh的，Linux没有装。Ubuntu上安装zsh: `sudo apt-get install zsh`.

再用 `cat /etc/shells`查看已安装的shell:

```shell
# /etc/shells: valid login shells
/bin/sh
/bin/bash
/bin/rbash
/bin/dash
/usr/bin/tmux
/usr/bin/screen
/bin/zsh
/usr/bin/zsh
```

发现zsh已经安装好了。把当前shell改为zsh: `chsh -s /bin/zsh`.

### 安装 oh my zsh

自动安装: `wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh`

### 配置 zsh

安装插件

* auto-suggestions
  * 任意目录下: `git clone git://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/plugins/zsh-autosuggestions`
  * `.zshrc`里加入`plugins=(git zsh-autosuggestions)`, 然后`source ~/.zshrc`.