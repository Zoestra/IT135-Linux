Zoestra Hammer
IT135 SU25


1) vi/vim supports two modes, insertion and command.  What do we move from insertion to command mode?
	- escape

2) How do we move from command to insertion mode?
	- `i` to insert before cursor
	- `a` to insert after cursor (append)
	- `o` to start a new line and insert
	- `cc` to change the entire line, deleting it and inserting
	- `ciw` to change inside word
	- `c$` change till end of line
	- `c` and any motion, basically
	- big fan of `c`


3) What is the exact syntax to save what we've typed in vim to a new file named my_file.txt?
	-  `:w my_file.txt`

4) In nano, what are the shortcut keys used to move to the beginning and the end of the current line?
	- `CTRL + a`  moves to beginning
	- `CTRL + e`  moves to end

5) What are the shortcut keys to cut and paste lines of text?
	- `CTRL + k`  to cut
	- `CTRL + u`  to paste

6) How does the author use CTRL + w?
	- it searches for words in the document

7) What commands does the author use to move up and down the screen?
	- `CTRL + v`  to move down
	- `CTRL + y`  to move up

8) When creating a tar file, the author mentions potentially using -v for verbose.  What does he say you may wish to do with the data thus produced?
	- you could output that to a text file to make a list of everything in the tar

9) Why does the author recommend creating a temporary directory in which to extract the contents of a compressed file?
	-  in case there is a big file system inside the tar

10) While there are multiple formats for creating compressed files, why would we use the .zip format, when it is likely not the most efficient method of compression?
	-  its usable on every platform

11) Write an example of a redirecting an error message to a file.  For example, write the contents of a ls command on a non-existent directory or file.
	-  `ls notreal 2> file.txt`

12) Write an example of appending (not overwriting) data to the end of an existing file.
	- `echo "append this text" >> some_file.txt`

13) If asked in an interview, what is the purpose of the $PATH, what would you say?
	- $PATH is a list of all the locations that programs are located. its how programs find each other without giving explicit paths

14) Why would we alter the $PATH in our shell startup file (.bash_profile, .bashrc)?
	- if you have a program installed in an unusual location (ie because its something you're still writing), you can add that location to the $PATH so that you can run it without an explicit path

15) View the command that generates a report created by the author in this video, and alter it to add a second column, including the date and avoid the -u option, thus creating a report with every unauthorized login attempt including the date and the username, and again, output this to a file, as does the author.
- ` cat auth.log  | grep "input_userauth_request" | awk '{print $1 " " $2 " " $3 "\t" $9  }' > users.txt
`
	
15) What command does the author use to extract only the Linux kernel information?
	- `uname -r`

16) What command does the author using to show how much space files and directories take up on the current system?
	- `df -h`

17) What are the two commands we need to run to update apt and then all of the existing managed packages?
	- `apt-get update`
	- `apt-get upgrade`
	- or on arch, `pacman -Syu`