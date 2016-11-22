# docker主要命令
#对于 Docker 来说，其实容器和镜像的差别并不大。容器可以认为是已经运行过的或正在运行的镜像，只不过是镜像上面添加了几个改动层。
#当然，大部分镜像也是如此。例如某些 mysql 镜像，便仅仅是在官方 ubuntu 镜像的基础上增加了一个 mysql 改动层。
	docker ps -a
		#Docker 会为所有已经运行（包括已经停止）的容器随机分配一个唯一的名字和一个唯一的 ID，docker 命令可以识别 ID，也可以识别这个名字。
	
	docker run -it ubuntu
		#使用 -i（交互式）和 -t（临时终端）参数运行一个容器ubuntu.每次运行 docker run 命令的时候，Docker 都会指定新建容器，并且为容器自己的改动层。
	
	docker start -ai ubuntu
		#使用 -a 参数将容器的输出导出到终端，同时使用 -i 参数进行交互式的操作。这条命令可以让我们继续运行容器 ubuntu
	
	docker commit -a "Jordan Bach" -m "saved my message" insane_wright billhe/message:v0.0.1
		#本条命令将容器 insange_wright 的改动层的属性变为“只读”，并且指定存储为 billhe/message 镜像。
		#镜像基于原 ubuntu 镜像，增加了一个改动层，标签为 v0.0.1。标签可以为任意，当然一般用来记录版本信息。
	docker run -it billhe/message:v0.0.1
		#运行上面存储的镜像
	
	docker images
		#检查当前的镜像
		
	docker rm ubuntu
		#删除容器
	
	docker rmi billhe/message
		#删除镜像
#主流镜像地址
	http://www.linuxidc.com/Linux/2015-09/122750.htm
