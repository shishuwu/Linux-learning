# Gradle Learning

[Gradle 完整指南（Android）](http://www.jianshu.com/p/9df3c3b6067a)

## Some context of Gradle
* Groovy 
* Structure

		|--build.gradle (像maven的parent pom)
		|--settings.gradel
		|--app
			|--build.gradle



## Command Line

## Samples
Find samples from: `./gradle/samples`


## Troubling Shootings
### Proxy settings
Go to `USER_HOME/.gradle`, create `gradle.properties`, and the content is like following:

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