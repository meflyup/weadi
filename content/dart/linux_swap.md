---
title: "amazon ami instance上的swap交换文件的设置"
date: 2019-09-22T15:39:11+08:0u0
draft: false
weight: 2
---
### 查看现有swap
```
sudo swapon -s
```
如果有显示，则表示当前系统已经设置了交换文件
### 取消现有交换文件
```
sudo swapoff /xxx/xxx
```
/xxx/xxx是***swapon -s***中显示的文件名

### 新建一个文件，将其转化为swap文件
```
sudo dd if=/dev/zero of=/swapfile bs=1024 count=1048576 
表示创建块为1M,大小为1G的文件
```
```
sudo chmod 600 /swapfile
确保安全
```
```
sudo mkswap swapfile
表示设定该文件为交换文件
```
启用
```
sudo swapon /swapfile
```
然后使用
```
sudo swapon -s 
```
就可以看到了。
为了永久启用这个交换文件，还需要编辑/etc/fstab:
```
sudo vim /etc/fstab
```
添加如下行:
```
/swapfile swap swap defaults 0 0
```