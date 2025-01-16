### Basic Linux Commands

- **Commands**:

  - System Information Commands

    - `whoami` – Display the currently logged-in user.
    - `id` – Show user identity (UID, GID, and groups).
    - `id root` – Display identity details for the root user.
    - `pwd` – Show current directory path.
    - `clear` – Clear the terminal screen.
    - `hostname` – Display the hostname.
    - `uname` – Display system information.
      - `uname -a` – Show system information in a long format.
      - `uname -r` – Display the kernel release.
      - `uname -m` – Show the machine hardware name.
      - `uname -s` – Print the kernel name.
      - `uname -v` – Show kernel version.
      - `uname -o` – Print the operating system name.
      - `uname -p` – Show the processor type.
      - `uname -i` – Print the hardware platform.
    - `tree` – Display the directory structure in a tree-like format.
      - `tree -d` – Display directory structure without files.
      - `tree -f` – Display file names.
      - `tree -L 2` – Display directory structure up to two levels deep.
      - `tree -h` – Display file sizes in human-readable format.
      - `tree -a` – Display hidden files.
    - `df` – Display disk space usage.
      - `df -h` – Display disk space usage in human-readable format.
      - `df -h /home` – Display disk space usage for a specific directory.
      - `df -h /dev/sda1` – Display disk space usage for a specific partition.
      - `df -h /dev/sda1 /dev/sda2` – Display disk space usage for multiple partitions.

  - Printing Strings

    - `echo` – Print text or variables to the terminal.
    - `echo file.txt` – Print the contents of a file.
    - `echo $variable` – Print the value of a variable.
    - `echo "Hello, World!"` – Print a string.
    - `echo ~` or `echo $HOME` – Print the home directory path.
    - `echo "Hello, $NAME!"` – Print a string with a variable.

  - Directory & Path Basics

    - `absolute path` – Full path from the root (e.g., `/home/user/docs`).
    - `relative path` – Path from the current directory (e.g., `docs`).
    - `~` – Home directory.
    - `..` – Parent directory.
    - `.` – Current directory.
    - `/` – Root directory.
    - `-` – Previous directory.

  - Basic File Types

    - `file.txt` – Text file.
    - `file.jpg` – Image file.
    - `file.pdf` – PDF file.
    - `file.exe` – Executable file.
    - `file.zip` – Compressed file.
    - `.file` – Hidden file.
    - `file.MD` – Markdown file.
    - `file.sh` – Shell script file.

  - Directory Navigation Commands

    - `cd` – Change directory.
    - `cd ~` – Go to the home directory.
    - `cd ..` – Go up one directory.
    - `cd directory/` – Change to a specific directory.
    - `cd -` – Go back to the previous directory.
    - `cd /` – Go to the root directory.

  - Listing Files and Directories

    - `ls` – List files and directories in the current directory.
    - `ls -l` – List files and directories in long format.
    - `ls -a` – List all files, including hidden files.
    - `ls -la` – List all files in long format, including hidden files.
    - `ls -lh` – List files and directories with human-readable sizes.
    - `ls -l file.txt` – List details of a specific file.
    - `ls -ld directory/` – List details of a directory.
    - `ls -ld /` – List details of the root directory.

  - Managing Files

    - `touch fileName.extension` – Create an empty file.
    - `touch file1.txt file2.txt` – Create multiple files.
    - `echo "Hello, World!" > fileName.extension` – Write text to a file. If file exist, replace existing content. If the file doesn't exist, it will be created first, then the content will be written.
    - `cat fileName.extension` – Display the contents of a file.
    - `cat fileName.extension > new_fileName.extension` – Copy the contents of one file to another.
    - `cat -n fileName.extension` – Display the contents of a file with line numbers.

  - Viewing Files Contents

    - `head` – Display the first 10 lines of a file.
    - `head -n n fileName.extension` – Display the first n lines of a file.
    - `head -c n fileName.extension` – Display the first n bytes of a file.
    - `tail` – Display the last 10 lines of a file.
    - `tail -n n fileName.extension` – Display the last n lines of a file.
    - `tail -c n fileName.extension` – Display the last n bytes of a file.
    - `tail -f fileName.extension` – Display the last 10 lines of a file and continue to update as the file grows.

  - Managing Directories

    - `mkdir directoryName` – Create a new directory.
    - `mkdir -p directory1/directory2` – Create nested directories.
    - `mkdir -v directoryName` – Verbose mode for creating directories.
    - `mkdir -m 755 directoryName` – Create a directory with specific permissions.
    - `rmdir directoryName` – Remove an empty directory.
    - `rm -r directoryName` – Remove a directory and its contents recursively.

  - Comparing Files & Directories

    - `diff file1 file2` – Compare two files line by line.
    - `diff -q file1 file2` – Compare two files and return exit status.
    - `diff -s file1 file2` – Compare two files and display a message.
    - `diff -r dir1 dir2` – Compare two directories recursively.
    - `diff -r -q dir1 dir2` – Compare two directories recursively and return exit status.
    - `diff -r -s dir1 dir2` – Compare two directories recursively and display a message.
    - `diff -r -q dir1 dir2 > diff_` – Compare two directories recursively and save the output to a file.

  - Copying and Moving Files and Directories

    - `cp fileName copyFileName` – Copy a file.
    - `cp fileName directory` – Copy a file to a
      directory.
    - `cp -r directory1 directory2` – Copy a directory recursively.
    - `mv fileName newFileName` – Rename a file.
    - `mv fileName dirname` – Move a file to a directory.
    - `mv dirname newDirName` – Rename a directory.
    - `mv -i fileName directory` – Move a file to a directory with an interactive prompt.

  - Deleting Files and Directories

    - `rm filename` – Remove a file.
    - `rm file1 file2` – Remove multiple files.
    - `rm -r dir` – Remove a directory and its contents, including hidden files.
    - `rm -i` – Prompt before deleting.
    - `rm -rf` – Forcefully delete a directory without prompting.
    - `rm -rf dir` – Forcefully delete a directory without prompting.
    - `rm -rf dir1 dir2` – Forcefully delete multiple directories without prompting.

  - Manual Pages

    - `man command` – Display the manual page for a command.
    - `man -k keyword` – Search the manual pages for a keyword.
    - `man -f command` – Display the manual page for a command.

  - campgen Auto-completion

    - `compgen -c` – List all available commands.
    - `compgen -a` – List all available aliases.
    - `compgen -A function` – List all available functions.
    - `compgen -A variable` – List all available variables.
    - `compgen -A user` – List all available users.
    - `compgen -A group` – List all available groups.
    - `compgen -A host` – List all available hosts.

  - Aliases

    - `alias ls='ls -l'` – Create an alias for the ls command.
    - `alias` – List all aliases.
    - `unalias ls` – Remove an alias.
    - `alias rm='rm -i'` – Create an alias for the rm command.

  - Help and Information

    - `help` – Display help information for the shell.
    - `help command` – Display help information for a specific command.
    - `help -d` – Display a list of available help topics.
    - `help -m` – Display a list of available help manuals.
    - `help -s` – Display a list of available help sections.
    - `help -w` – Display a list of available help websites.
    - `help -v` – Display a list of available help versions.

  - File Permissions

    - `chmod u=rwx fileName` – Set all permissions for the owner of a file.
    - `chmod u+x fileName` – Add execute permission to the owner of a file.
    - `chmod g+w fileName` – Add write permission to the group of a file.
    - `chmod o-r fileName` – Remove read permission from others for a file.
    - `chmod a=rwx fileName` – Set all permissions for all users.
    - `chmod 777 fileName` – Set all permissions for all users.
    - `chmod 755 fileName` – Set read, write, and execute permissions for the owner and group, and read and execute permissions for others.
    - `chmod 644 fileName` – Set read and write permissions for the owner, and read permissions for the group and others.
---
