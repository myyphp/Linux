#linux文件系统及基本命令
***
login:
	用户名：用户ID 系统内部都是通过检查用户ID来判断用户的
	
认证机制：Authentication

授权：Authorization 检查用户具有哪些权限

审计：Audition (日志) 纪录用户操作的行为

prompt,命令提示符:

命令：

magic number: 魔数（判断命令的执行类型）

shebang

#!/bin/bash

# command  options...  arguments...

选项：
>> －短选项（可以组合使用）

>> －－长选项

参数：命令的作用对象

list: ls

列出，列表

目录：文件，路径映射

路径：从指定起始点到目的地所经过位置的集合

文件系统：file system

列出指定路径下的文件


目录：working directory, current directory

 当用户登录系统成功后，默认是出于某一目录的

pwd: Printing Working directory

ls
	-l：长格式

		文件类型：

			-：普通文件 (f)

			d: 目录文件

			b: 块设备文件 (block)

			c: 字符设备文件 (character)

			l: 符号链接文件(symbolic link file)

			p: 命令管道文件(pipe)

			s: 套接字文件(socket)

		文件权限：9位，每3位一组，每一组：rwx(读，写，执行), r--

		文件硬链接的次数

		文件的属主(owner)

		文件的属组(group)

		文件大小(size)，单位是字节

		时间戳(timestamp)：最近一次被修改的时间

			访问:access

			修改:modify，文件内容发生了改变

			改变:change，metadata，元数据

	-h：做单位转换

	-a: 显示以.开头的隐藏文件

		. 表示当前目录

		.. 表示父目录

	-A

	-d: 显示目录自身属性

	-i: index node, inode

	-r: 逆序显示

	-R: 递归(recursive)显示
	
cd: change directory

	家目录，主目录, home directory

	cd ~USERNAME: 进入指定用户的家目录

	cd -:在当前目录和前一次所在的目录之间来回切换

命令类型：

	内置命令(shell内置)，内部，内建

	外部命令：在文件系统的某个路径下有一个与命令名称相应的可执行文件
	

环境变量：命名的内存空间

	变量赋值

		NAME=Jerry
		

	PATH: 使用冒号分隔的路径

	O(1)

type: 显示指定属于哪种类型
	
date：时间管理

Linux: rtc

	硬件时钟

	系统时钟


获得命令的使用帮助：

内部命令：

	help COMMAND

外部命令：

	COMMAND --help
	
命令手册：manual

man COMMAND

whatis COMMAND


分章节：

1：用户命令(/bin, /usr/bin, /usr/local/bin)

2：系统调用

3：库用户

4：特殊文件(设备文件)

5：文件格式(配置文件的语法)

6：游戏

7：杂项(Miscellaneous)

8: 管理命令(/sbin, /usr/sbin, /usr/local/sbin)

<>：必选

[]：可选

...：可以出现多次

|：多选一

{}：分组

MAN：

	NAME：命令名称及功能简要说明

	SYNOPSIS：用法说明，包括可用的选项

	DESCRIPTION：命令功能的详尽说明，可能包括每一个选项的意义

	OPTIONS：说明每一个选项的意义

	FILES：此命令相关的配置文件

	BUGS：

	EXAMPLES：使用示例

	SEE ALSO：另外参照

翻屏：

	向后翻一屏：SPACE

	向前翻一屏：b

	向后翻一行：ENTER

	向前翻一行：k

查找：

/KEYWORD: 向后

n: 下一个

N：前一个 


?KEYWORD：向前

n: 下一个

N：前一个 

q: 退出


在线文档：

info COMMAND

文档：/usr/share/doc

google

apache, hadoop

练习：

	使用date单独获取系统当前的年份、月份、日、小时、分钟、秒
	

hwclock

	-w: 将软件时间写入到硬件系统 

	-s: 反之


cal: calendar

练习：

1、echo是内部命令还是外部命令？

2、其作用？

3、如何显示“The year is 2013. Today is 26.”为两行？

转义，逃逸

练习：

1、printf是内部命令还是外部命令？

2、其作用？

3、如何显示“The year is 2013. Today is 26.”为两行？

file命令及其用法。


Windows: PE

Linux: ELF



文件系统：

rootfs: 根文件系统

FHS：Linux （规定Linux的文件系统）

/boot: 系统启动相关的文件，如内核、initrd，以及grub(bootloader)

/dev: 设备文件

	设备文件：

		块设备：随机访问，数据块

		字符设备：线性访问，按字符为单位

		设备号：主设备号（major）和次设备号（minor）

/etc：配置文件

/home：用户的家目录，每一个用户的家目录通常默认为/home/

USERNAME

/root：管理员的家目录；

/lib：库文件

	静态库,  .a （直接包含在程序里面）

	动态库， .dll, .so (shared object)（多个程序可以共享一个库文件，节省内存）

/lib/modules：内核模块文件

/media：挂载点目录，移动设备

/mnt：挂载点目录，额外的临时文件系统

/opt：可选目录，第三方程序的安装目录

/proc：伪文件系统，内核映射文件

/sys：伪文件系统，跟硬件设备相关的属性映射文件

/tmp：临时文件, /var/tmp

/var：可变化的文件

/bin: 可执行文件, 用户命令

/sbin：管理命令

/usr：shared, read-only

	/usr/bin

	/usr/sbin

	/usr/lib
	
/usr/local：

	/usr/local/bin

	/usr/local/sbin

	/usr/local/lib

命名规则：

1、长度不能超过255个字符；

2、不能使用/当文件名

3、严格区分大小写

相对路径：

绝对路径：



文件管理
	
目录管理

ls

cd

pwd

mkdir：创建空目录

	-p:

	-v: verbose

/root/x/y/z

/mnt/test/x/m,y

mkdir -pv /mnt/test/x/m /mnt/test/y

mkdir -pv /mnt/test/{x/m,y}

~USERNAME 

命令行展开：

/mnt/test2/

a_b, a_c, d_b, d_c

(a+d)(b+c)=ab+ac+db+dc

{a,d}_{b,c}


# tree：查看目录树

删除目录：rmdir (remove directory)

	删除空目录

	-p
	
文件创建和删除

# touch （主要是更改文件的时间戳信息，文件不存在则创建）

	-a

	-m

	-t

	-c

# stat （查看文件的时间戳信息）

创建文件，可以使用文件编辑器

ASCII: 

128不同的字符：
	
二进制：

		2^6=0,63

		2^7=0,127

		000 0000 - 111 1111

ASCII:		

0000 1001: t

2^16: 65536

标准：GB18030, GBK, GB2312，Unicode

0000 1001 0000 1110：上， 卫

nano

删除文件：rm

	-i

	-f

	-r
	
rm -rf /

练习：

1、创建目录

(1)在/mnt下创建boot和sysroot；

(2)在/mnt/boot下创建grub；

(3)在/mnt/sysroot下创建proc, sys, bin, sbin, lib, usr, var, etc, dev, home, 
root, tmp

	a)在/mnt/sysroot/usr下创建bin, sbin, lib

	b)在/mnt/sysroot/lib下创建modules

	c)在/mnt/sysroot/var下创建run, log, lock

	d)在/mnt/sysroot/etc下创建init.d
	

复制和移动文件

cp： copy

cp SRC DEST

	-r

	-i

	-f

	-p

	-a：归档复制，常用于备份
	

cp file1 file2 file3

一个文件到一个文件

多个文件到一个目录

cp /etc/{passwd,inittab,rc.d/rc.sysinit} /tmp/

mv: move

移动文件

mv SRC DEST

mv -t DEST SRC


install

	-d DIRECOTRY ... ：创建目录

	SRC DEST

install -t DIRECTORY SRC...

作业1：

1、创建目录/backup

# mkdir -v /backup

2、复制目录/etc至/backup目录中，并重命名为“etc-当前日期”，如
etc-2013-02-26；要求保留文件原来的属性，保持链接文件；

cp

	-r 

	-p

	-d

# cp -a /etc /backup/etc-2013-02-28

命令替换
	
3、复制文件/etc/inittab为/tmp/inittab.new，并删除inittab.new文件的后两行；

# cp /etc/inittab  /tmp/inittab.new

# nano /tmp/inittab.new

作业2：

1、思考：ls命令是否可以显示某目录的整体大小，即包括其内部的所有文
件的整体大小？

2、通过帮助手册，学习使用du命令；

# du 

	-s

	-h
3、通过帮助，学习read命令；

变量：内存空间，有名称

变量赋值：

变量替换

作业3：

描述GPL, BSD, Apache三个开源协定的大体联系及区别。

自由软件

开源协定，版权描述


作业4：

1、如何获取Linux当前最新的内核版本号？
	www.kernel.org

2、列出你所了解的Linux发行版，并说明其跟Linux内核的关系。

	Linux, GNU: GNU/Linux, 源代码
	

	发行版：Fedora, RedHat(CentOS), SUSE, Debian(Ubuntu, Mint), Gentoo, LFS(Linux From Scratch)
	
C, Tom, AMD, Jerry, 

RedHat: 通用格式

奔腾：


运行程序

设备管理

软件管理

进程管理

网络管理


目录管理：

ls、cd、pwd、mkdir、rmdir、tree

文件管理：

touch、stat、file、rm、cp、mv、nano

日期时间：

date、clock、hwclock、cal

查看文本：

cat、tac、more、less、head、tail

cat：连接并显示

	-n

	-E
	
***
#备注信息
1.  ＃ \ls     (\可以使得命令去除掉默认选项来执行)

2.  ＃ hash       (查看系统换成的命令信息，让执行命令的时候，会默认在环境变量里面查找，当找到之后，就缓存在内存中，下次直接从缓存中获取)
