
一、linux/ubuntu 操作
    1·root权限：
	    进入root：
		    sudo su
		退出root:
		    su wenyan
		安装：
		   （ubuntu>=17.04）
			sudo apt install archieve-name
			(ubuntu<17.04)
			sudo apt-get install archieve-name
	    linux内核版本查询两种方法：
	       （1）cat /proc/version
		   （2）uname -a
		linux 系统版本：
	        lsb_release -a
		更新：
		    (ubuntu>=17.04)
			sudo apt --upgrade install archieve-name
			(ubuntu<17.04)
			sudo apt-get --upgrade install archieve-name 
		    
		(最好不用root，容易造成系统奔溃)
    
	2·进入文件夹：
	    cd filefolder
	
	3·退出文件夹：
	    退出到上一层：
		    cd ..
		退出到根目录：
		    cd ~
			
    4·解压：
           http://www.cnblogs.com/daizhuacai/archive/2013/07/06/3174885.html
	   .gz
    	    gunzip filename.gz
	    .tar.gz
    	    tar -zxvf filename.tar.gz /home/filefolder
	    .zip
	        unzip filename.zip
	        解压到指定目录：
                    unzip -d /temp filename.zip
	5·压缩：
	    .zip
		    zip -r filename.zip directory_to_compress
		.tar
		    tar -zcvf filename.tar.gz directory_to_compress
		
		rar常用命令主要有:

            e 将文件解压到当前目录
              例:unrar e test.rar
              注:用e解压的话，不仅原来的file1.txt和file2.txt被解压到当前目录，就连dir1里面的所有文件
              也被解压到当前目录下，不能保持压缩前的目录结构，如果想保持压缩前的目录结构，用x解压

            x 带路径解压文档中内容到当前目录
              例:unrar x test.rar
                 这样解压的话，dir1就会保持原来的目录结构
			
			d 从文档中删除文件
              例:rar d test.rar file1.txt
         将tgz文件解压到指定目录
 
         tar在linux上是常用的打包、压缩、加压缩工具，他的参数很多，折里仅仅列举常用的压缩与解压缩参数
 
         参数：
 
             -c ：create 建立压缩档案的参数；
 
             -x ： 解压缩压缩档案的参数；
 
             -z ： 是否需要用gzip压缩；
 
             -v： 压缩的过程中显示档案；
 
             -f： 置顶文档名，在f后面立即接文件名，不能再加参数
 
        举例： 一，将整个/home/www/images 目录下的文件全部打包为 /home/www/images.tar
 
        tar -cvf /home/www/images.tar /home/www/images ← 仅打包，不压缩
 
        tar -zcvf /home/www/images.tar.gz /home/www/images ← 打包后，以gzip压缩
 
        在参数f后面的压缩文件名是自己取的，习惯上用tar来做，如果加z参数，则以tar.gz 或tgz来代表gzip压缩过的tar file文件
 
           1 将tgz文件解压到指定目录
 
              tar   zxvf    test.tgz  -C  指定目录
 
              比如将/source/kernel.tgz解压到  /source/linux-2.6.29 目录
 
                tar  zxvf  /source/kernel.tgz  -C /source/ linux-2.6.29
 
          2 将指定目录压缩到指定文件
 
             比如将linux-2.6.29 目录压缩到  kernel.tgz
 
             tar czvf   kernel.tgz   linux-2.6.29

         (http://www.2cto.com/os/201308/233614.html	)
       
       rar:
           安装：sudo apt-get install unrar
           卸载：sudo apt-get remove unrar
       rar常用命令主要有:

e 将文件解压到当前目录
  例:rar e test.rar
    注:用e解压的话，不仅原来的file1.txt和file2.txt被解压到当前目录，就连dir1里面的所有文件
    也被解压到当前目录下，不能保持压缩前的目录结构，如果想保持压缩前的目录结构，用x解压

x 带路径解压文档中内容到当前目录
  例:rar x test.rar
    这样解压的话，dir1就会保持原来的目录结构

a 添加文件到操作文档
例:rar a test.rar file1.txt 若test.rar文件不存在，则打包file1.txt文件成test.rar
    例:rar a test.rar file2.txt 若test.rar文件已经存在，则添加file2.txt文件到test.rar中
    (这样test.rar中就有两个文件了）
    注，如果操作文档中已有某文件的一份拷贝，则a命令更新该文件，对目录也可以进行操作
  例:rar a test.rar dir1

c 对操作文档添加说明注释
  rar c test.rar
    （会出现Reading comment from stdin字样，然后输入一行或多行注释，以ctrl+d结束）
    cf 添加文件注释，类似上面的c，不过这个是对压缩文档中每个文件进行注释

    cw 将文档注释写入文件
    例:rar cw test.rar comment.txt

d 从文档中删除文件
    例:rar d test.rar file1.txt

k 锁定文档
  例:rar k test.rar 锁定文档后，该文档就无法进行任何更新操作了

r 修复文档
  例:rar r test.rar
    当rar文件有问题时，可以尝试用该命令进行修复（鬼知道有多少用）

s 转换文档成自解压文档
  例:rar s test.rar
    会生成一个test.sfx的可执行文档，运行它的效果就相当于rar x test.rar，
    适合于向没有rar的用户传输文件

t 检测文档
  例:rar t test.rar
    检测test.rar的完整性，一般压缩完大型文件准备传输前最好用这个命令来确保文件的正确性

      以上就是rar的常用命令，一个rar操作只能有一个命令，而选项却可以有多个

    6·新建文件夹：	
	    mkdir filefolder
	    # 递归创建目录
		mkdir -p filefolder_1/filefolder_2
		
	7·新建文件：
	    touch filename.cpp/..
	
	8·打开文件:
	    gedit filename.cpp/..
		
	9·编译:
	    (文件目录下)
	        gcc filename.c
			g++ filename.cpp
		    python filename.py
		    sh filename.sh
    
	10·移动文件：
	    mv filename.cpp archieve_file
	
	11·重命名文件：
	    mv filefolder_A  filefolder_B
		    将 filefolder_A 重命名为 filefolder_B
			
		mv filefolder_A  filefolder_B/filefolder_C
		    将filefolder_A 移动到filefolder_B下并重新名为filefolder_C
	12 ./与 ../
            "./" ：代表当前目录
            "../"：代表上一层目录
            "/"  : 代表根目录
	    	 
二、CRC-Remote-sever
    1·账户：
        sftp://crcfe01.crc.nd.edu
        xxu8
        qq@Qwe123
    
    2·查看GPU
	    nvidia-smi
	
	3·申请GPU
	    qrsh -q gpu@@csecri

	4·查看内存
	    quota
	
	
	
		   
三、Git
    1·账户：
	      wendian

	2·密码：
	     xxxx2015
	
	3·账户切换：
         su git
    
	4·命令：
	    1)添加文件：
		    添加所有文件：
	            git add .
			添加特定文件： 
			    git add archieve.cpp/..
		    
			git commit -a
			    该命令可直接提交所有修改，省去git add ./ git diff /git commit 的操作，但如果有新文件加入，则不可使用 
			
		2)添加备注：
		    git commit -m "wenyan version 1.0"
			
			
		
        3)push:
            git push (可添加origin master/ origin )		
		   
		
        4)查看：
            git diff：产看文件的修改
            git status：查看当前目录
			
            git log：查看历史提交和修改
            git log -p：详细的log
            git branch: 常看当前所有分支
			
        5)创建分支：
            git branch dectory
                ：该命令只是在本地创建分支，如果要在remote也创建相应的分支
            git	push --set-upstream origin dectory
			    :服务器分支创建成功
		
		6) 合并(merge):合并某分支到主干道：
		    a) 切换到master:
			    git checkout master
			b) merge:
			    git merge dectory
		
		7) 分支删除：
		    a)分支合并到master的删除：
		        git branch -d dectory
				
			b)删除：
			    git branch -D dectory
				
				
四、Cmake
    1·CMakeLists.txt创建:
         各级src文件夹都要创建相应的CMakeLists.txt

	2·src创建:

	3·build创建:
	    进入build文件夹：
		    终端执行： 
			    cmake ..
				make
			test:
			    ./hello

            make install
			 
    	
五、安装notepad++
    

    sudo add-apt-repository ppa:notepadqq-team/notepadqq
    sudo apt-get update
    sudo apt-get install notepadqq

    卸载命令如下：

    sudo apt-get remove notepadqq
    sudo add-apt-repository --remove ppa:notepadqq-team/notepadqq	

六、安装pip
   安装pip的方法：
      Install pip and virtualenv for Ubuntu 16.04LTS Maverick and newer,输入下面命令

      $ sudo apt-get install python-pip python-dev build-essential 
      $ sudo pip install --upgrade pip 
      $ sudo pip install --upgrade virtualenv 
   
七、更换系统源：

  首先备份系统源

    sudo cp /etc/apt/sources-list  /etc/apt/sources-list.bak

  将sources-list更换成下面的源

  清华大学源：
  复制代码

  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial main restricted
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates main restricted
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial universe
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates universe
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-updates multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-backports main restricted universe multiverse
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security main restricted
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security universe
  deb https://mirrors.tuna.tsinghua.edu.cn/ubuntu/ xenial-security multiverse

或阿里源
复制代码
deb-src http://archive.ubuntu.com/ubuntu xenial main restricted #Added by software-properties
deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted
deb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted multiverse universe #Added by software-properties
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted multiverse universe #Added by software-properties
deb http://mirrors.aliyun.com/ubuntu/ xenial universe
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates universe
deb http://mirrors.aliyun.com/ubuntu/ xenial multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse #Added by software-properties
deb http://archive.canonical.com/ubuntu xenial partner
deb-src http://archive.canonical.com/ubuntu xenial partner
deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted multiverse universe #Added by software-properties
deb http://mirrors.aliyun.com/ubuntu/ xenial-security universe
deb http://mirrors.aliyun.com/ubuntu/ xenial-security multiverse

或网易的源
deb http://mirrors.163.com/ubuntu/ zesty main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ zesty-security main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ zesty-updates main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ zesty-proposed main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ zesty-backports main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty-security main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty-updates main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty-proposed main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty-backports main restricted universe multiverse

更新下源

sudo apt-get update
sudo apt-get upgrade
 
八、更换pip源

在用户目录下创建.pip文件夹，并创建pip.conf文件

1 [global]
2 trusted-host =  pypi.mirrors.ustc.edu.cn
3 index-url = https://pypi.mirrors.ustc.edu.cn/simple

或者
  另外一个事情是将pip源指向阿里云的源镜像：http://mirrors.aliyun.com/help/pypi，具体添加一个 ~/.config/pip/pip.conf 文件，设置为：

[global]
trusted-host =  mirrors.aliyun.com
index-url = http://mirrors.aliyun.com/pypi/simple

Ubuntu17.04系统安装完毕之后，首先做两个准备工作，一个是更新apt-get的源，这次用的是网易的源：

deb http://mirrors.163.com/ubuntu/ zesty main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ zesty-security main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ zesty-updates main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ zesty-proposed main restricted universe multiverse
deb http://mirrors.163.com/ubuntu/ zesty-backports main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty-security main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty-updates main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty-proposed main restricted universe multiverse
deb-src http://mirrors.163.com/ubuntu/ zesty-backports main restricted universe multiverse

另外一个事情是将pip源指向清华大学的源镜像：https://mirrors.tuna.tsinghua.edu.cn/help/pypi/，具体添加一个 ~/.config/pip/pip.conf 文件，设置为：

[global]
index-url = https://pypi.tuna.tsinghua.edu.cn/simple

这两件事情都可以加速安装相关工具包的速度，事半功倍。

然后就是给GTX1080显卡安装驱动，参考了这篇文章《How to install Nvidia Drivers on Ubuntu 17.04 & below, Linux Mint》，并且选择了这篇文章所指的最新的381.09驱动：


sudo apt-get purge nvidia*
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt-get update && sudo apt-get install nvidia-381 nvidia-settings

安装完毕后重启电脑即可，运行nvidia-smi即可检验驱动是否安装成功。不过之后在安装CUDA9的时候，又被安利了一次384.69显卡驱动，所以我不太清楚这个过程是否有必要。

2. 安装CUDA TOOLKIT

依然前往NVIDIA的CUDA官方页面，登录后可以选择CUDA9.0版本下载：CUDA Toolkit 9.0 Release Candidate Downloads, 这次我选择的是面向ubuntu17.04的deb版本:

下载完deb文件之后按照官方给的方法按如下方式安装CUDA9：

sudo dpkg -i cuda-repo-ubuntu1704-9-0-local-rc_9.0.103-1_amd64.deb
sudo apt-key add /var/cuda-repo-9-0-local-rc/7fa2af80.pub
sudo apt-get update
sudo apt-get install cuda

安装过程中发现貌似又一次安装了显卡驱动，版本是384.69，安装完毕后运行“nvidia-smi”提示错误：Failed to initialize NVML: Driver/library version mismatch，这个时候是需要重启机器让新的版本的显卡驱动生效，再次运行“nvidia-smi”：

之后可以测试一下CUDA的相关例子，我将cuda9.0下的sample拷贝到一个临时目录下进行编译：


cp -r /usr/local/cuda-9.0/samples/ .
cd samples/
make

然后运行几个例子看一下：

textminer@textminer:~/cuda_sample/samples/1_Utilities/bandwidthTest$ ./bandwidthTest

[CUDA Bandwidth Test] - Starting...
Running on...

Device 0: GeForce GTX 1080
Quick Mode

Host to Device Bandwidth, 1 Device(s)
PINNED Memory Transfers
Transfer Size (Bytes) Bandwidth(MB/s)
33554432 11258.6

Device to Host Bandwidth, 1 Device(s)
PINNED Memory Transfers
Transfer Size (Bytes) Bandwidth(MB/s)
33554432 12875.1

Device to Device Bandwidth, 1 Device(s)
PINNED Memory Transfers
Transfer Size (Bytes) Bandwidth(MB/s)
33554432 231174.2

Result = PASS

NOTE: The CUDA Samples are not meant for performance measurements. Results may vary when GPU Boost is enabled.

textminer@textminer:~/cuda_sample/samples/6_Advanced/c++11_cuda$ ./c++11_cuda

GPU Device 0: "GeForce GTX 1080" with compute capability 6.1

Read 3223503 byte corpus from ./warandpeace.txt
counted 107310 instances of 'x', 'y', 'z', or 'w' in "./warandpeace.txt"

最后在 ~/.bashrc 里再设置一下cuda的环境变量：

export PATH=/usr/local/cuda/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
export CUDA_HOME=/usr/local/cuda

同时 source ~/.bashrc 让其生效。

3. 安装cuDNN

安装cuDNN很简单，不过同样需要前往NVIDIA官网：https://developer.nvidia.com/cudnn，这次我们选择的是cuDNN7, 关于cuDNN7，NVIDIA官方主页是这样写的:

    What’s New in cuDNN 7?
    Deep learning frameworks using cuDNN 7 can leverage new features and performance of the Volta architecture to deliver up to 3x faster training performance compared to Pascal GPUs. cuDNN 7 is now available as a free download to the members of the NVIDIA Developer Program. Highlights include:

    Up to 2.5x faster training of ResNet50 and 3x faster training of NMT language translation LSTM RNNs on Tesla V100 vs. Tesla P100
    Accelerated convolutions using mixed-precision Tensor Cores operations on Volta GPUs
    Grouped Convolutions for models such as ResNeXt and Xception and CTC (Connectionist Temporal Classification) loss layer for temporal classification 

我选择的是这个版本：cuDNN v7.0 (August 3, 2017), for CUDA 9.0 RC --- cuDNN v7.0 Library for Linux

下载完毕后解压，然后将相关文件拷贝到cuda安装目录下即可：

tar -zxvf cudnn-9.0-linux-x64-v7.tgz
sudo cp cuda/include/cudnn.h /usr/local/cuda/include/
sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64/ -d
sudo chmod a+r /usr/local/cuda/include/cudnn.h
sudo chmod a+r /usr/local/cuda/lib64/libcudnn*
	
	    
