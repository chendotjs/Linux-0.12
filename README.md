# Linux-0.12
Linux0.12内核代码中文注释 + 在高版本GCC 5.4.0 + Ubuntu 16.04

编译结果如下:

![image](https://github.com/sky-big/Linux-0.12/blob/master/compile_picture.jpg)


运行结果如下:

![image](https://github.com/sky-big/Linux-0.12/blob/master/run_result.jpg)



运行环境下载地址:
http://oldlinux.org/Linux.old/bochs/linux-0.12-080324.zip

Dockerfile修改自 <https://github.com/ultraji/linux-0.12/blob/master/src/note/%E5%AE%9E%E9%AA%8C%E7%9B%B8%E5%85%B3/%E5%AE%9E%E9%AA%8C%E7%8E%AF%E5%A2%83%E6%90%AD%E5%BB%BA%E5%8F%8A%E8%AF%B4%E6%98%8E.md>

- vnc登陆密码: 123456
- 默认用户: ubuntu
- 用户密码: 123456

用docker挂载宿主机Volume

`docker run -t -i -p 6080:6080 -v /home/chen/tmp/Linux-0.12:/home/ubuntu/Desktop/linux-0.12 -e USER=$USER  -e USERID=$UID chendotjs/ubuntu-xfce-vnc:oslab`

然后 `make CC=gcc-4.8`

编译出的Image就是系统镜像，作为floppya，用qemu和bochs都能启动

Qemu结果:

![image](./qemu-run-kernel.png)

Bochs结果:

![image](./bochs-run-kernel.png)

参考项目：

<https://github.com/ultraji/linux-0.12.git>
