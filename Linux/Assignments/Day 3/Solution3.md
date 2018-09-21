# Assignment 3

# Task1 Read about the below topics

1) SED

```
SED command in UNIX is stands for stream editor and it can perform lot’s of function on file like, searching, 
find and replace, insertion or deletion. Though most common use of SED command in UNIX is for substitution 
or for find and replace. By using SED you can edit files even without opening it, 
which is much quicker way to find and replace something in file, than first opening that file in VI Editor and then changing it.

The basic usage is:

sed [options] commands [file-to-edit]

General syntax for sed −

/pattern/action

Some important Blogs:
https://www.digitalocean.com/community/tutorials/the-basics-of-using-the-sed-stream-editor-to-manipulate-text-in-linux
https://www.computerhope.com/unix/used.htm
https://www.tutorialspoint.com/unix/unix-regular-expressions.htm
https://www.tecmint.com/linux-sed-command-tips-tricks/
https://www.linuxtechi.com/20-sed-command-examples-linux-users/
```

2) AWK 

```
Awk is a programming language which allows easy manipulation of structured data and the generation of formatted reports. 
The Awk is mostly used for pattern scanning and processing. 
It searches one or more files to see if they contain lines that matches with the specified patterns and then perform associated actions.

Some of the key features of Awk are:

  - Awk views a text file as records and fields.
  - Like common programming language, Awk has variables, conditionals and loops
  - Awk has arithmetic and string operators.
  - Awk can generate formatted reports
  - Awk reads from a file or from its standard input, and outputs to its standard output. Awk does not get along with non-text files.

Awk Blog:
https://www.thegeekstuff.com/2010/01/awk-introduction-tutorial-7-awk-print-examples
https://www.cse.iitb.ac.in/~br/courses/cs699-autumn2013/refs/awk-tutorial.html
https://likegeeks.com/awk-command/
```

3) shebang

```
The shebang is a special character sequence "#!" located at the top of many script file. 
It specifies which program should be called to run the script. 
The shebang is always on the first line of the file, and is composed of the characters #! followed by the path to the interpreter program. 
 For example, in a shell script, the complete line may look similar to the following:
 #!/bin/bash

The #! syntax used in scripts to indicate an interpreter for execution of script under UNIX / Linux operating systems.
```

4) exit status

```
Each Linux command returns a status when it terminates normally or abnormally. You can use command exit status in the shell script to display an error message or take some sort of action.

Exit codes are a number between 0 and 255, which is returned by any Unix command when it returns control to its parent process.
Other numbers can be used, but these are treated modulo 256, so exit -10 is equivalent to exit 246, and exit 257 is equivalent to exit 1.
These can be used within a shell script to change the flow of execution depending on the success or failure of commands executed.
Success is traditionally represented with exit 0; failure is normally indicated with a non-zero exit-code.

check exit status of command using echo $?
```

# Task2

Make a script and pass 5 command line arguments(arguments value should be interger)

print 1st and 5th command line arguments
print "INDIA" if 2nd argument equal to 10 else it will print "india"
print addition of all arguments

```
#!/bin/bash
#print 1st and 5th command line arguments
#print "INDIA" if 2nd argument equal to 10 else it will print "india"
#print addition of all arguments

echo "First command line argument is $1 and Fifth command line argument is $5"

if [ $2 -eq 10 ]; then
 echo "INDIA"
else
 echo "india"
fi

for var in "$@"
do
sum=$(expr $sum + $var)
done
echo "Sum of all arguments is: $sum"                                    
```
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%203/media/1.png)

# Task3

Make a script and pass one command line arguments(use loop)

print the table of command line argument if value is less 10
print 5 times "INDIA" if value is greater than or equal to 10

```
#!/bin/bash
#print the table of command line argument if value is less 10
#print 5 times "INDIA" if value is greater than or equal to 10

if [[ $1 -lt '10'  ]] ; then
        for (( i=1; i<=10; i++ ))
                do
                        echo " $1 * $i = $(( $1 * $i )) "
                        #echo "$res"
                        #echo " $1 * $i = $res "
                done
else
        for (( i=1; i<=5; i++ ))
                do
                        echo "INDIA"
                done
fi                                    
```
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%203/media/2.png)

# Task4

Make a script and print your name 10 times(use fuction to print your name)

```
#!/bin/bash
#!/bin/bash
#Make a script and print your name 10 times(use fuction to print your name)
print_name(){
echo "Ekansh Jain"
}

for (( i=1; i<=10; i++ ))
do
print_name
done

```
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%203/media/3.png)

# Task5

Make a excel sheet manually with 5 column, and print the 1st,3rd and 5th column

![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%203/media/4.png)

```
awk '{ if(NR%2 != 0) print $1 }' sample.csv
```

# Task6

Install the zabbix-agent using shell script

```
# Only run it if we can (ie. on Ubuntu/Debian)
if [ -x /usr/bin/apt-get ]; then
  sudo apt-get update
  sudo apt-get -y install zabbix-agent sysv-rc-conf
  sudo sysv-rc-conf zabbix-agent on
  sudo sed -i 's/Server=127.0.0.1/Server=zabbix.opstree.com/' /etc/zabbix/zabbix_agentd.conf
  sudo sed -i 's/ServerActive=127.0.0.1/ServerActive=zabbix.opstree.com/' /etc/zabbix/zabbix_agentd.conf
  HOSTNAME='192.168.22.10-zabbixagent' && sudo sed -i "s/Hostname=Zabbix\ server/Hostname=$HOSTNAME/" /etc/zabbix/zabbix_agentd.conf
sudo service zabbix-agent restart
fi
```
![alt text](https://github.com/helloekansh/ot-training/blob/master/Linux/Assignments/Day%203/media/5.png)
