# Docker Learning
## TODO
* 改下ym?源，方便Build

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



## Commands
* You can run docker commands unless to switch to root 

		su

* common commands
	
		docker --help
	
		docker images

		docker ps // 查看所有启动的
		docker ps -a //查看所有启动及非启动的Container

		docker run -d -p 8080:80 --name instanceName xx/yy:version // 跑image (8080是host port, 80是docker port)

		docker exec -it instanceName /bin/bash //到instance里面去跑bash


		docker rm contianer_id //id可以fuzzy
		
	

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

## References
* How to install Dockers
	* [Ubuntu](https://docs.docker.com/engine/installation/linux/ubuntulinux/)
