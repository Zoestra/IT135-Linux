# Text processing lab
## Commands used in lab

1. `curl` *Client for URLs*
	- `curl -LO https://newmanix.com/classes/it135/files/text_files.zip`
	- downloads a file from a url
	- `-L`
		- `--location`
		- redoes request if server responds with "page has moved"
	- `-O`
		- `--remote-name`
		- names output file after the remote file
2. `unzip`
	- unzips file
	- works without destination
3. `grep` *global regular expression search and print*
	- searches files for given phrase
	- `grep -i "warn" system.log`
		- `-i` - interactive prompt
4. `sed` *stream editor*
	- find and replace words
	- matches with regular expressions
	- `sed -i.bak 's/[Ff][Aa][Ii][Ll]/FAILURE/g' app_output.log`
		- `-i`
			- output gets written to file, rather than just displayed in console
			- overwrites original data
		- `-i.bak`
			- output is written to a .bak file
		- `'s/[Ff][Aa][Ii][Ll]/FAILURE/g'` 
			- the sed "script"
			- `s/` - substitution
			- `/g` - global (applies to each occurrence)
			- `[Ff][Aa][Ii][Ll]` 
				- matches all cases of string `"fail"`
			- `/FAILURE`
				- what the matches will be replaced with
5. `awk` 
	- basically a database querying command
	- splits tables by designated seperator
	- returns specified columns, rows

## Wrap up questions
1. Which tool felt easiest to understand? Why
	- `grep`. i've use it before, and it has the simplest purpose. 
2. What surprised you about how awk or sed works?
	- `awk` seems like it does way more than a linux cli program should. its basically a miniature SQL
3. How could you use a pipeline like these to clean log files or reports?	
	- use grep to find only the lines you need, use awk to isolate the data columns you need, use sed to filter out formatting or change names