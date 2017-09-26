# Maven

## Goals



## setting.xml
It is the whole maven configuration entrance.

### Repository
There is default repository directory in this file. You can customize your own path.


### Proxy
If your environment is behind proxy, then you need to configure the proxy.



### Mirror
Sometimes, the default official mirror might have problems, such as:

* network is poor 
* behind proxy
* ...

Then, you could specify a customized mirror, such as 阿里's mirror.

	<mirror>
        <id>nexus-aliyun</id>
        <mirrorOf>*</mirrorOf>
        <name>Nexus aliyun</name>
        <url>http://maven.aliyun.com/nexus/content/groups/public</url>
    </mirror>
  