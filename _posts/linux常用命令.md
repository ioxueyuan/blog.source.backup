---
title: linux常用命令
date: 2016-07-20 21:39:50
categories:
- 学习笔记
- Linux
tags:
- 常用命令
---
此篇文章列出Linux学习中记录的常用命令！
<!-- more -->
## 列出文件和目录
#### 1、ls -a：显示隐藏文件
#### 2、ls -l：显示长列表格式
#### 3、mkdir：新建一个目录
#### 4、rmdir：删除一个空目录
#### 5、touch：建立空文件
#### 6、cp 复制命令
- cp 文件 dir：复制文件到dir目录
- cp -r dir1 dir2：递归复制命令（复制子目录信息）

#### 7、mv 移动文件和改文件名
#### 8、rm 删除文件和目录
- rm -rf *：删除所有内容(包括目录和文件) r递归 f强制

#### 9、more 显示文件内容，带分页 more xxx.log (空格键是下一页，Ctrl + Page up上一页)
#### 10、less 显示文件内容带分页
#### 11、grep 在文本中查询内容
- grep "shunping" aaa.java
- grep -n "zhongqiang" aaa.java 显示行数

#### 12、| 管道命令
#### 13、man：帮助命令 全称manual 手册
#### 14、find：查找命令
- find / -name aaa.java 在根目录下找名字为aaa.java的文件

#### 15、重定向命令
- ls -l > aaa.txt 把ls -l命令执行的结果存到aaa.txt文件中，如果该文件不存在则创建否则覆盖
- ls -al >> aaa.txt 把执行结果追加到aaa.txt

#### 16、终止命令(强制中断程序的执行，进程终止)：Ctrl+c
#### 17、挂起进程：Ctrl+z

```
fg:重新启动前台中断
bg:中断任务后台执行
```
