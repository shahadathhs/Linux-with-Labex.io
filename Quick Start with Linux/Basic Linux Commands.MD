### Basic Linux Commands

- **Commands**:

  - System Information Commands
    - `whoami` – Display the currently logged-in user.
    - `id` – Show user identity (UID, GID, and groups).
    - `id root` – Display identity details for the root user.
    - `pwd` – Show current directory path.
  - `clear` – Clear the terminal screen.
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
  - Creating and Modifying Files

    - `touch fileName.extension` – Create an empty file.
    - `echo "Hello, World!" > fileName.extension` – Write text to a file. If file exist, replace existing content. If the file doesn't exist, it will be created first, then the content will be written.

    - `cat fileName.extension` – Display the contents of a file.
    - `cat fileName.extension > new_fileName.extension` – Copy the contents of one file to another.

  - Managing Directories

    - `mkdir directoryName` – Create a new directory.
    - `mkdir -p directory1/directory2` – Create nested directories.
    - `mkdir -v directoryName` – Verbose mode for creating directories.
      `mkdir -m 755 directoryName` – Create a directory with specific permissions.
    - `rmdir directoryName` – Remove an empty directory.
    - `rm -r directoryName` – Remove a directory and its contents recursively.

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

---
