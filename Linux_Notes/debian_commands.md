
### File/Directory Commands


file.exe - an executable file, or program.

| Command       | Usage & Explanation  |
| ------------- |:-------------:|
| `~` | This is a shortcut for your home directory. eg, if your home directory is /home/ryan then you could refer to the directory Documents with the path /home/ryan/Documents or ~/Documents. |
| `.`| This is a reference to your current directory. eg in the example above we referred to Documents on line 4 with a relative path. It could also be written as ./Documents (Normally this extra bit is not required but in later sections we will see where it comes in handy).      |`..`| This is a reference to the parent directory. You can use this several times in a path to keep going up the hierarchy. eg if you were in the path /home/ryan you could run the command ls ../../ and this would do a listing of the root directory.|
|`man <command to look up>` or `man -k <search term>`|synopsis. This is really just a quick overview of how the command should be run. Square brackets ( [ ] ) indicate that something is optional. (option on this line refers to the command line options listed below the description)
To exit the man pages press 'q' for quit.|
|`cp`| Copy - ie. Copy a file or directory|
|`mv`| Move - ie. Move a file or directory (can also be used to rename).|
|`ls`| List files/directories in a directory.|
|`ls -l`| Lists all the files and their permissions.|
|`ls -p`| List files and their type (directory/file).|
|`pushd` or`popd`| Put working directory on a stack|
|`file <arg>`| Determine file type|
|`locate`| Find files by name|
|`updatedb`| Update database for locate|

#### Wild Cards
| Command       | Usage & Explanation  |
| ------------- |:-------------:|
|`*` |Represents zero or more characters|
|`?` |Represents a single character|
|`[]`|Represents a range of characters|

### Trouble Shooting
|`<filename> .bash_history`| of any file lists the last user that modified it and when.|
|`top`|Lists all the processes that are running that can fit in terminal window|
|`ps aux`|Lists all the processes that are running.|
|`ps`|Lists all the processes that are running in the terminal.|
|`kill <PID>`| eg: `kill 6978` or  `kill -9 6978`. `-9` argument kills it more if the first kill didn’t work.|

### Help
which - locate a command 
history - display bash command history

 GETTING HELP 
whatis - display the on-line manual descriptions 
apropos - search the manual page names and descriptions
man - an interface to the on-line reference manuals 

WORKING WITH FILES
cp - copy files and directories
mv - move (rename) files

TEXT FILES
cat - concatenate files and print on the standard output 
more/less - file perusal filter for crt viewing 
nano - command line text editor 

USERS 
sudo - execute a command as superuser 
su - change user ID or become another user 
users - print the user names of users currently logged in 
id - print real and effective user and group IDs 

CHANGING FILE PERMISSIONS 
chmod - change permissions of a file 
Read is equivalent to ‘4’.
Write is equivalent to ‘2’.
Execute is equivalent to ‘1’
we just add up the number for chmod 777
Owner, Group, Others
KILLING PROGRAMS AND LOGGING OUT 
Ctrl+C - kill a running command 
killall - kill processes by name 
exit - log out of bash 

USEFUL SHORTCUTS 
Ctrl+D - signal bash that there is no more input 
Ctrl+L - redraw the screen 

RESOURCE ALLOCATION
sudo blkid - Lists all the drives on a system and their IDs.
du - list disk usage of the directories
df - disk space usage

TROUBLESHOOTING
sudo reboot - restarts the system, good after an install
htop
top
sudo shutdown -h now - Tells it to shutdown now and to halt the system. Time in is in minutes or now. This will still run even if you stop the terminal from running.
Undo by running sudo shutdown -c

KNOW LINUX SYSTEM BUILDING BLOCKS
How Systems boot/load in Linux
? BIOS → BOOT LOADER → BOOT → STARTS LINUX KERNEL & ROOT 
Shell and How It Interacts with Underlying OS
https://oskarth.com/unix01/
The shell is the command interpretor in an operating system such as Unix or GNU/Linux, it is a program that executes other programs. It provides a computer user an interface to the Unix/GNU Linux system so that the user can run different commands or utilities/tools with some input data.
In computing, a shell is a user interface for access to an operating system's services. In general, operating system shells use either a command-line interface (CLI) or graphical user interface (GUI), depending on a computer's role and particular operation. It is named a shell because it is the outermost layer around the operating system.
An operating system (OS) is system software that manages computer hardware, software resources, and provides common services for computer programs. 
Shells are actually special applications that use the kernel API in just the same way as it is used by other application programs. A shell manages the user–system interaction by prompting users for input, interpreting their input, and then handling an output from the underlying operating system (much like a read–eval–print loop, REPL).[3] Since the operating system shell is actually an application, it may easily be replaced with another similar application, for most operating systems. 
A command-line interface (CLI) is an operating system shell that uses alphanumeric characters typed on a keyboard to provide instructions and data to the operating system, interactively. For example, a teletypewriter can send codes representing keystrokes to a command interpreter program running on the computer; the command interpreter parses the sequence of keystrokes and responds with an error message if it cannot recognize the sequence of characters, or it may carry out some other program action such as loading an application program, listing files, logging in a user and many others. 
UNIX File System and Storage
Unix file system is a logical method of organizing and storing large amounts of information in a way that makes it easy to manage. ... These directories are organized into a tree-like structure called the file system. Files in Unix System are organized into multi-level hierarchy structure known as a directory tree.
https://en.wikipedia.org/wiki/Unix_filesystem
Process Management and State
https://www.2000trainers.com/linux/linux-process-manage/
Linux Virtual Memory Model
Linux supports virtual memory, that is, using a disk as an extension of RAM so that the effective size of usable memory grows correspondingly. ... The part of the hard disk that is used as virtual memory is called the swap space. Linux can use either a normal file in the filesystem or a separate partition for swap space.
What is Virtual Memory?
Virtual Memory is an address mapping ●Maps virtual address space to physical address space–Maps virtual addresses to physical RAM–Maps virtual addresses to hardware devices●PCI devices●GPU RAM●On-SoC IP blocks
Techniques for Resource Control
The kernel can't determine what CPU processes are important without your help.
Most processes are started at the same priority level and the Linux kernel schedules time for each task evenly on the processor. Have a CPU intensive process that can be run at a lower priority? Then you need to tell the scheduler about it!
There are at least three ways in which you can control how much CPU time a process gets:
Use the nice command to manually lower the task's priority.
Use the cpulimit command to repeatedly pause the process so that it doesn't exceed a certain limit.
Use Linux's built-in control groups, a mechanism which tells the scheduler to limit the amount of resources available to the process.

Common System Troubleshooting Tools and Techniques

Extras
How does Docker for desktop work?
Hyperplane sets up the required compute resources etc for each VM or container and is a barrier between the host and container/VMs. Its like a series of membranes that separate organelles within the same cell.
How can root user in a container ‘escape’ to underlying host system?
User namespace (not k8s namespace, but linux namespace) is not differentiated between host and container.
So If you create a root user in the container the host machine’s root user is the same b/c they are in the same namespace even though they are separated by container:host. This means a root user in a container can escape and execute in the host system as a root user.
