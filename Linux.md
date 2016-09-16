# Linux-learning

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

### Best Practice
* Shell error solution:
   
		http://superuser.com/questions/957913/how-to-fix-and-recover-a-corrupt-history-file-in-zsh


