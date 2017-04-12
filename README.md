oopy_dev-OOPY开源团队统一开发平台
==============

![logo](/assets/logo.png)

为了整个OOPY开源团队更好的协助，我们创建了一个统一的软件开发平台。该平台基于``VirtualBox``，``Vagrant``， ``Ubuntu``等开源软件搭建，内置了``Python``，``arm-none-eabi-gcc``，``vim``，``git``等开发工具。可在该平台上进行``Python``，``C``，``C++``,``嵌入式C``等语言的编程。且该平台能够同时运行在Window，Linux，MACOSX三大主流操作系统中，具有一致的运行效果。

下面分别介绍各操作系统中的安装方法:

### 1. Windows中的安装

>最低配置要求:
>内存: >= 4G
>硬盘空间: >= 10G
>版本: >= Win7

>演示机器
>型号: Surface pro 4
>CPU: m3
>内存: 4G

##### 1.1 安装终端软件-cmder

>Cmder：
>Cmder是一个Windows平台下的linux终端模拟器，自带了大量linux工具，比如 grep, curl(没有 wget)； 像vim, grep, tar, unzip, ssh, ls, bash, perl, git等。且完全版大小仅80多MB，非常小巧精悍。

![cmder](/assets/cmder.jpg)

打开官网首页

>http://cmder.net/

直接下载安装即可(``注:一定要下载full版本``)

##### 2.2 安装虚拟机软件-VirtualBox

>VirtualBox
>Oracle VirtualBox是由德国InnoTek软件公司出品的虚拟机软件，现在则由甲骨文公司进行开发，是甲骨文公司xVM虚拟化平台技术的一部分。它提供用户在32位或64位的Windows、Solaris及Linux 操作系统上虚拟其它x86的操作系统。用户可以在VirtualBox上安装并且运行Solaris、Windows、DOS、Linux、OS/2 Warp、OpenBSD及FreeBSD等系统作为客户端操作系统[1]。

打开官网首页

https://www.virtualbox.org/

点击下图图标:
![virtualbox_download](/assets/virtualbox_download.png)

选择:``Windows hosts``
![virtualbox_download_1](/assets/virtualbox_download_1.png)

下载完成后，一路next,yew，即可进行安装。


##### 2.3 安装虚拟机插件-VirtualBox Extension Pack
>由于VirtualBox中默认没有安装USB扩展，所以需要安装Extension Pack进行安装。

``注：``此步骤需在2.2安装完成后进行。

打开VirtualBox 下载页面:

>https://www.virtualbox.org/wiki/Downloads

![virtualbox_download_2](/assets/virtualbox_download_2.png)

下载完成后，默认安装即可。

##### 2.4 安装虚拟化工具-Vagrant

>Vagrant
>Vagrant是一款用于构建及配置虚拟开发环境的软件，基于Ruby,主要以命令行的方式运行。
主要使用Oracle的开源VirtualBox虚拟化系统，与Chef，Salt，Puppet等环境配置管理软件搭配使用， 可以实行快速虚拟开发环境的构建。

打开Vagrant 的下载页面:
>https://www.vagrantup.com/downloads.html

![vagrant_download](/assets/vagrant_download.png)

选择上图中的版本，下载安装，一路next即可。

```
完成最后一步后，会要求重启，按要求重启即可。
```
##### 2.5 Clone 项目代码到本地

打开Cmder，执行如下命令，切换到C盘根目录。
```
cd \
```
Clone github上的代码到本地
```
git clone https://github.com/oopy/oopy_dev.git
```
clone完成后，C盘根目录下就会出现名称为oopy_dev的文件夹。

从下面的链接中，oopy_dev.box到oopy_dev中。

>NULL
文件较大，请保存耐心。

下载完成后，在Cmder中进入oopy_dev文件夹:
```
cd oopy_dev
```

此时输入ls 会列举该文件夹中存在的文件，如下图:
```
ls
待补充
```

##### 2.6 初始化并启动运行环境


首先将oopy_dev.box添加到本地box列表中。

在Cmder中运行如下命令:

```
vagrant box add oopy_dev oopy_dev.box
```

初始化Vagrant 运行环境
```
vagrant up
```

ssh 链接进入Ubuntu环境
```
vagrant ssh
```

>注
>关闭Vagrant: vagrant halt
>其中Vagrant: vagrant reload
>再次进入Vagrant: vagrant ssh

##### 2.7 写一个Hello world

使用``vagrant ssh``登陆进入Ubuntu系统:

使用vim编辑main.c文件:
```
vim main.c
```
输入以一个hello world 的代码:
```
#include <stdio.h>
int main(void){
  printf("Hello world!\n");
  return 0;
}
```
使用gcc编译
```
gcc main.c -o hello
```
运行
```
./hello
```
``PS:``关于vim的使用，先预览此篇，高级技巧请自行Google:-D
>http://coolshell.cn/articles/5426.html

### 2 Macosx 上的安装

待补充

### 3 Ubuntu 上的安装

待补充

### 4 后续
后续会介绍，如何使用git工具，如何在该环境下编译STM32程序，以及如何参与开源项目。

>关于我们
>Infinite && Python
>我们是OOPY硬件开源团队，专注于物联网与人工智能。

![logo](/assets/logo.png)
