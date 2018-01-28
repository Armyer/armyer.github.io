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
    File "/usr/lib/python3.5/ssl.py", line 929, in recv_into
    return self.read(nbytes, buffer)
File "/usr/lib/python3.5/ssl.py", line 791, in read
return self._sslobj.read(len, buffer)
                             File "/usr/lib/python3.5/ssl.py", line 575, in read
                             v = self._sslobj.read(len, buffer)
                             socket.timeout: The read operation timed out

                                 During handling of the above exception, another exception occurred:

                                      Traceback (most recent call last):
                                          File "/usr/lib/python3/dist-packages/pip/basecommand.py", line 209, in main
                                          status = self.run(options, args)
                                          File "/usr/lib/python3/dist-packages/pip/commands/install.py", line 317, in run
                                          requirement_set.prepare_files(finder)
                                          File "/usr/lib/python3/dist-packages/pip/req/req_set.py", line 360, in prepare_files
                                          ignore_dependencies=self.ignore_dependencies))
                                          File "/usr/lib/python3/dist-packages/pip/req/req_set.py", line 577, in _prepare_file
                                          session=self.session, hashes=hashes)
                                          File "/usr/lib/python3/dist-packages/pip/download.py", line 810, in unpack_url
                                          hashes=hashes
                                          File "/usr/lib/python3/dist-packages/pip/download.py", line 649, in unpack_http_url
                                          hashes)
                                          File "/usr/lib/python3/dist-packages/pip/download.py", line 871, in _download_http_url
                                          _download_url(resp, link, content_file, hashes)
                                          File "/usr/lib/python3/dist-packages/pip/download.py", line 595, in _download_url
                                          hashes.check_against_chunks(downloaded_chunks)
                                          File "/usr/lib/python3/dist-packages/pip/utils/hashes.py", line 46, in check_against_chunks
                                          for chunk in chunks:
                                              File "/usr/lib/python3/dist-packages/pip/download.py", line 563, in written_chunks
                                              for chunk in chunks:
                                                  File "/usr/lib/python3/dist-packages/pip/utils/ui.py", line 139, in iter
                                                  for x in it:
                                                      File "/usr/lib/python3/dist-packages/pip/download.py", line 552, in resp_read
                                                      decode_content=False):
                                                          File "/usr/share/python-wheels/urllib3-1.13.1-py2.py3-none-any.whl/urllib3/response.py", line 344, in stream
                                                          data = self.read(amt=amt, decode_content=decode_content)
                                                          File "/usr/share/python-wheels/urllib3-1.13.1-py2.py3-none-any.whl/urllib3/response.py", line 311, in read
                                                          flush_decoder = True
                                                          File "/usr/lib/python3.5/contextlib.py", line 77, in __exit__
                                                          self.gen.throw(type, value, traceback)
                                                          File "/usr/share/python-wheels/urllib3-1.13.1-py2.py3-none-any.whl/urllib3/response.py", line 231, in _error_catcher
                                                          raise ReadTimeoutError(self._pool, None, 'Read timed out.')
                                                      requests.packages.urllib3.exceptions.ReadTimeoutError: HTTPSConnectionPool(host='pypi.python.org', port=443): Read timed out.
                                                      black@black-U80V ~ $
解决方法：
                                                                                                                 pip --default-timeout=100 install xxxx   // xxxx表示软件名


                                                                                                                      # 2.配置jdk导致 ubuntu无法开机进入桌面：

                                                                                                                          进入recovery mode模式下，按住e进入编辑，将ro recovery nomodeset 改为 rw single init=/bin/bash后按 F10重启进入shell终端后修改之前配置的文件后重启即可。





                                                                                                                          # 3.在虚拟机下与本地文件夹共享

                                                                                                                          进入Ubuntu系统，打开终端，先执行命令，在挂载点目录添加“bdshare”目录，接着执行"mount -t vboxsf BaiduShare /mnt/bdshare/",就能完成共享文件夹的设置。第一个源文件目录，第二个为本地文件目录。



                                                                                                                          # 4. 在虚拟机打开程序报错Failed to open/create the internal network 'HostInterfaceNetworking-wlp3s0' (you might need to modpr .....


                                                                                                                                                                                                                                          Please install the virtualbox-dkmbs package and execute 'modprobe vboxdrv' as root.
                                                                                                                                                                                                                                          解决：etc/init.d/vboxdrv setup 或者 start















                                                                                                                                                                                                                                         )
