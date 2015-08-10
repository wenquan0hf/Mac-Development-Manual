# Git and Github  

作为一名开发者怎么可能没有 [Git](http://git-scm.com/) 呢? 我们马上就来安装：
  
```
$ brew install git  
```  

好的，现在我们来测试一下 git 是否安装完好：
  
```
$ git --version  
```  

运行 $ which git 将会输出 /usr/local/bin/git.

接着，我们将定义你的 Git 帐号（与你在 [GitHub](https://github.com/) 使用的用户名和邮箱一致）
  
```
$ git config --global user.name "Your Name Here"
$ git config --global user.email "your_email@youremail.com"  
```  

这些配置信息将会添加进 `~/.gitconfig` 文件中.

我们将推荐使用 HTTPS 方法（另一个是 SSH），将你的代码推送到 Github 上的仓库。如果你不想每次都输入用户名和密码的话，可以按照此 [描述](https://help.github.com/articles/set-up-git) 说的那样，运行：
  
```
$ git config --global credential.helper osxkeychain 
```  

此外，如果你打算使用 SSH 方式，可以参考此 [链接](https://help.github.com/articles/generating-ssh-keys).  
  
## Git Ignore  

创建一个新文件 `~/.gitignore` ，并将以下内容添加进去，这样全部 git 仓库将会忽略以下内容所提及的文件。
  
```
\# Folder view configuration files
.DS_Store
Desktop.ini

\# Thumbnail cache files
._*
Thumbs.db

\# Files that might appear on external disks
.Spotlight-V100
.Trashes

\# Compiled Python files
*.pyc

\# Compiled C++ files
*.out

\# Application specific files
venv
node_modules
.sass-cache  
```