# Gradle Learning
**[用Gradle构建Spring Boot项目](http://www.cnblogs.com/davenkin/p/gradle-spring-boot.html)** 【可参照此项目做一遍】

[Gradle 完整指南（Android）](http://www.jianshu.com/p/9df3c3b6067a)

## Some context of Gradle
* Groovy 
* Structure

		├── README.md
		├── build.gradle (类比maven parent pom)
		├── gradle
		│   └── wrapper (本地gradle环境，初创者引入，需上传版本库)
		│       ├── gradle-wrapper.jar
		│       └── gradle-wrapper.properties
		├── gradlew (script for linux)
		├── gradlew.bat (scipt for windows: gradle xx等同于./gradlw.bat xx)
		└── src
		    ├── main
		    │   └── java
		    │       └── shishuwu
		    │           ├── Application.java
		    │           ├── HelloController.java
		    │           └── HelloWorld.java
		    └── test
		        └── java

> Note:
>  
> * 推荐使用wrapper: 1. 可使用相同版本gradle 2. 其它使用者无须再安装gradle
> 
## Command Line
* `gradle tasks`: 显示所有tasks
* `gradle build`: 依赖java

		

## Advanced
### Customized Task



## Samples
Find samples from: `./gradle/samples`

### smallest sample
* create `build.gradle`, input:
	
		task helloWorld << {
		   println "Hello World!"
		}

* run command: `gradle helloWorld`
	
		:helloWorld
		Hello World!
		
		BUILD SUCCESSFUL
		
		Total time: 2.544 secs


## Troubling Shootings
### Proxy settings
Go to `USER_HOME/.gradle`, create file `gradle.properties`, and the content is like following:

	# proxy - http
	systemProp.http.proxyHost=HostAddress
	systemProp.http.proxyPort=8080
	systemProp.http.proxyUser=
	systemProp.http.proxyPassword=
	systemProp.http.nonProxyHosts=*.nonproxyrepos.com|localhost
	
	# proxy - https
	systemProp.https.proxyHost=HostAddress
	systemProp.https.proxyPort=8080
	systemProp.https.proxyUser=
	systemProp.https.proxyPassword=
	systemProp.https.nonProxyHosts=*.nonproxyrepos.com|localhost

> Note: Official reference [document](https://docs.gradle.org/current/userguide/build_environment.html#sec:accessing_the_web_via_a_proxy).


## Appendix
* [Gradle学习系列](http://www.cnblogs.com/davenkin/p/gradle-learning-1.html)
	* Github: git clone https://github.com/davenkin/gradle-learning.git