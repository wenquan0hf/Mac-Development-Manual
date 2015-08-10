# MySQL  

## 安装

我们将使用 Homebrew 安装 [MySQL](http://www.mysql.com/)，同时也会安装 MySQL 的相关文件。

安装 MySQL:
  
```
$ brew update # 这是一个好习惯
$ brew install mysql  
```  

在使用 MySQL 前，我们需要做一些设置：
  
```
$ unset TMPDIR
$ mkdir /usr/local/var
$ mysql_install_db --verbose --user=`whoami` --basedir="$(brew --prefix mysql)" --datadir=/usr/local/var/mysql --tmpdir=/tmp  
```  

## 使用

启动 MySQL 服务，运行 mysql.server
  
```
$ mysql.server start  
```  

关闭 MySQL，运行：
  
```
$ mysql.server stop  
```  

你可以了解更多 mysql.server 的命令，运行：
  
```
$ mysql.server --help  
```  

登录 MySQL, 运行:
  
```
$ mysql -uroot  
```  

**Note**: 默认情况下，MySQL 用户 root 没有密码，这对本地开发没有关系，但如果你希望修改密码，你可以运行:
  
```
$ mysqladmin -u root password 'new-password'  
```  

译注：

当你在设置密码时出现问题，可以参考 [lgn21st](https://ruby-china.org/topics/1901) 的方式。

此外，如果你觉得敲那么多命令是一件很麻烦的事情，那么你也可以参考 [Mac OS安装 MySQL（使用二进制PGK包安装）](http://elf8848.iteye.com/blog/1914209)