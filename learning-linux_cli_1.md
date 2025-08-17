Zoestra Hammer
IT135 SU25

1. The author explains the distro of Linux used in this course is Ubuntu. What distro is Ubuntu based on? Why would it be important to know what the distro
	   - Debian
	   - different distros use different foundational software. for instance, ubuntu uses `apt` as a package manager, and arch uses `pacman`

2. [Critical Thinking] The author explains using GitHub Codespaces will look a little different than what he types on his Ubuntu distro. Why use GitHub Codespaces, in our case?
	   -  effectively zero setup, completely agnostic of the host system. 

3. One of the commands the author shows in this video is named stat. Why type of information is provided by this command and how could it be useful?
	   -  Stat can show information like last access, creation date, and permissions, and shows us more than ls does. 

3. How do we determine we're looking at an absolute and not a relative path?
	   -  an absolute path will either begin with a `/` or a `~`, which refer to root and home, whereas a relative path begins with a folder
	
4. [Critical Thinking] Since an absolute path is more specific, why would we use a relative path? Please give an example of a relative path, and also the absolute path to the same folder or file.
	   - relative paths are quicker to type if we're manually entering it, and if we are writing a script, we might know where the file might be, but should know what the local structure will be
	- absolute path: `~/.config/nvim/lua/plugins/`
	- relative path : `lua/plugins/`, assuming working directory is `~/.config/nvim/`

5. [Critical Thinking] In this video, the author shows 2 different ways to deal with a space in a directory name. Why method do you prefer, and why?
	- i prefer single quotes, `'/path/with spaces'` as its much cleaner to read

7. What command does the author use to view the entire contents of the departments directory including the sub-directories?
	   - `ls -R departments/`
	   - eza has a better version of this, which i run with `ls -T` because of an alias. 

8. Write the exact syntax for a find command that retrieves any directory or file that contains the letter "d" in the current directory.
	-  `find . -name "*d*"`

9. [Critical Thinking] In this video, the author does not show us how to do a case insensitive search for a file or directory. Search the web and do a case insensitive version of the find command you created for #8 above.
	-  `find . -iname "*d*"`

10. When the author logs in to use superuser permissions (su) why do the password characters not show up on the command line?
    -  its a security measure to prevent people from figuring out your password by number of characters

11. [Critical Thinking] Allowing write access to others (the public) for example on a web server is considered insecure and dangerous as it can allow access to hackers to inject code into our servers then activate these by hitting the resource they upload in our space with a browser. Therefore, of the following sets of octal permissions, which one of them is safe from this kind of attack, as it does not allow public write permission - 757, 756, 754 or 752?
    -  754

12. What are the corrected versions of each of the 4 commands the author provides? Explain what is wrong with each of the commands provided.
	- `cd ~` or `cd`
		- `~` is an alias for home, so `~/home` is a redundant path that wont work
    - `ls /home` 
	    - ls is lowercase
    - `mv ~/log.tar.gz /home/scott`
	    - the destination path was malformed
	- `chmod 754 ~/log.tar.gz`
		- the example did not provide a setting to change the permissions to
	

13. According to the author, name a disadvantage to a tool that takes a "swiss army knife" approach?
    - swiss army tools do many things, but they dont do any of them very well. its better to have a specialized tool that only does a single thing

14. In this video, the author uses the wc command and comes back with 6 as the number of characters in the string hello. Why is this?
    - the string ends in a new line character `\n`

15. [Critical Thinking] When the author uses the cat and tail command to print out the last 5 lines of the file named poems.txt, what is the advantage of using cat -n prior to piping tail -n5?
    -   that way we get to see how many lines are in the original file

16. What is the exact syntax to find the characters "the" or "The" (case insensitive) using grep in a file named poems.txt?
    -  `grep -i 'the' poems.txt`

17. [Critical Thinking] Write the exact syntax for a simple command line awk program which prints first the id column, then the name column and last the team column for each of the lines in the file named simple_data.txt.
    - `awk '{print $2 "\t" $1 "\t" $3} simple_data.txt`

18. [Critical Thinking] Write the exact syntax of a sed command that changes every instance of the word "Purple" to the words "Vikings" in a file named simple_data.txt and redirects the output to a file named vikings.txt.
    - `sed s/Purple/Vikings simple_data.txt > vikings.txt`

19. [Critical Thinking] Write a command that numerically sorts the contents of the file named simple_data.txt numerically by the second column (id) and redirects the output to a file named sorted_data.txt
    - `sort -k2 -n simple_data.txt > sorted_data.txt`
