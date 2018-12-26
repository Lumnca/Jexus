## :umbrella:Jexus安装及配置  ##

在Linux上运行ASP.NET网站或WebApi的传统步骤是，先安装libgdiplus，再安装mono，然后安装Jexus。在这个过程中，虽然安装Jexus是挺简便的一件事，但是安装mono就相对的比较费时费力了。

现在的情况不同了，为了克服安装 Mono 的繁琐，简化 ASP.NET WEB 应用在Linux操作系统上的部署过程，我们为Jexus 5.8.1制作了一款无需安装mono就能使用的“独立版”，该“独立版”支持64位的CentOS 6.5、Ubuntu 12.04以上版本的操作系统，能运行WebForm、Mvc3-5、WebService 以及WebApi，支持PHP，支持OWIN，支持反向代理，也就是说，无需安装mono的“独立版”与需要安装mono的“通用版”在功能上是完全相同的。

下面具体谈谈Jexus“独立版”的使用。

### :one: 下载 ###

把 jexus压缩包下载到linux临时文件夹tmp中。

```linux
cd /tmp
```
开始下载
```
wget linuxdot.net/down/jexus-5.8.1-x64.tar.gz
```

### :two: 解压 ###

```
tar -zxvf jexus-5.8.1-x64.tar.gz
```
解压完成后，会在/tmp中得到一个jexus文件夹。把jexus文件夹移动或复制到一个指定的工作位置，这个位置你自己决定，建议大家统一使用/usr路径。

```
sudo mv jexus /usr
```
然后清理/tmp中的jexus：
```
sudo rm -rf /tmp/jexus*
```

### :three:建一个简单的aspx网页用于测试： ###

由于jexus的默认的网站配置文件指向的物理路径是/var/www/default，所以，我们在/var下创建www文件夹，在www下创建default文件夹(如果存在该文件夹就直接打开)。创建完成后:

进入目录/var/www/default:
```
cd /var/www/default
```
创建一个默认页面，不需要编写内容
```
vim  default.cshtml
```

保存后退出。

### :four:启动jexus并尝试访问默认网站： ###

进入jexus目录：
```
cd /usr/jexus
```
启用默认网站：
```
sudo ./jws start
```

接下来访问你的IP地址，如果看到时间则表示成功，这只是成功了一部分，如果想启用ASP .NET还要进行后续操作

### :five:Jexus的常用命令：###
```
启动：sudo ./jws start

重启：sudo ./jws restart

停止：sudo ./jws stop

启动某个网站： sudo start 网站名

重启某个网站：sudo restart 网站名

停止某个网站：sudo stop 网站名

```





