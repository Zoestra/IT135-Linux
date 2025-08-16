1. When UNIX was re-written in the C language, what was the advantage?
	- Greater portability between chipsets
2. What option does the author recommend for Windows users who wish to learn Unix/Linux?
	- Windows Subsystem for Linux (weasel)
3. How do we move through (and rerun) previously typed commands?
	-  up arrow cycles through old command
	- if `set -o vi` is enabled, press escape to enter normal mode, and then `j` will scroll up
4. The tab key is hugely useful when we work with Unix/Linux. What does it do?
	- attempts to autocomplete the partial command. behavior depends on which shell you're running
5. What command lets us know which version of Unix/Linux we're running?
	- 
6. [True or False] The order we place the options in doesn't matter.
	- True
7. What does the author type to determine the current shell?
	-  `echo $SHELL`
8. What key combination does the author use to exit Nano?
	- `<ctrl> x`
9. [Critical Thinking] What does nano do if we run the command followed by a file that does not yet exist? For example using the command: `nano test.txt`
	- it opens a buffer which we can edit, but if we dont save the file, we lose it. you're editing the file before it exists.
10. What command does the author use to show the current directory?
	- ls
11. What is the purpose of what the author calls the dot files?
12. What command does the author use to get to the parent directory?
13. Why does the author recommend using only lower case letters when naming files in Unix?
14. Why does the author recommend using underscore instead of a space when naming files?
15. What command allows us to view the contents of a file and scroll both down and up in a large document?
16. When creating directories one within the other, what switch does the author add to the mkdir command?
17. When using the mv command to move files, what is the purpose of the switch -i?
18. When copying a directory, what switch do we add so the entire contents of all sub-directories are copied as well?
19. What does rm -R do when the target is a directory?
20. How is a symlink different than a shortcut or alias?
