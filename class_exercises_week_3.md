1. Create a directory named testdir  
	- `mkdir testdir`
2. Move to the new directory, create a file named testfile.txt  
	- `cd testdir`
	- `touch testfile.txt`
3. Create and write a short message into a new file.  
	- `echo "hello world" > testfile.txt`
4. Open and edit the file in a terminal-based text editor.  
	- `vi testfile.txt`
5. Create a copy of an existing file.  
	- `cp testfile.txt testfilecopy.txt`
6. Delete a file from the system.  
	- `rm testfilecopy.txt`
7. Save your command history to a file.  
	- `history > history.txt`
8. View the contents of your saved history file.  
	- `cat history.txt`
9. Run a JavaScript file using the system’s built-in JavaScript engine.  
	- `qjs hello.js`
10. Compile and run a C program from source code.
	- in codespace
		- `gcc hello.c -o hello`
	- in normal use
		- `make`
11. make nested directories
	- `mkdir -p a/b/c`
12. remove nested directories
	- `rm -r a/`
	- or for interactive prompt
		- `rm -ri a/b/c`
		