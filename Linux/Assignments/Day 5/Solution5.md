# Assignment 5

# Task1) How would you check

* Memory used by a process(RAM):
  ```
  i) free command
  e.g. free -m 
  The m option display all data in mbs

  ii) /proc/meminfo
  e.g. cat /proc/meminfo
  
  iii) vmstat
  e.g.vmstat -s
  The s option, lays out the memory usage statistics much like the proc command.
 
  iv) top command
  e.g. top
  The top command is generally used to check memory and cpu usage per process.
  
  v) htop
  e.g. htop
  It is not available by default. You need to install it
  
  vi) demidecode command
  eg. sudo dmidecode 
  Displays out hardware information about the installed RAM

  [Link](https://www.binarytides.com/linux-command-check-memory-usage/)
  ```
  
* total number of open files by a process:
  ```
  Note: first we need get the process id (pid) of the process.
  Step1) Simply use any one of the following command to obtain process id:
  - ps -aef | grep {process-name} e.g.  ps -aef | grep httpd
  - ps aux | grep {program-name} 
  - ps -C {program-name} -o pid=  e.g. ps -C firefox -o pid=
  
  Step2) Then you may know number of open files by a process using these commands
  i) pfiles {PID}
  ii) ls -l /proc/{PID}/fd
  iii) lsof -p {PID}
  
  Ref. Link: https://www.cyberciti.biz/faq/howto-linux-get-list-of-open-files/
  ```
* running duration of a process:
  ```
  Step1) Find PID of a process (say openvpn)
  e.g. pidof openvpn
  
  Step2) How to check how long a process has been running?
  You need to pass the -o etimes or -o etime to the ps command. The syntax is:
  ps -p {PID-HERE} -o etime
  ps -p {PID-HERE} -o etimes
  e.g. ps -p 6176 -o pid,cmd,etime,uid,gid

  Note: etime Display elapsed time since the process was started, in the form [[DD-]hh:]mm:ss.
  etimes Display elapsed time since the process was started, in seconds.

  Ref. Link: https://www.cyberciti.biz/faq/how-to-check-how-long-a-process-has-been-running/
  ```
# Task2) What is file descriptor
  ```
  In simple words, when you open a file, the operating system creates an entry to represent that file 
  and store the information about that opened file. 
  So if there are 100 files opened in your OS then there will be 100 entries in OS (somewhere in kernel). 
  These entries are represented by integers like   (...100, 101, 102....). 
  This entry number is the file descriptor. So it is just an integer number that uniquely represents an opened file in operating system. 
  If your process opens 10 files then your Process table will have 10 entries for file descriptors.

  Similarly when you open a network socket, it is also represented by an integer and it is called Socket Descriptor.
   ```
# Task 3) How to kill a process
  ```
  i) kill [signal or option] PID(s)
  ii) pkill {process name}

  Signal Name		Signal Value			Behaviour

  SIGHUP	     	1				          Hangup
  SIGKILL		    9				          Kill Signal
  SIGTERM		    15				        Terminate
  
  SIGTERM is the default and safest way to kill a process. 
  SIGHUP is less secure way of killing a process as SIGTERM. 
  SIGKILL is the most unsafe way among the above three, to kill a process which terminates a process without saving.
  
  Ref Link: https://www.tecmint.com/how-to-kill-a-process-in-linux/
  ```
# Task 4) What is parent process ID
  ```
  How to get parent from child pid
  ps -o ppid= -p {child process id}
  ```
# Task 5) Print pid of current shell
  ```
  echo $$
  ```
# Task 6) How to clear a log file of running process
  ```
  Empty File Content by Redirecting to Null
  > access.log
  
  Ref. Link https://www.tecmint.com/empty-delete-file-content-linux/
  ```
# Task 7) What are Running, Waiting, Stopped and Zombie processes
  ```
  Running
The process is either running (it is the current process in the system) or it is ready to run (it is waiting to be assigned to one of the system's CPUs).
Waiting
The process is waiting for an event or for a resource. Linux differentiates between two types of waiting process; interruptible and uninterruptible. Interruptible waiting processes can be interrupted by signals whereas uninterruptible waiting processes are waiting directly on hardware conditions and cannot be interrupted under any circumstances.
Stopped
The process has been stopped, usually by receiving a signal. A process that is being debugged can be in a stopped state.
Zombie
This is a halted process which, for some reason, still has a task_struct data structure in the task vector. It is what it sounds like, a dead process.
  
  Ref. Link https://www.tldp.org/LDP/tlk/kernel/processes.html
  ```
 # Task 8) What init process is responsible for
  ```
 The first process that starts when Linux System is booted is – init process, 
  hence it is   assigned a value of ‘1‘ in most of the cases.
  Init is the master process and can not be killed this way, which insures that the master process  don’t gets killed accidentally. 
  Init decides and allows itself to be killed, where kill is merely a  request for a shutdown.
  ```
  # Task 9) How do you you elevate the priority of a process
  ```
 Ref. Link: https://www.thegeekstuff.com/2013/08/nice-renice-command-examples/?utm_source=tuicool
  ```
   # Task 10) How do you check those process that are waiting for the resources
  ```
 Ref. Link: http://osr507doc.xinuos.com/en/PERFORM/tool_ps.html
  ```
   # Task 11) What are stdin, stdout, and stderr and how do we use them
  ```
 Ref. Link: http://www.learnlinux.org.za/courses/build/shell-scripting/ch01s04.html
  ```
   # Task 12) How many tables are there in iptables. What filter and nat table responsible for
  ```
 Ref. Link: https://www.thegeekstuff.com/2011/01/iptables-fundamentals
  ```
  
 
