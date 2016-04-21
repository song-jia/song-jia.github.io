在进行所有安装之前需要先执行下面的命令安装GnuPG用于RVM在安装过程中验证安装包

```bash
gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
```

安装RVM

```bash
\curl -sSL https://get.rvm.io | bash -s stable
```

安装完成后执行下面的命令把rvm命令加到shell中,命令中星号的部分替换成当前登陆的用户名。

```bash
source /Users/*******/.rvm/scripts/rvm
```
安装最新ruby

```bash
rvm isntall 2.3
```

安装成功

```bash
$ ruby -v
ruby 2.3.0p0 (2015-12-25 revision 53290) [x86_64-linux]
```
