Zoestra Hammer
IT135 SU25

1) What is the exact syntax to send the content from file1.txt and append it to file2.txt?
	- `cat file1.txt >> file2.txt`  
	
2) What is the exact syntax to direct an alphabetized list of movies from a file named movies.text to a file named sorted_movies.txt?
	- `sort < movies.text > sorted_movies.txt `

3) What is the exact syntax to pipe a list of movies in a file named  movies.txt to the command line and remove all duplicate movies?
	- `cat movies.txt | uniq`

4) The author show us how to suppress output from a command using > dev/null.  In what situations would we want to use this?
	- if we are writing a bash script and need to use a command that normally has a large output, but we dont want to see the output, suppressing the  output can be useful. 
	
5) As a beginner, in what file does the author recommend placing our configurations?
	-`~/.bash_profile

6) What is the syntax to run our bash configuration file at this time (right away) by using the command line?
	-  `source <path to config>`

7) The author creates an alias "ll".  What does this command do for us, if we create it?
	- it runs `ls -lah`

8) [Critical Thinking] The author creates aliases for existing commands, and in doing so alters or replaces some of the built in functionality.  While doing so, he creates an alias for mkdir as mkdir -p.  Why would this be useful?
	- the -p option is very convenient, and basically has no drawbacks to using it all the time, so setting as the default is useful

9) When setting an environment variable, what is the purpose of export?
	- exporting the variable makes it available to any sub-processes created by the shell

10) What is the exact syntax used to add the /usr/local/mysql/bin directory to the path in your configuration file?
	- `export PATH='$PATH:/usr/local/mysql/bin'`

11) Why does the author recommend putting a space at the end of the prompt when we create a custom prompt in our configuration file?
	-  if you dont include a space, your command will begin immediately after the prompt and look terrible.

12) What is the exact syntax to add the username, current shell and current working directory to a custom prompt in our configuration file?
	- `PS1=\u \s \w `