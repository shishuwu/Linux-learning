# Linux-learning

## SSH
Use command to connect to Linux system remotely.

	$ ssh username@ip_address

> Note: must specify a user name as the login user. Otherwise, it will your client system default user name.

## Ubuntu
### apt-get
Advanced Package Tool
	
    $sudo apt-get xxx


* Get latest packages list
		
        $sudo apt-get update

### shell
* Update read-only file
		
		sudo <editor> <filename>
		e.g.:
			$sudo vim filename
* Current user
		
		$whoami

* Accept ssh connection

		sudo apt-get update
		sudo apt-get install openssh-server
		sudo ufw allow 22


 	- Client

			ssh username@ip_address, and password. e.g.:
			
			ssh shishuwu@192.168.231.129

* Find directory			
	
		whereis Nginx

* Search in Vim

		If you are working in Ubuntu,follow the steps:
		
		Press / and type word to search
		- To search in forward press 'SHIFT' key with  * key
		- To search in backward press 'SHIFT' key with # key

* Copy file from windows to linux

		scp ms_device-1.0-SNAPSHOT.jar shishuwu@192.168.231.130:/home/shishuwu/Downloads/ms_device-1.0-SNAPSHOT.jar

* Unset Proxy

		unset http_proxy
		unset ftp_proxy
		unset https_proxy

* Find process

		$ ps ax | grep firefox


## Debian
### Shell
* Debian does not support "sudo" by default
	* Install "sudo" related tools OR 
	* Use: su root (switch to root account, then do other operations)

### Best Practice
* Shell error solution:
   
		http://superuser.com/questions/957913/how-to-fix-and-recover-a-corrupt-history-file-in-zsh


