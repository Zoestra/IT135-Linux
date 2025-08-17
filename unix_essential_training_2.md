Zoestra Hammer
IT135 SU25


1) What shortcut command can I type to take me to my home directory?
	- `cd ~` 
	
2) What command would I use to view the hidden files in a directory?
	- `ls -a`
	
3) When using the chown command, what’s the purpose of the switch -R?
	- applies the change of ownership recursively to all sub-directories
	
4) [Critical Thinking] What’s the 9 character permission string for a file which is read/write/execute for all users?
	- `-rwxrwxrwx`
	
5) What’s the command to create a permission set on a file named myfile.txt where the owner has full permission, and all others get only read permission?
	- `chown 744`

6)  [Critical Thinking] Why would a hacker want root access to a web server?
	- then they can run commands on the server, which can give them access to sensitive data or functions

7) What command would you type to see which users have permission to run the sudo command?
	- `sudo cat /etc/sudoers`

8) What does the following command do: `sudo !!`
	- repeat the last command but prefix with sudo

9) In Unix/Linux what is the $PATH and why is it important?
	- $PATH is the master list of programs installed on the system. this is how programs find each other and check for their dependencies

10) If we change the Path via the command line as done in this video, how long does the changed Path last?
	- it only lasts for the current session. when you close the terminal, it reverts to normal

11) What command can we use to display the available disk space on the system?
	- `df`

12) What information does the top command give us?
	- shows a list of all running processes, sorted  by resource usage
	
13) What is the universal way to force quit a running process?
	- `CTRL + c`
	
14) What command can stop PID 520 from running in the background?
	- `kill -9 520`

15) The author claims the history file is for one purpose and the history command is for another.  What are these purposes?
	- the  file is usually used by the system, while the command is usually used by the user


16) What happens when you use the exclamation point key and then the cat command?, for example: `!cat`
	- reruns the last time the cat command was ran

