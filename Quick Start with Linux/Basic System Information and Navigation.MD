### Basic System Information and Navigation

- **Commands**:
    - `echo` – Print text or variables to the terminal.
    - `whoami` – Display the currently logged-in user.
    - `id` – Show user identity (UID, GID, and groups).
    - `id root` – Display identity details for the root user.
    - `pwd` – Show current directory path.
    - `clear` – Clear the terminal screen.
    - `echo` – Print text or variables to the terminal.
    - `echo file.txt` – Print the contents of a file.
    - `echo $variable` – Print the value of a variable.
    - `echo "Hello, World!"` – Print a string.
    - `echo ~` – Print the home directory path.
    - Absolute Paths
    - Relative Paths
    - `cd` – Change directory.
    - `cd ~` – Go to the home directory.
    - `cd ..` – Go up one directory.
    - `cd directory/` – Change to a specific directory.
    - `ls` – List files and directories in the current directory.
    - `ls -l` – List files and directories in long format.
    - `ls -a` – List all files, including hidden files.
    - `ls -la` – List all files in long format, including hidden files.
    - `ls -lh` – List files and directories with human-readable sizes.
    - `ls -l file.txt` – List details of a specific file.
    - `ls -ld directory/` – List details of a directory.


---

### 1. **echo**

- **Full-Form**: Not an acronym; "echo" is simply a command that repeats (or "echoes") text.
- **Purpose**: Prints text or variables to the terminal.
- **Syntax**:
    
    ```bash
    echo [text or $VARIABLE]
    ```
    
- **Examples**:
    
    ```bash
    echo Hello, World!       # Prints: Hello, World!
    echo $HOME               # Prints the path of the home directory
    ```
    

---

### 2. **whoami**

- **Full-Form**: "Who Am I"
- **Purpose**: Displays the username of the currently logged-in user.
- **Syntax**:
    
    ```bash
    whoami
    ```
    
- **Examples**:
    
    ```bash
    whoami                   # Output might be: "user" (shows the current user)
    ```
    

---

### 3. **id**

- **Full Form**: Not an acronym; "id" refers to identifying user information.
- **Purpose**: Shows detailed user identity information, including UID (User ID), GID (Group ID), and the groups to which the user belongs.
- **Syntax**:
    
    ```bash
    id [username]
    ```
    
- **Examples**:
    
    ```bash
    id                       # Shows UID, GID, and groups for the current user
    id root                  # Shows UID, GID, and groups for the root user
    ```
    

---

### 4. **id root**

- **Purpose**: Displays identity details specifically for the root user, providing the root's UID, GID, and group information.
- **Syntax**:
    
    ```bash
    id root
    ```
    
- **Example**:
    
    ```bash
    id root                  # Output includes root's UID (usually 0), GID, and groups
    ```
    

---

### 5. **pwd**

- **Full-Form**: "Print Working Directory"
- **Purpose**: Displays the absolute path of the current directory.
- **Syntax**:
    
    ```bash
    pwd
    ```
    
- **Example**:
    
    ```bash
    pwd                      # Output might be: "/home/user/directory"
    ```
    

---

### 6. **clear**

- **Full Form**: Not an acronym; "clear" clears the terminal screen.
- **Purpose**: Clears all text and resets the terminal view to a blank screen.
- **Syntax**:
    
    ```bash
    clear
    ```
    
- **Example**:
    
    ```bash
    clear                    # Clears the terminal screen
    ```
    

---

### 7. **cd**
- **Full-Form**: "Change Directory"
- **Purpose**: Changes the current working directory.
- **Syntax**:
    ```bash
    cd [directory]
    ```
    Examples**:
    ```bash
    cd /home/user/directory  # Changes to the specified directory
    cd ~                      # Changes to the home directory
    cd ..                      # Changes to the parent directory
    ```

---

# **Paths and Basic Directory Commands**

- **Commands**:
    - `absolute path` – Full path from the root (e.g., `/home/user/docs`).
    - `relative path` – Path from the current directory (e.g., `docs`).
    - `echo ~` – Show the home directory path.
- **Tasks**:
    - Understand the difference between absolute and relative paths by practicing `cd` with both types.
    - Print the path of the home directory using `echo ~`.

---

---

### 1. **absolute path**

- **Definition**: An absolute path is the full path to a file or directory starting from the root directory (`/`).
- **Purpose**: Provides a complete and specific location in the filesystem, ensuring the path remains the same regardless of the current directory.
- **Syntax**:
    
    ```bash
    /path/to/directory_or_file
    ```
    
- **Examples**:
    
    ```bash
    /home/user/docs      # Absolute path to the "docs" folder in "user's" home directory
    /var/log/syslog      # Absolute path to the "syslog" file in the "log" directory
    ```
    
- **Use Case**: Used when you want to specify an exact location from the root directory, making it accessible from anywhere.

---

### 2. **relative path**

- **Definition**: A relative path is the path to a file or directory relative to the current directory.
- **Purpose**: Provides a shorter, context-based path, useful when navigating within nearby folders or files from the current location.
- **Syntax**:
    
    ```bash
    path/to/directory_or_file
    ```
    
- **Examples**:
    
    ```bash
    docs                  # Relative path to the "docs" folder in the current directory
    ../images             # Relative path to the "images" folder in the parent directory
    ```
    
- **Use Case**: Useful for navigating within the filesystem without specifying the full path, often in scripts and smaller projects where directory structure is known.

---

### 3. **echo ~**

- **Purpose**: Displays the home directory path for the current user.
- **Syntax**:
    
    ```bash
    echo ~
    ```
    
- **Example**:
    
    ```bash
    echo ~      # Might output: /home/user (the home directory path of the current user)
    ```
    
- **Explanation**: The `~` (tilde) symbol represents the home directory of the logged-in user, so `echo ~` prints the path to that directory.
