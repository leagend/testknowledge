###在windows 10安装linux###
1.启用开发者模式

![在更新和安全中开启开发者模式](https://www.howtogeek.com/wp-content/uploads/2016/04/img_570999e304309.png)

2.安装Windows中的linux子系统

![在“启用或管理Windows功能”中启用windows中linux子系统](https://www.howtogeek.com/wp-content/uploads/2016/04/img_570999427548f.png)

3.安装lxrun
```
lxrun /install /y
或者
C:\bash
```
Tips:
* [win10 Bash On Windows 下载安装，Win10 ubuntu子系统安装太慢解决办法](https://github.com/wilon/wilon.github.io/issues/7)

First enable Windows Subsystem for Linux from “Program and Features” -> “Turn Windows features on or off”
Restart Windows (MS has a thing for rebooting)
Download one of the image and host it on your local web server if not done already
Start Fiddler and enable “Automatic Breakpoints” (Alt+F11)
Start command prompt and run “lxrun /install /y”
Switch to Fiddler. You will see a request to “https://go.microsoft.com/fwlink/?LinkID=730581”. Click on “Headers” tab -> Right click on “Location” -> “Edit Header” -> Paste your local link URL (i.e. http://localhost/xenial-server-cloudimg-amd64-root.tar.gz) and click on Save -> Run to Completion
There will be another request to “http://localhost/xenial-server-cloudimg-amd64-root.tar.gz”.  Just click on “Run to completion” this time.

[可供安装的Linux images位于](https://cloud-images.ubuntu.com/locator/)

```
安装过程

下载包

下载 安装包 16.04.0.2-server-cloudimg-amd64-root.tar.gz
使用Fiddler

下载Fiddler 并安装

打开 Fiddler，按照如下步骤：

找到Tools-->Fiddler Options...
-->单击HTTPS
-->勾选Decrypt HTTPS traffic
-->勾选Ignore server certificate errors (unsafe)
-->单击OK。

打开命令提示符，输入bash，输入y确认下载安装。

此时在Fiddler监测到HTTP连接，根据操作图2的步骤：
在Fiddler窗口右边单击AutoResponder
-->勾选下面的 Enable rules 、 Unmatched requests passthrough、Enable Latency这三个选项
-->在Fiddler窗口左边单击"https://wsldownload.azureedge.net/16.04.0.2-server-cloudimg-amd64-root.tar.gz"链接
-->在Fiddler窗口右边单击"Add Rule"按钮，将其添加到按钮下方的规则列表
-->在规则列表单击刚才新建的那一条
-->在规则列表下方有个Rule Editor，选择事先下载好的源离线压缩包

安装Ubuntu子系统

Win+R，输入cmd，Enter
输入bash /y安装，普通用户登陆
或输入lxrun /install /y安装，root用户登陆
安装完后，输入bash
```

4.使用Ubuntu bash

```
apt-get install libssl-dev libcurl4-openssl-dev python-dev
```
