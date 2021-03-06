# Homebrew  

包管理工具可以让你安装和更新程序变得更方便，目前在 OS X 系统中最受欢迎的包管理工具是 Homebrew.

## 安装

在安装 Homebrew 之前，需要将 Xcode Command Line Tools 安装完成，这样你就可以使用基于 Xcode Command Line Tools 编译的 Homebrew。

在 terminal 中复制以下命令（不包括 $），跟随指引，将完成 Hombrew 安装。
  
```
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" 
```  

紧接着，我们需要做一件事让通过 Hombrew 安装的程序的启动链接 (在 /usr/local/bin 中）可以直接运行，无需将完整路径写出。通过以下命令将 /usr/local/bin 添加至 $PATH 环境变量中:
  
```
$ echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bash_profile  
```  

**Cmd+T** 打开一个新的 terminal 标签页，运行以下命令，确保 brew 运行正常。
  
```
$ brew doctor  
```  

译注：

安装完成后，Homwbrew 会将本地 /usr/local 初始化为 git 的工作树，并将目录所有者变更为当前所操作的用户，将来 brew 的相关操作不需要 sudo 。 
  
## Homebrew 基本使用  

安装一个包，可以简单的运行：
  
```
$ brew install <package_name>  
```  

更新 Homebrew 在服务器端上的包目录：
  
```
$ brew update  
```  

查看你的包是否需要更新：
  
```
$ brew outdated  
```  

更新包：
  
```
$ brew upgrade <package_name>  
```   

Homebrew 将会把老版本的包缓存下来，以便当你想回滚至旧版本时使用。但这是比较少使用的情况，当你想清理旧版本的包缓存时，可以运行：
  
```
$ brew cleanup  
```  

查看你安装过的包列表（包括版本号）：
  
```
$ brew list --versions  
```   
  
## Homebrew Cask  

你已经感受到了使用 Homebrew 安装命令行程序的便利。那么接下来，我们将通过 Homebrew Cask 优雅、简单、快速的安装和管理 OS X 图形界面程序，比如 Google Chrome 和 Dropbox。

## 安装

安装 Homebrew-cask 是如此的简单直接，运行以下命令即可完成：
  
```
$ brew tap caskroom/cask  // 添加 Github 上的 caskroom/cask 库
$ brew install brew-cask  // 安装 brew-cask
$ brew cask install google-chrome // 安装 Google 浏览器
$ brew update && brew upgrade brew-cask && brew cleanup // 更新  
```  

### 搜索

如果你想查看 cask 上是否存在你需要的 app，可以到 [caskroom.io](http://caskroom.io/) 进行搜索。

### 文件预览插件

有些 [插件](https://github.com/sindresorhus/quick-look-plugins) 可以让 Mac 上的文件预览更有效，比如语法高亮、markdown 渲染、json 预览等等。
  
```
$ brew cask install qlcolorcode
$ brew cask install qlstephen
$ brew cask install qlmarkdown
$ brew cask install quicklook-json
$ brew cask install qlprettypatch
$ brew cask install quicklook-csv
$ brew cask install betterzipql
$ brew cask install webp-quicklook
$ brew cask install suspicious-package   
```  

### OS X 图形界面程序
  
```
$ brew cask install alfred
$ brew cask install appcleaner
$ brew cask install cheatsheet
$ brew cask install dropbox
$ brew cask install google-chrome
$ brew cask install onepassword
$ brew cask install sublime-text
$ brew cask install totalfinder
...  
```  

译注：

如果你经常使用 Alfred 启动程序，那么你会想 Alfred 可以搜索 brew cask 安装的程序，实现这些仅需运行：
  
```
brew cask alfred link  
```  

此外你还可以通过 brew cask 安装 [launchrocket](https://github.com/jimbojsb/launchrocket)，来管理通过 brew 安装的 service  
   
![](images/1.png)