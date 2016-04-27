---
layout: post
title: OSX上安装RVM和Ruby
category: OSX
tags: [OSX,RVM,Ruby]
---

##背景
使用系统自带的Ruby gem安装ruby程序的时候会要求使用root帐号或者使用sudo来提高权限。并且当某些程序需要其他版本Ruby的时候切换也不是很方便。不过很幸运RVM可以帮助我们方便的管理Ruby版本在不同版本间方便切换，而且所有内容都安装在当前用户的目录中不会有权限问题。下面是简单的RVM安装使用步骤。

##安装

RVM的官网提供了详尽的[安装方法](http://rvm.io/rvm/install#explained),对英文没有障碍或是想了解更多的朋友可以参考。

在进行所有安装之前需要先执行下面的命令安装GnuPG用于RVM在安装过程中验证安装包

```bash
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
```

如果执行上面的命令报错"gpg: command not found"需要先安装gpg。如果已经安装homedrew可以使用下面的命令安装gpg。

```bash
brew install gnupg gnupg2
```

安装RVM

```bash
\curl -sSL https://get.rvm.io | bash -s stable
```

安装完成后执行下面的命令把rvm命令加到shell中,命令中星号的部分替换成当前登陆的用户名。

```bash
source /Users/*******/.rvm/scripts/rvm
```

安装好以后执行rvm list known列出可以安装的ruby版本。

```bash
$rvm list known
# MRI Rubies
[ruby-]1.8.6[-p420]
[ruby-]1.8.7[-head] # security released on head
[ruby-]1.9.1[-p431]
[ruby-]1.9.2[-p330]
[ruby-]1.9.3[-p551]
[ruby-]2.0.0[-p643]
[ruby-]2.1.4
[ruby-]2.1[.5]
[ruby-]2.2[.1]
[ruby-]2.2-head
ruby-head
```

安装ruby 2.1

```bash
rvm isntall 2.1
```

安装成功

```bash
$ ruby -v
ruby 2.1.5p273 (2014-11-13 revision 48405) [x86_64-darwin15.0]
```