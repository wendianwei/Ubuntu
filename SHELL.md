1·Begin:
    The procedure must be begin with the following line:
        #!/bin/sh
		(eg: #!/usr/python)
	If you want to run the archieve.sh file, you should first run:
	    sh chmod +x archieve.sh
		./archieve.sh
	after you run the upper order, the sh ./archieve.sh then can run successfully.

2·Annotation:
    Every sentence begin with # presenting the line is annotation.
  
3·Variable:
    #The variables assignment operation
        a = "hello world"
	
	#Print the variables
	    echo "A is:"
		echo $a
	
	    num = 2
		#The error output:
		    echo "This is the $numnd"
		#The right output:
		    echo "This is ${num}nd"
			#The visual interface will print:
			    This is 2nd
	
4·Environment variable:
    #The variable which dealed by "export" is environment variable, 
	#But the environment variable is always used in sign in

5·Shell order and control process:
    1) echo "Some txt": Print "Some txt" to visual interface
    2) ls: file list
    3) wc -l file_archive.txt: calculate the line in the file_archive
	4) wc -w file_archive.txt: calculate the number of word in file_archive
	5) wc -c file_archive.txt: calculate the number of string in file_archive
	6) cp sourcefile destfile: copy file
	7) mv oldname newname: move file or rename file
	8) rm file_archive.txt: delete file_archive file
	9) rm -rf file: delete file
	10) grep 'wenyan' file_archive: search 'wenyan' in file_archive
	11) cut -b 5-9 file_archive.txt: output the contents from 5 to 9 line
    12) cat file_archive.txt: output file_archive to visual interface
	13) file file_archive: get the type of file_archive
	14) read var: reminder the user input var and assign the  varlue to variable 
	15) sort file_archive.txt: sort the line of file_archive
	16) uniq: delete the line in file 
	    eg: sort file_archive.txt | uniq
	17) expr: math calculate eg: add 2 and 3 expr 2 "+" 3
	18) find file_archive: search file_archive
     	eg: find . -name file_archive -print
	19) tee : output the data to standard devices or file 
	    eg: somecommand | tee file_archive
    20) basename file_archive: return the file name which not incude file path 
        eg: basename /usr/tux ==> tux
	21) dirname file: return the file path
	    eg: dirname /bin/tux ==> /bin
	22) head file: print the first few rows
	23) tail file: print the tail few rows
	24) sed:
	25) awk:
	27) wget: get data from wed
	    eg: wget --no-check-certificate http://www.cs.toronto.edu/~kriz/cifar-10-binary.tar.gz

6·流程控制
    1) if： 表达式 如果条件为真则执行then后面的部分：
        if [ …. ]; then
            ….
        elif [ …. ]; then
            ….
        else
            ….
        fi 
	    通常用" [ ] "来表示条件测试。注意这里的空格很重要。要确保方括号的空格。
        [ -f "somefile"/$somefile ] ：判断是否是一个文件
        [ -x "/bin/ls" ] ：判断/bin/ls是否存在并有可执行权限
        [ -n $var ] ：判断$var变量是否有值
        [ $a = $b ] ：判断$a和$b是否相等
	    [ ! -e "somefile"/$somefile] : 判断somefile是否存在
	    [ -r $somefile ] 判断somefile是否可读
	    
	    eg:
            [ -f "/etc/shadow" ] && echo “This computer uses shadow passwors”
            这里 && 就是一个快捷操作符，如果左边的表达式为真则执行右边的语句
	
    2) case： 表达式可以用来匹配一个给定的字符串，而不是数字。

        case ... in
        
        ...) do something here ;;
        
        esac	
	    eg:
		    file lf.gz

　　        这将返回：

            lf.gz: gzip compressed data, deflated, original filename,

            last modified: Mon Aug 27 23:09:18 2017, os: Unix
		   
		    #!/bin/sh

            ftype=`file "$1"`
            
            case "$ftype" in
            
            "$1: Zip archive"*)
            
            　　unzip "$1" ;;
            
            "$1: gzip compressed"*)
            
            　　gunzip "$1" ;;
            
            "$1: bzip2 compressed"*)
            
            　　bunzip2 "$1" ;;
            
            *) echo "File $1 can not be uncompressed with smartzip";;
            
            esac
	
    3) select: 表达式是一种bash的扩展应用，尤其擅长于交互式使用。用户可以从一组不同的值中进行选择。

        select var in ... ; do
        
        　break
        
        done
        
        .... now $var can be used ....
        
        下面是一个例子：
        
         
        #!/bin/sh
        
        echo "What is your favourite OS?"
        
        select var in "Linux" "Gnu Hurd" "Free BSD" "Other"; do
        
        　　　　break
        
        done
        
        echo "You have selected $var"	
        	
    4) while-loop 将运行直到表达式测试为真。will run while the expression that we test for is true.

        关键字"break" 用来跳出循环。而关键字”continue”用来不执行余下的部分而直接跳到下一个循环。
        
        while ...; do
        
        ....
        
        done
        
        　　
        
        for-loop表达式查看一个字符串列表 (字符串用空格分隔) 然后将其赋给一个变量：
        
        for var in ....; do
        
        　 ....
        
        done
	
7 *:
    在向程序传递任何参数之前，程序会扩展通配符和变量。这里所谓扩展的意思是程序会把通配符（比如*）替换成合适的文件名，它变量替换成变量值。为了防止程序作这种替换，可以使用引号
	eg：
        两个jpg文件， mail.jpg 和tux.jpg
	
	    echo *.jpg
		
		将输出mail.jpg 和 tux.jpg
		
		echo "*.jpg"
		echo '*.jpg'
		讲输出 *.jpg两次
		
	单引号更严格一些，它可以防止任何变量扩展。双引号可以防止通配符扩展但允许变量扩展
	eg:
	    #!/bin/sh

        echo $SHELL
        
        echo "$SHELL"
        
        echo '$SHELL'
        
        　　运行结果为：
        
        /bin/bash
        
        /bin/bash
        
        $SHELL
	
	还有一种防止这种扩展的方法，那就是使用转义字符——反斜杆
	
	
	
	