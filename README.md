
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
			 
    	
	
	
	    
