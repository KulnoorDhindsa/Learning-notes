# Part 1 - Learning the Shell

## Chapter 1 - What is the Shell?

### The Shell
Takes your keyboard input and passes it to the OS to execute. 
On most Linux systems this is Bash.

### Terminal Emulator
A program that gives you a window to type in. The window itself 
is the terminal emulator — Bash is what runs inside it.

### Shell Prompt
Appears as: `username@machinename:current_directory$`
Dollar sign = regular user. Hash (#) = root user (superuser privileges).

### Notes
- Most Linux distros use Bash by default
- GUI desktops usually include a terminal emulator in the menu
---
## Chapter 2 - Navigation

### Filesystem Hierarchy
Linux organises its files in a singular *root directory*.
Unlike Windows which has multiple directories (or folders like C:\, D:\), 
Linux has sub-directories in its *root directory*, thus has a *tree* type filesystem.

This structure is standardised by the **Filesystem Hierarchy Standard (FHS)**.

| Directory | Purpose |
|---|---|
| `/` | Root — top of the entire hierarchy |
| `/bin` | Essential user binaries (`ls`, `cp`, `cat`) |
| `/sbin` | System/admin binaries (`fsck`, `reboot`) |
| `/etc` | Configuration files |
| `/home` | User home directories |
| `/root` | Root user's home directory |
| `/var` | Variable data — logs, spools, caches |
| `/tmp` | Temporary files (cleared on reboot) |
| `/usr` | Secondary hierarchy — user programs, libraries, docs |
| `/usr/bin` | Non-essential user binaries |
| `/usr/sbin` | Non-essential system binaries |
| `/usr/local` | Locally installed software |
| `/lib` | Essential shared libraries |
| `/lib64` | 64-bit libraries |
| `/dev` | Device files (`sda`, `tty`, `null`) |
| `/proc` | Virtual FS — kernel and process info |
| `/sys` | Virtual FS — hardware and kernel data |
| `/mnt` | Temporary mount points |
| `/media` | Removable media (USB, CD) |
| `/opt` | Optional/third-party software |
| `/boot` | Bootloader files, kernel |
| `/srv` | Data for services (FTP, HTTP) |
| `/run` | Runtime data since last boot |

> `/proc` and `/sys` are virtual filesystems — they don't exist on disk, the kernel generates them in memory at runtime.

### Pathnames
1. **Absolute Pathnames** 
    Begins with the root directory (/) and reaches the location of the file branch by branch.
    - Assume we ran `cd /usr/bin` prior to following commands.
      `cd /usr` navigates directly to `/usr`.

2. **Relative Pathnames**
    Uses `.` for the working directory and `..` for its parent directory.
    - Assume we ran `cd /usr/bin` prior to following commands.
      `cd ..` to go to 'usr' or *parent directory*.

### Notes
- By default, on starting a terminal emulator session, our working directory is 'home directory'.
- Most of the files in Linux systems are installed in `/usr/bin`.
  Here the root directory is the leading slash '/', a directory 'usr' is in it with a sub-directory 'bin'.
- The Shell prompt displays the name of the current working  directory.
- `./` is omitted in most areas as its implied.
- By default, if a pathname is not specified to something, working directory is assumed.
---
## Chapter 3 - Exploring The System

### File Names
Filenames starting with (.) full stop are *hidden*.
They are case sensitive.
Prefer underscores rather than spaces in filenames.
Extensions are not required by Linux. The shell determines file type via magic bytes, not the extension.

### ASCII Text
Simple method of representation of information on computer.
Contains characters and basic control codes like *carriage return* and *line feed*.

### Less Is More
`less` is a part of **pager** programes, i.e. programes allowing easy viewing of files by showing page-by-page view of long files.
Unlike `more`, `less` pages backward and forward, along with extra commands like `/` and `q` that make viewing long files easier.

### Everything is a file
Core Unix philosophy is that devices, processes, sockets, directories - all are treated as files.

### Links (Briefly)
  1. A symlink lets you give a file a stable nickname, so the underlyinh real file can change without breaking anything that dipends on that nickname.
  2. A hard link is sa pointer *directly to data on the disk* rather than a filename.
---
## Chapter 4 - Manipulating Files and Directories

### Wildcards/Globbing
Special characters that help specify groups of filenames based on patterns of characters.
Common **Character Classes** include:
|Character Class|Meaning|
|---------------|-------|
|[:alnum:]|Matches alphanumeric characters|
|[:alpha:]|Matches alphabetic characters|
|[:digit:]|Matches numerals|
|[:lower:]|Matches lowercase letters|
|[:upper:]|Matches uppercase letters|


Commonly used wildcards:
|Wildcard|Matches|
|`*`|All files|
|`k*`|Files beginning with *k*|
|`k*.txt`|Files starting with 'k' and ending with *.txt*|
|`Hello??`|FIles beginning with 'Hello' followed by two characters|
|`[abc]*`|Files begining with a, b or c followed by whatever|
|`Track.[0-9][0-9]`|Files starting with *Track* followed by 2 numerals from 0-9|
|`[[:lower:]]*`|FIles beginning with a lowercase letter|
|`[![:digit:]]*`|Files **NOT** beginning with a digit|
|`*[[:lower:]123]|Files ending with a lowercase letter or the numerals 1,2 or 3.|

- `*-` anything before
- `[...]` match exactly one characters that must be any of the things inside the bracket.

### No Undelete command in Linux
In Unix-like OS like Linux, there is no undelete command for `rm`.
`rm *.html` deletes all HTML files frmo a directory.
`rm * .html` deleted everything first, then tries to delete the HTML files but since everything is delelted already, it shows error.

