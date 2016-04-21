安装ubuntu SSH server
$ sudo apt-get install openssh-server
测试SSH访问
在本机测试：
$ ssh localhost
有可能会提示未知的fingerprint回答yes即可。
之后提供你的系统帐户密码，至此你已经通过SSH登录了你自己的计算机，这说明SSH server工作在正常。

通过另一台电脑访问
如果你有另一台电脑和ubuntu在同一个本地网络中，运行：
$ ssh name@192.168.33.11
使用ubuntu的帐户替换上面命令中的name，并且用ubuntu的IP替换“192.168.33.11”。
之后提供密码即可通过CLI登录ubuntu。

安装并配置Vino
sudo apt-get install vino
安装完成以后需要执行下面的命令手动启动vino。
vino-preferences
在弹出的窗口中选择 ..... TODO
打开"session and startup"设置面板，选择添加下面的命令
/usr/lib/vino/vino-server
