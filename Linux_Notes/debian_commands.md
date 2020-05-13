~ (tilde) - This is a shortcut for your home directory. eg, if your home directory is /home/ryan then you could refer to the directory Documents with the path /home/ryan/Documents or ~/Documents
. (dot) - This is a reference to your current directory. eg in the example above we referred to Documents on line 4 with a relative path. It could also be written as ./Documents (Normally this extra bit is not required but in later sections we will see where it comes in handy).
.. (dotdot)- This is a reference to the parent directory. You can use this several times in a path to keep going up the hierarchy. eg if you were in the path /home/ryan you could run the command ls ../../ and this would do a listing of the root directory.
file.exe - an executable file, or program.
man <command to look up>
synopsis. This is really just a quick overview of how the command should be run. Square brackets ( [ ] ) indicate that something is optional. (option on this line refers to the command line options listed below the description)
To exit the man pages press 'q' for quit.
man -k <search term>
File commands
cp Copy - ie. Copy a file or directory
mv Move - ie. Move a file or directory (can also be used to rename).
vi == vim
Wild Cards
* - represents zero or more characters
? - represents a single character
[] - represents a range of characters
<filename> .bash_history of any file lists the last user that modified it and when
top
Lists all the processes that are running that can fit in terminal window
ps aux - Lists all the processes that are running.
ps - Lists all the processes that are running in the terminal.
Kill a crashed process (‘firefox’ browser)
ps aux | grep 'firefox'
kill [signal] <PID>
kill 6978
kill -9 6978
This kills it more if the first kill didn’t work. Confirm via ps aux | grep 'firefox'
ls 
ls -l : lists all the files and their permissions
ls -p : list files and their type (directory/file)
pushd/popd - put working directory on a stack
file - determine file type
locate - find files by name
updatedb - update database for locate 
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
