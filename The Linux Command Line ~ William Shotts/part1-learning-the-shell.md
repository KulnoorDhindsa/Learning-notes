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
Unlike Windows which has multiple directories (or folders like C:\ , D:\), Linux has sub-directories in its *root directory*, thus has a *tree* type file system.

### Pathnames
1. **Absolute Pathnames** 
    Begins with the root directory (/) and reaches the location of the file branch by branch.
    - Assume we ran `cd /usr/bin` prior to following commands.
      `cd /usr` goes up one level to `/usr`.

2. **Relative Pathnames**
    Uses `.` for the working directory and `..` for it's parent directory.
    - Assume we ran `cd /usr/bin` prior to following commands.
      `cd ..` to go to ``'usr' or *parent directory*.

### File Names
Filenames starting with (.) full stop are *hidden*.
They are case sensitive.
Prefer underscores rather than spaces in filenames.
**Extensions don't exist in Linux**. They are still used so that at a glance, the reader can configure what file it is. The Shell determines file type differently.

### Notes
- By default, on starting a terminal emulator session, our working directory is 'home directory'.
- Most of the files in Linux systems are installed in `/usr/bin`.
  Here the root directory is the leading slash '/', a directory 'usr' is in it with a sub-directory 'bin'.
- The Shell prompt displays the name of the current working  directory.
- `./` is omitted in most areas as its implied.
- By defualt, if a pathname is not specified to something, working directory is assumed.