1. 首先在服务器上安装ssh的服务器端。
$ sudo apt-get install openssh-server

2. 启动ssh-server。
$ /etc/init.d/ssh restart

3. 确认ssh-server已经正常工作。
$ netstat -tlp
tcp6 0 0 *:ssh *:* LISTEN -
看到上面这一行输出说明ssh-server已经在运行了。

4. 在Ubuntu客户端通过ssh登录服务器。假设服务器的IP地址是192.168.0.103，登录的用户名是xxu8:
$ ssh -l xxu8 crcfe02.crc.nd.edu
接下来会提示输入密码，然后就能成功登录到服务器上了。

5. exit() 
   退出 ssh 链接

在linux下一般用scp这个命令来通过ssh传输文件。

新打开一个终端：
1、从服务器上下载文件
scp xxu8@crcfe02.crc.nd.edu:/path/filename /var/www/local_dir（本地目录）

 例如:
    scp xxu8@crcfe02.crc.nd.edu:wendian/doc/CRC_ND_how-to.pdf /home/wenyan/wenyan


2、上传本地文件到服务器
scp /path/filename username@servername:/path 

例如:scp /home/wenyan/wenyan/wendian/doc/README.md SHELL.md xxu8@crcfe02.crc.nd.edu:wendian/doc

 

3、从服务器下载整个目录
scp -r username@servername:/var/www/remote_dir/（远程目录） /var/www/local_dir（本地目录）

例如:scp -r xxu8@crcfe02.crc.nd.edu:wendian/doc /home/wenyan/wenyan/wendian

4、上传目录到服务器
scp  -r local_dir username@servername:remote_dir
例如：scp -r test  xxu8@crcfe02.crc.nd.edu:wendian/   把当前目录下的test目录上传到服务器的/var/www/ 目录



一种是命令行安装；另一种是通过Ubuntu Software Center安装，希望对大家能有帮助！

方法一（推荐）：命令行安装

只需要一条命令：

sudo apt-get install openssh-server

随后，Ubuntu 会自动下载并安装 openssh server，并一并解决所有的依赖关系。

想了解更详细的内容，请查看：http://www.linuxidc.com/Linux/2011-04/34588p3.htm

方法二 ：通过 Ubuntu Software Center 安装

首先进入 Ubuntu Software Center，然后在搜索栏里输入“openssh-server”；

随后会看到搜索结果里有openssh-server；

接着点击“Install”就可安装。

下面介绍在Windows系统下远程连接Linux，我用的是Putty远程连接工具：

1. 首先要确保你的Linux可以联网，并启动openssh server。

sudo /etc/init.d/ssh start

2. 然后通过下面的命令查看IP地址：

ifconfig

3. 然后在客户端启动Putty 输入要远程连接的Linux IP地址，端口号默认为22，就可远程连接到Linux。



























