---
title: 分区、shell、进程
date: 2016-08-25 18:20:45
categories:
- 学习笔记
- Linux
tags:
- linux的基本使用
---
此篇讲解了Linux系统的分区、shell和进程的相关知识。
<!-- more -->
# linux分区（挂载和卸载）
### 一块硬盘分为==基本分区==和==扩展分区==(数目和不能大于4)
#### 基本分区(主分区)：可以马上被使用但不能再分区(主分区一般存放操作系统)
#### 扩展分区：必须再进行分区(即逻辑分区，没有数量限制)后才能使用
#### 1、fdisk -l:查看linux系统分区具体情况
    /dev/sda1
    dev代表设备的意思
    sd代表scsi硬盘(还有hd代表IDE硬盘，便宜点)
    a代表第一块硬盘
    1代表第一个分区
#### 2、df [目录全路径]：查看某个目录在哪个分区
#### 3、df [-参数]：查看磁盘使用情况 eg:df -l



# Shell介绍
## Shell种类：
### Shell名称&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;开发者&nbsp;&nbsp;&nbsp;&nbsp;命令名称
### Bourne&nbsp;&nbsp;&nbsp;&nbsp;S.R. Bourne&nbsp;&nbsp;&nbsp;&nbsp;/bin/sh(大陆)
### C&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bill Joy&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/bin/csh
### Kom&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;David&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;/bin/ksh(欧洲)
#### 1、env [该命令可以显示当前操作系统的环境变量]
#### 2、chsh -s 新的shell [shell的修改] eg：chsh -s /bin/csh
    不同的shell命令格式不一样，或者命令有差别
#### 3、命令补全功能：输入一个字母，后按tab键两下
#### 4、history 5：显示最近使用的5个命令（不写数字则显示全部）
#### 5、!5：此项说明执行历史编号为5的命令
#### 6、!ls：此项说明执行最后一次以“ls”开头的命令
# 进程和线程
## 进程：进程就是正在执行的程序
## 线程：
(1)轻量级的进程  
(2)进程有独立的地址空间，线程没有（注：蓝屏有可能读错地址空间，即在内存内查找错误内容）  
(3)线程不能独立存在，它是由进程创建的。（fork）Thread   
(4)相对讲，线程耗费的cpu、和内存小于进程
#### 进程相关命令：
##### ps显示系统执行的进程(静态)
ps -a :显示当前终端的所有进程信息  
ps -u :以用户的格式显示进程信息  
ps -x :显示后台进程运行的参数

ps -aux [看的全面，信息也全面]
##### 终止进程kill/killall
kill 进程号  
kill 16251：终止进程号为16251的进程
kill -9 16251：因为有些进程会捕捉某些信号，如果直接不能结束进程可以用“-9”，传送信息  
killall 进程号：把该进程及该进程所开子进程关闭
##### 动态监控进程top