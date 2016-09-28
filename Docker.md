# Docker Learning
## TODO





		

## Definition
* Docker Structure
	* Client
	* Server/Engine
	* Image/Container

			Docker	面向对象
			------------------
			容器		对象
			镜像		类

	* Registry (such as: Docker hub)
	* Dockfile (for build)
		* Stored in github
		* build command line (Dockerfile must be here)
				
				docker build -t xx/yy:version . 		//xx/yy: 你的image名称， . 存放目录

## Installation
### For Linux
* How to install Dockers on
	* [Ubuntu](https://docs.docker.com/engine/installation/linux/ubuntulinux/)
	

### For Windows/Mac
* Need Toolbox & extra docker-machine help
	* docker-machine
		
			docker-machine env
			eval $(docker-machine env)

### Prerequisites
* 国外Docker Hub的镜像获取太慢了
	* [配置 Docker 加速器](https://www.daocloud.io/mirror#accelerator-doc)

## Commands
* You can run docker commands unless to switch to root 

		su

* common commands
	
		docker --help
	
		docker images

		docker ps // 查看所有启动的
		docker ps -a //查看所有启动及非启动的Container

		docker run -d -p 8080:80 --name instanceName xx/yy:version // 跑image (-d:后台，8080是host port, 80是docker port)

		docker exec -it instanceName /bin/bash //到instance里面去跑bash

		
		docker rm contianer_id //id可以fuzzy(至少3个字符)
		docker rmi image_id
	

## Best Practices
* [Tag, push, and pull your image](https://docs.docker.com/engine/getstarted/step_six/)
	
		name the image & push
		
		$ docker tag 7d9495d03763 shishuwu/image-name:latest
		
		$ docker push shishuwu/image-name

		$ docker pull shishuwu/image-name

## Dockerfile
### sample


### VOLUMN ["/var/lib/mysql"] 
	* 指定保存文件
	* 在启动容器时，也可以指定
		
			docker run -d -p 3306:3306 -v host_dir:container_dir

			
		
		Note: instance可以stop,数据还在。如果把instance彻底删除，这时可以根据image创建instance,用-v重新map一下就可以了

### ENTRYPOINT

===========================

## Docker Registry
Store images, ...
### public 
* docker hub

### private
We could create hub by ourself... Such as:

* [csphere?](https://hub.docker.com/r/csphere/csphere/)
* TBC

===========================

## Docker Compose
Run multiple containers by one command

* docker-compose.yml

		sample: 

### commands
	docker-compose up -d //启动多个容器 （配置在 yml文件里）
	docker-compose stop // 停止。。。
	docker-compose ps //查看docker容器
	docker-compose rm //删除docker容器




## CI/CD
1. Build一个带Jenkins的image
2. Run这个image
	1. 通过v挂载host的 docker程序
		1. /usr/bin/docker
		2. /var/run/docker.sock
	3. 通过v挂载host的 maven程序
		1. /root/maven-tar????


3. 通过其它机器访问 Jenkins网页（上面Run的时候已经对外暴露端口了）

4. 创建Project
	1. Git pull Dockerfile
	2. Write script to build docker: docker build ...

5. 创建Project （代码）
	1. Git pull code
	2. 写构建脚本 ????
		1. docker build maven
		2. docker create maven
		3. docker build code
		4. docker push

## References

	
