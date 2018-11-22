#git命令行工具使用简明手册v0.1	
  你如果没用过git，那你肯定不好意思说自己是一个软件开发人员。git自诞生迅速成为最流行的分布式版本控制系统。2008年GitHub网站的上线更是让git火得一塌糊涂！
   作为一个命令行爱好者，本文档介绍了基于命令行的git使用（主要在winodws环境下）。这篇文档是git的入门教程，可满足一个git普通用户的使用，如果想进一步了解git，推荐网上的《Git权威指南》，指南本身也是开源的，可以在https://github.com/jiangxin/docker-gotgit找到。本教程也放在github上，可以在xxx找到，由于个人水平有限，难免有疏忽和错误之处欢迎批评指正。
 
git是什么？
  git是一个开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。最初git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。git与常用的版本控制工具 CVS, Subversion 等不同，它采用了分布式版本库的方式，这意味着它并不依赖于中心服务器来保存你文件的旧版本。任何一台机器都可以有一个本地版本的控制系统，其实就是一个硬盘上的文件，我们称之为仓库（repository）。如果是多人协作的话，你还需要一个线上仓库，用来同步代码等信息，支持多人协作，比如著名的GitHub等网站。当然，git是一个开源系统，你也可以自己搭建一个git服务器，用于公司内部的软件版本控制。
安装客户端
Linux
  大部分linux发行版应该已经包含了git客户端，如果你在命令行下执行git成功，那么说明你的机器上已经安装了git。如果没有安装，可以用发行版的软件包管理工具安装，如基于debain的发行版可以用apt-get install git安装。
Windows
  最初git是基于linux的命令行方式，和windows的shell有较大差异，最初在windows下模拟linux命令行的软件还有问题。不过随着软件的成熟，gitscm的windows下git客户端已经非常好用，可以到https://gitforwindows.org/下载安装，我们只要执行Git Bash程序就可以进入命令行方式。要注意在Git Bash里，本地硬盘,如C:\myfile文件，在gitscm命令行下写成/C/myfile。
基本配置及目录
git config --global user.name "My Name" 
git config --global user.email myEmail@example.com
  安装好客户端之后，首先执行这两个命令来设置使用者名字和邮件，这代表了你在提交时候的身份。
  其实config命令修改了git的配置文件，Git相关的配置文件有三个
1. windows在gitscm安装目录下gitconfig ，linux在/etc/gitconfig：包含了适用于系统所有用户和所有项目的值。
2.windows在用户目录下.gitconfig ，linux在~/.gitconfig：只适用于当前登录用户的配置。
3. 位于git项目目录中的.git/config：适用于特定git项目的配置。
对于同一配置项，三个配置文件的优先级是1<2<3
git init
  进入某个空的文件夹下，打开Git Bash命令窗口输入git init。命令主要用来初始化一个空的git本地仓库。执行完上面的命令，当前目录下会自动生成.git隐藏文件夹，该隐藏文件夹就是git版本库，下面讨论的所有对象都存储在这个目录里。初始化完成之后，你就可以在这个文件夹里创建文件进行管理了。

