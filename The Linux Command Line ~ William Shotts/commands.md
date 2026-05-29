# Linux Commands

## System Information
|Command|What it does|
|-------|-----------|
|`date`|Displays the current date and time|
|`cal`|By default displays a calendar of the current month|
|`df`|To see the amount of  currently free space on our *disk drives*|
|`free`|To see the amount of free memory|
---

## Shell and Environment
|Command|What it does|
|-------|------------|
|`exit`|To end a terminal session by closing the *terminal emulator window*|
---

## Navigation
| Command | What it does | Common Options |
|---------|-------------|----------------|
| `pwd` | Prints current directory path | — |
| `ls` | Lists directory contents | See below |
| `cd` | Changes directory | See below |

### ls options
| Option | What it does |
|--------|-------------|
| `-a` | Shows hidden files (starting with `.`) |
| `-l` | Long format — shows permissions, size, date |
| `-h` | Human-readable sizes (use with `-l`) |
| `-r` | Reverses sort order |
| `-S` | Sorts by file size |
| `-t` | Sorts by last modified time |

### ls combinations worth knowing
| Command | What it does |
|---------|-------------|
| `ls -la` | Long format + hidden files |
| `ls -lh` | Long format + readable sizes |
| `ls -lt` | Long format + sorted by time |

### cd shortcuts
| Command | What it does |
|---------|-------------|
| `cd` | Goes to home directory |
| `cd -` | Goes to previous directory |
| `cd ~username` | Goes to that user's home directory |
---
                 
## File Inspection 
|Command|What it does|Notes|
|-------|------------|-|
|`file`|Displays file type and brief description|-|
|`less`|Displays interactive display of content of file|Displays one screenful at a time|

### less commands worth knowing
|Command|What it does|
|-------|------------|
|`G`|Moves to end of text file|
|`/`|To search for keywords|
|`q`|To exit `less`|
---

### Terminal Management
|Command|What it does|
|-------|------------|
|`reset`|Restores terminal to sane state when its garbled|
---

### File Manipulation
|Command|What it does|Notes|
|-------|------------|----|
|`mkdir`|Creates new directories|`mkdir dir1 dir2 dir3` would make three seperate directories|
|`cp`|Copies files or directories|
|`mv`|Moves or renmes files|`mv file1 file2` moves content of file1 to file2 if file2 exists, and renames file1 to file2 if file2 doesnt exist|

Common `cp` options:
|Options|Meaning|
|-------|-------|
|`-i` or `--interactive`|Promtps user for confirmation before overwriting existing files|
|`-u` or `--update`|While copying files from directories, Shell copies *non-existant* or *updated* files only to the new directory|
|`-v` or `--verbose`|Displays vital information while copying|
|`-r` or `--recursive`|Gives permission to go through deep into complex directories having files and sub-directories to copy everything into a new directory|


`cp file1 file2` copies content of file1 into file2 (destroys content of file2 (if exists)). If file2 doesnt exist, then Shell creates a new file 'file2' with file1's content.
`cp file1 file2 dir1` copies content of file1 and file2 into directory dir1.

`mkdir dir...` `cp item... directory` and in other commands followed by `...` means that these commands can be repeated for different files sepearated by a space.