# Assignment

# Task 1) Install and configure apache/httpd

Step1: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/1.png)

Step2: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/2.png)

# Task 2) Install and configure nginx - configure it to run as reverse proxy to apache
    Webpage should say
   'Hi! i am devops ninja'

Step1: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/3.png)

Step2: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/4.png)

Step3: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/5.png)

Step4: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/6.png)

Step5: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/7.png)

Step6: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/8.png)

Step7: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/9.png)
   
# Task 3) Install and configure 'ntp' - with singapore time zone

Step1: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/10.png)

# Task 4) Install Tomcat version 8 (a brief explaination about the it's directories in doc)

Step1: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/11.png)

Step2: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/12.png)

Step3: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/13.png)

# Task 5) Install java version 8 with home directory set as an environment variable

Step1: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/14.png)

Step2: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/15.png)

Step3: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/16.png)

# Task 6) Install 'build essentials' (mention in doc that why do we need it )

Step1: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/17.png)

Step2: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/18.png)

# Task 7) Install logrotate and rotate tomcat's catalina.out log as:
    rotate the log file after 500kb
    keep only last 5 files
    
Step1: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/19.png)

# Task 8) Make a directory as '/ninja' having one file inside with name 'devops' and share it via nfs & then mount the same on '/mnt'

```javascript
#On the host(for ubuntu/debian):
	sudo apt install nfs-kernel-server
#On the client:
	sudo apt install nfs-common
#Configure host machine
	a.sudo mkdir /ninja ; sudo touch /ninja/devops
	b.sudo chmod -R 665 /ninja
	c.sudo vim /etc/exports
		/ninja/	<client_ip_address>(mount_options)
	d.restart nfs
		sudo systemctl restart nfs-kernel-server
#Configure client machine
	Mount the nfs-shared directory
	sudo mount -t <server_ip>:/ninja /mnt
```
# Task 9) Install git (a brief explaination about - what it is and why do we need it in doc)

Step1: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/20.png)

[Git Ref Link](https://www.atlassian.com/git/tutorials/why-git)

# Task 10) After installing above check the respective logs if everything is installed and running (mention the log files name in doc)
    Also mention other files got created with software installation
 
Step1: 
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%201/media/23.png)
    
 
    
