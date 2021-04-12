# docker安装总结（centos)

注：由于自己服务器之前已安装有docker,并有已经在运行的容器，这里就没有卸载掉在重新安装，总结一下安装过程中常用的命令和对容器和镜像的理解。

#### yum源替换相关：

##### 修改镜像文件来源

yum-config-manager   --add-repo  \

https://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

##### 修改repo配置文件

sed -i 's/download.docker.com/mirrors.aliyun.com\/docker-ce/g'   /etc/yum.repos.d/docker-ce.repo

#### 安装

1、yum install docker-ce docker-ce-cli containerd.io

2、curl   -fsSL  get.docker.com  -o  get-docker.sh

​      sh   get-docker.sh   --mirror Aliyun  （使用脚本自动安装）

#### docker与传统虚拟机的区别

传统虚拟机需要虚拟出一套硬件之后，然后才能在其上运行一个完整的操作系统，并在该系统上再运行所需的应用程序。

容器内的应用程序直接运行于宿主的内核，从文件系统、网络互联到进程隔离。

#### 镜像与容器

镜像是一个特殊的文件系统，除了提供容器运行时所需的程序、库、资源、配置等文件外，还包括一些为运行时准备的一些配置参数（如匿名卷、环境变量、用户）。注：镜像不包含任何动态数据。

容器的实质是进程，容器进程运行于属于自己的独立的命令空间。容器可以被创建、启动、停止、删除、暂停。

镜像与容器的关系就好像面向对象程序设计中的类和实列一样，镜像是静态的定义，容器是镜像运行时的实体。



