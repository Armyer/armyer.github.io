---
layout: post
title: configure environment in ubuntu
date: 2016-10-09 20:32:20 +0300
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: post-1.jpg # Add image post (optional)
tags: [Bug]
author: armyer# Add name author (optional)
---

# 1.安装you-get 的python软件报错：sudo pip3 install you-get:

Traceback (most recent call last):
        File "/usr/share/python-wheels/urllib3-1.13.1-py2.py3-none-any.whl/urllib3/response.py", line 226, in _error_catcher
        yield
        File "/usr/share/python-wheels/urllib3-1.13.1-py2.py3-none-any.whl/urllib3/response.py", line 301, in read
        data = self._fp.read(amt)
        File "/usr/share/python-wheels/CacheControl-0.11.5-py2.py3-none-any.whl/cachecontrol/filewrapper.py", line 49, in read
        data = self.__fp.read(amt)
        File "/usr/lib/python3.5/http/client.py", line 448, in read
        n = self.readinto(b)
        File "/usr/lib/python3.5/http/client.py", line 488, in readinto
        n = self.fp.readinto(b)
        File "/usr/lib/python3.5/socket.py", line 575, in readinto
        return self._sock.recv_into(b)
   
解决方法：
                                                                                                                 pip --default-timeout=100 install xxxx   // xxxx表示软件名



# 2.配置jdk导致 ubuntu无法开机进入桌面：

进入recovery mode模式下，按住e进入编辑，将ro recovery nomodeset 改为 rw single init=/bin/bash后按 F10重启进入shell终端后修改之前配置的文件后重启即可。




# 3.在虚拟机下与本地文件夹共享
 进入Ubuntu系统，打开终端，先执行命令，在挂载点目录添加“bdshare”目录，接着执行"mount -t vboxsf BaiduShare /mnt/bdshare/",就能完成共享文件夹的设置。第一个源文件目录，第二个为本地文件目录。


# 4. 在虚拟机打开程序报错 Failed to open/create the internal network 'HostInterfaceNetworking-wlp3s0' (you might need to modpr .....Please install the virtualbox-dkmbs package and execute 'modprobe vboxdrv' as root.
 解决：etc/init.d/vboxdrv setup 或者 start






