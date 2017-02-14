---
layout: post
title: linux常用命令之文件查找
categories: linux
description: linux常用命令
keywords: linux
---

## 查找文件

### which 寻找执行文件

命令：

	**which** [-a] command

参数：

	-a：将所有的有PATH目录汇总可以找到的命令均列出，而不只第一个被找到的命令名称

示例: 

	which ifConfig

### 文件名的查找

1 **wherehis** 寻找特定文件

命令：

	whereis [-bmsu] 文件或目录名

参数：

	-b:只找二进制格式的问题件
	-m：只找在说明文件manual路径下的文件
	-s：只找source源文件
	-u：查找不在上述三个选项中的其他特殊文件


> whereis 命令只能用与程序名的搜索，而且只搜索二进制文件、man说明文件和源代码文件。


2、 **find** 寻找文件

命令:
	
	find  [path] [option] [action]

(1) 与时间有关的参数：共有 -atime、-ctime与-mtime 

说明： 
	
	-mtime n：n为数字，意为在n天之前的"一天之内"被更改过的文件名；
	-mtime +n:列出在n天之前（不含n天本身）被更改过的文件名；
	-mtime -n：列出在n天之前（含n天本身）被更改过的文件名；

示例：

	将过去系统上面24小时内有改动的文件列出
	find / -mtime 0 

	寻找/etc 下面的文件，如果文件日期比/etc/passwd新就列出
	find /etc -newer /etc/passwd

(2) 与用户或用户组名有关的参数

	-uid n: n为数字，这个数字是用户的账号ID，即UID
	-gid n：n为数字，这个数字是用户组名的ID ，即UID
	-user name: name为用户名的名称
	-group name： name为用户组名
	-nouser : 寻找文件的所有者不存在/etc/passwd 的人
	-nogroup: 寻找文件的所有用户组不存在于/etc/group的文件

> 当你自行安装软件时，很可能该袁健的属性当中并没有文件所有者


示例：
	
	查找/home 下面属于 vbird 的文件
	find /home/ -user vbird
	查找系统中不属于任何人的文件
	find / -nouser

(3) 与文件权限及名称有关的参数

	-name filename ： 查找文件名为filename 的文件。
	-size [+-] SIZE:  查找比SIZE还要大（+）或者小（-）的文件。size 的规格有 c:代表 byte ，k:代表bytes。所以要找比50kb 还要大的文件，就是“-size +50K”
	-type TYPE: 查找文件的类型为TYPE的，类型主要有：一般正规文件 f、设备文件 b,c、 目录 d 等
	-perm mode:查找文件权限“刚好等于”mode 的文件，这个mode的类似chmod的属性值，-rwsr-xr-x 属性值为 4755
	-perm +mode：查找文件权限包含任一 mode 的文件

示例：
	
	找出文件名为passwd的这个文件
	find / -name passwd
	
(4) 其他可进行的操作：

	-exec command : command 为其他命令 ， -exec后面可在接其他命令来处理找到的结果
	-print ：将结果打印到屏幕上，这个操作是默认操作

示例：
	
	将找到的文件使用 ls -l 列出来
	find / -perm +7000 -exec ls -l {} \; 


3、 **locale** 寻找文件

					
 
	
	



