# Text Processing Lab pt2

1. extracting just timestamps from file
- `cut -d' ' -f1,2 system.log`
	- `-d' '` - delimiter, which character separates the columns
		- in this case, delimiter is `' '` (space)
	- `-f1,2`
		- `-f` - field, which column to extract
		- `1,2` - columns 1 and 2
	- `system.log`
		- target file
2. List Unique Log Levels
- `cut -d' ' -f3 system.log | sort | uniq -c`
	- `cut -d' ' -f3 system.log` see above
	- `| sort` pipe output into sort program
	- `| uniq -c` pipe into uniq
		- `-c` prefixes each line with number of times it appeared
3. Count the number of ERROR messages
 -  `grep ERROR system.log | wc -l`
	 - ` grep ERROR system.logs` 
		 - search for `ERROR` in file `system.logs`
	 - `| wc -l `
		 - pipe into wc
		 - `wc` - word count
			 - prints number of lines, words, bytes
		 - `-l` `--lines`
			 - prints newline count
    ➤ What would happen if you used "-i" with grep?
	 - `-i` ignores case, so it would also find `error`
4. Save a cleaned file using `tee`
- `sed -E 's/fail(ed)?/FAILURE/Ig' app_output.log | tee cleaned_app_output.log`
	-  `sed -E 's/fail(ed)?/FAILURE/Ig' app_output.log` 
		- cleans `app_output.log` with `sed`
		- replaces `fail` or `failed` with `FAILURE`
	- `| tee cleaned_app_output.log` 
		- pipes the output of sed into `tee`
		- `tee` saves the input into `cleaned_app_output.log`, and prints to console
5.   Extract and Count Backup Start Times
-  `grep "Starting backup job" system.log | cut -d' ' -f2`
	- finds backup jobs, shows pertinent fields
	- all this has been explained above
  ➤ Bonus: Count how many times it happened:
	- `grep "Starting backup job" system.log | wc -l`

## Reflection / Discussion Questions
1. What’s the difference between "sort | uniq" and just "uniq"?
	- `uniq` will return in order of appearance
	- `sort | uniq` will return in sorted order
2. What are some advantages of combining tools like cut, sort, and uniq?
	- allows you to create a complex pipeline of commands to find just what you need, or extract information from logs
3. How might this be useful in IT support, QA, or DevOps?
	- combing through logs can be very important in diagnosing and debugging issues. logs can reveal exactly where the problems arise.
# from codeshare
08/14/2025: 

  

1. Startup files on load of Codespace: Inside a GitHub repo that uses Codespaces, there are configuration files that define and customize the development environment for a project.  Previously we had the issue that we created a [shell startup file](https://docs.google.com/document/d/1kVLhj1EqpPT47XusAfTvebP4KZq3IlFWMtnB5lDg194/edit?tab=t.0) file (.bashrc) that was not loading when we loaded our Codespace.  We're going to fix that here.  NOTE: We'll be making these changes directly in the repo  
    The devcontainer.json file is a configuration file that allows us to automatically install extensions, set up environment variables, run commands when the Codespace is created, and configure tasks that happen every time a terminal is opened. It ensures that all tools, aliases, and functions are ready to use.
Here's the new version of the .devcontainer/devcontainer.json file:
```
{

  "extensions": [

    "GitHub.github-vscode-theme"

  ],

   "postAttachCommand": "cp -f .bashrc ~/.bashrc && . ~/.bashrc && git pull --all"

}
```


The line highlighted line above performs three key actions whenever we attach to a Codespace:

`cp -f .bashrc ~/.bashrc` – Copies the .bashrc file from the repo into the home directory (~), overwriting any previous version. This ensures that we always have the latest startup file loaded.

`. ~/.bashrc` – Sources the .bashrc file so that all aliases, functions, and environment settings are immediately available in the current terminal session.

`git pull --all` – Updates the repository to ensure any new files or changes are applied to the Codespace.

Together, this command guarantees a fresh, consistent environment on every session and keeps our repo aligned.

Confirmation of the successful load of .bashrc: We can also add an echo statement to get visual confirmation of the successful load of our .bashrc file.  In order to do so, add the following to your .bashrc file:

echo "✅ .bashrc successfully loaded!"

In this way we can see the .bashrc was successfully loaded!

B) After making sure our .bashrc file is loaded successfully, we started working on an [Intro to Scripting](https://docs.google.com/document/d/1R5HTObBAVyroSFpT_6ulwrodI36K_2moqL-JKI4cIr4/edit?tab=t.0)