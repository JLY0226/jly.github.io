

@[TOC](文章目录)


<hr style=" border:solid; width:100px; height:1px;" color=#000000 size=1">

# 前言

C语言是贝尔实验室在B语言的基础上开发出来的，C 语言之所以发展迅速，而且成为最受欢迎的语言之一，主要是因为它具有强大的功能。许多著名的系统软件，如UNIX/Linux、Windows、DBASE Ⅲ PLUS、DBASE Ⅳ 都是由C 语言编写的。

# 一、C语言的优点有哪些？
说到优点，那就多了去了。C语言主要有以下六大优点：
 ##### <font color=#0dd >简单、快速、高性能、兼容性好、功能强大、易于学习
 <font color=#000 >总之一句话，知道C语言牛逼plus就完事了，想要了解Linux底层原理，那必须好好学习c语言。

# 二、C语言最适合做什么？
 <font color=#0dd > 1.开发小工具

<font color=#0dd >2.和硬件打交道得程序

 <font color=#0dd >3.有高性能要求得应用程序

# 三、Linux环境下学习C语言
## 1.开发环境准备
#### step1:安装Linux虚拟机
推荐下载：

 [UbuntuKylin-desktop-amd64.iso](https://www.ubuntukylin.com/downloads/show.php?id=451&lang=en)

 [VMware Workstation Pro](https://my.vmware.com/cn/web/vmware/downloads/info/slug/desktop_end_user_computing/vmware_workstation_pro/16_0)

#### step2:安装文本编辑器
安装vim：

```
sudo apt-get update
sudo apt-get install vim
```

安装makeFile(自动化编译):
```
sudo apt-get install make
```

## 2.编写C语言
#### step1：进入工作目录
创建名为hello的C语言源文件hello.c
```
mkdir workspace   //创建工作目录
cd workspace      //切换至工作目录
mkdir c           //在工作目录下创建文件名为c的文件夹
cd c              //切换至c目录下
mkdir hello.c    //创建名为hello的c语言文件
vim hello.c      //使用vim编辑器打开文件
```
打开vim编辑器后需按<font color=#ff0000 > i <font color=#000>才可进行编写
```c
#include <stdio.h>

int main()
{
	printf("hello world");
	return 0;
}
```
编辑完成后如需退出，先按<font color=#ff0000 >ESC<font color=#000>回到命令模式，再输入 <font color=#ff0000 >  :wq <font color=#000>，w的意思是保存，q为退出，即先保存后退出，注意需要冒号。如需不保存退出，则输入<font color=#ff0000 > :q！

#### step2 ：编译、执行
```
gcc  hello.c -o hello.out  //编译
./hello.out     //执行
```



<hr style=" border:solid; width:100px; height:1px;" color=#000000 size=1">


## 3.MakeFile编写
make命令执行时，需要一个 Makefile 文件，用来告诉make命令需要怎么样的去编译和链接程序。

```
vi Makefile
```

```c
hello.out : max.o min.o hello.c -o hello.out
    gcc max.o min.o hello.c
max.o : max.c
    gcc -c max.c
min.o : min.c
    gcc -c min.c
```
```
make
```

解释：这段程序是一段简单的求最大值和最小值的一段程序，hello.out依赖于max.o、min.o、hello.c , max.o 依赖于max.c , min.o 依赖于min.c。



# 四、标准输入流、输出流及错误流
#### 标准输出流
```
./hello.out  >> hello.txt  //将hello.c编译执行后的结果不在终端显示，而是输出到hello.txt文本中
./hello.out  > hello.txt   //单箭头为每次执行会覆盖原文本中内容，双箭头则不会覆盖
```

#### 标准输入流
```
./hello.out  < input.txt  //将input.txt文本中的内容作为输入流输入
```
#### 标准错误流
```
fprintf(stderr,"错误");
return 1;
```

# 五、GDB工具
GDB是GNU开源组织发布的一个强大的UNIX下的程序调试工具。
```
gcc -g hello.c -o hello.out
```

显示源代码 —— l
启动单步调试 —— start  
打印变量值 ——  p  变量名   
查看函数堆栈 —— bt  
切入堆栈 —— f 堆栈名  
进入子程序内部 —— s   
单步执行 —— n   
退出 —— q  


# 六、总结
暂时就分享这么多啦，后面会继续更新。。。。。





