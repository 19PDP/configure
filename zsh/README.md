`.zshrc` 是在安装 [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh) 时生成的默认配置的基础上进行的修改

> 需要提前安装 oh-my-zsh：
>
> ```zsh
> sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
> ```

需要开启插件，在 `~/.zshrc` 文件中 `plugins=(git z zsh-autosuggestions)` 中按需添加插件名即可。安装 ohmyzsh 同时安装了大部分 [默认插件](https://github.com/ohmyzsh/ohmyzsh/wiki/Plugins)，没有默认安装的需要手动安装。



## oh-my-zsh 常用插件安装及使用

### cp

提供一个 `cpv` 命令，这个命令使用 rsync 实现带进度条的复制功能。

### gitignore

提供一条 `gi` 命令，用来查询 **gitignore 模板**。比如你新建了一个 python 项目，就可以用

```zsh
 gi python > .gitignore 
```

来生成一份 gitignore 文件。

### zsh_reload

提供一个 `src` 命令，重载 zsh。对于经常折腾 zshrc 的我，这条命令非常实用。

### z

提供一个 `z` 命令，在常用目录之间跳转。类似 autojump，但是不需要额外安装软件。



> 以下插件需要手动安装

###  [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)

shell 命令的代码高亮。你没有理由拒绝高亮。

```zsh
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

###  [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)

在输入命令的过程中根据你的历史记录显示你可能想要输入的命令，按 tab 补全。

```zsh
$ git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions 
```

### [git-open](https://github.com/paulirish/git-open)

[git-open](https://github.com/paulirish/git-open) 插件可以在你git项目下打开远程仓库浏览项目。

```zsh
$ git clone https://github.com/paulirish/git-open.git $ZSH_CUSTOM/plugins/git-open
```







----

// 不太实用！！！

安装插件管理工具 `zplug` :

```zsh
$ curl -sL --proto-redir -all,https https://raw.githubusercontent.com/zplug/installer/master/installer.zsh | zsh
```

或者直接使用 Homebrew 安装：

```zsh
$ brew install zplug
```

###  [zplug](https://github.com/zplug/zplug)

zsh 的插件管理器，类似 vim 的 vundle，把需要的所有插件写到 `zshrc` 里，然后运行 `zplug install` 就可以安装这些插件。就像这样：

```text
if [[ -f ~/.zplug/init.zsh ]] {
  source ~/.zplug/init.zsh  # zplug的安装目录，可能与此有异

  zplug "zsh-users/zsh-syntax-highlighting"
  zplug "zsh-users/zsh-autosuggestions"
  zplug "supercrabtree/k"
  zplug "denisidoro/navi"
  zplug "MichaelAquilina/zsh-you-should-use"
  zplug "changyuheng/zsh-interactive-cd"
  zplug "SleepyBag/zsh-confer"

  zplug "Powerlevel9k/powerlevel9k", from:github, as:theme, if:"[[ $ZSH_THEME_STYLE == 9k ]]"
  zplug "denysdovhan/spaceship-prompt", use:spaceship.zsh-theme, from:github, as:theme, if:"[[ $ZSH_THEME_STYLE == spaceship ]]"
  zplug "caiogondim/bullet-train.zsh", use:bullet-train.zsh-theme, from:github, as:theme, if:"[[ $ZSH_THEME_STYLE == bullet ]]"
  zplug "skylerlee/zeta-zsh-theme", from:github, as:theme, if:"[[ $ZSH_THEME_STYLE == zeta ]]"

  if ! zplug check --verbose; then
      echo 'Run "zplug install" to install'
  fi
  # Then, source plugins and add commands to $PATH
  zplug load
}
```

这个工具不仅可以用来装 zsh 插件，事实上它可以用来自动安装任何你认为有必要的插件、主题、脚本甚至二进制程序。但是对于非 zsh 插件的程序，在安装之前要先看看 zplug 的文档，搞清楚如何安装。

