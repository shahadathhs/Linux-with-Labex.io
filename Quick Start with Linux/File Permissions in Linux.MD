# **Comprehensive Guide to File Permissions in Linux**

## **Table of Contents**

1. **Understanding File Permissions**
    - Permission Types (`r`, `w`, `x`)
    - Permission Categories (`user`, `group`, `others`)
    - File Types (`-`, `d`, `l`, etc.)
2. **Viewing File Permissions**
    - `ls -l`
    - `ls -ld`
    - `ls -lR`
3. **Changing Ownership**
    - `chown`
    - `sudo chown`
    - `chgrp`
4. **Changing Permissions**
    - `chmod` (Symbolic Mode)
    - `chmod` (Numeric Mode)
    - Special Permissions (Sticky Bit, SUID, SGID)
5. **Numeric Mode Explained**
    - Understanding Permission Numbers
    - Examples and Common Permission Sets
6. **Practical Tasks**
    - Default Permissions (`umask`)
    - Managing Script Files and Permissions
7. **Advanced Topics**
    - ACL (Access Control Lists)
    - Standard File Permissions
    - ACLs vs Standard Permissions
    - Recursive Changes
    - Finding Files by Permissions
    - Symbolic Links and Permissions
    - Immutable Files
    - Masking Permissions with `umask`
    - Octal vs. Symbolic Representation Comparison
    - Hidden Permissions (CAP_* Capabilities)
    - Effective Permissions and the `stat` Command
8. **Security Best Practices**

---

## **1. Understanding File Permissions**

### **1.1 Permission Types**

- **`r` (Read)**: Allows reading the file or listing directory contents.
- **`w` (Write)**: Allows modifying the file or creating/deleting files in a directory.
- **`x` (Execute)**: Allows executing a file or entering a directory.

---

### **1.2 Permission Categories**

- **User (`u`)**: The owner of the file.
- **Group (`g`)**: The group associated with the file.
- **Others (`o`)**: Everyone else.

---

### **1.3 File Types**

- **`-`**: Regular file.
- **`d`**: Directory.
- **`l`**: Symbolic link.
- **`c`**: Character device.
- **`b`**: Block device.

Example of `ls -l` output:

```bash
-rw-r--r--  1 user group 1024 Nov 14 12:00 example.txt
```

- `rw-r--r--`: File type and permissions.
- `user`: Owner.
- `group`: Group.

---

## **2. Viewing File Permissions**

### **2.1 `ls -l`**

Displays detailed file information.

```bash
ls -l filename
```

---

### **2.2 `ls -ld`**

Displays directory information without listing its contents.

```bash
ls -ld dirname
```

---

### **2.3 `ls -lR`**

Recursively lists detailed file information for all subdirectories.

```bash
ls -lR dirname
```

---

## **3. Changing Ownership**

### **3.1 `chown`**

Change ownership of a file or directory.

```bash
chown user:group filename
```

---

### **3.2 `sudo chown`**

Execute `chown` with admin privileges.

```bash
sudo chown root:root filename
```

---

### **3.3 `chgrp`**

Change the group ownership of a file.

```bash
chgrp groupname filename
```

---

## **4. Changing Permissions**

### **4.1 `chmod` (Symbolic Mode)**

Change permissions using symbols.

```bash
chmod u+x filename  # Add execute permission for the user.
chmod g-w filename  # Remove write permission for the group.
chmod o+r filename  # Add read permission for others.
```

---

### **4.2 `chmod` (Numeric Mode)**

Set permissions using numbers.

- **`4`**: Read.
- **`2`**: Write.
- **`1`**: Execute.

Examples:

```bash
chmod 755 filename  # User: rwx, Group: r-x, Others: r-x
chmod 644 filename  # User: rw-, Group: r--, Others: r--
chmod 700 filename  # User: rwx, Group: ---, Others: ---
```

---

### **4.3 Special Permissions**

#### **Sticky Bit**

Prevents users from deleting files in shared directories unless they own them.

```bash
chmod +t dirname
```

#### **SUID (Set User ID)**

Allows a program to run with the permissions of its owner.

```bash
chmod u+s filename
```

#### **SGID (Set Group ID)**

Allows files created in a directory to inherit the group ownership of the directory.

```bash
chmod g+s dirname
```

---

## **5. Numeric Mode Explained**

### **5.1 Understanding Permission Numbers**

Permission numbers are calculated by adding the values of read, write, and execute permissions:

| Permission | Value |
|-------------|-------|
| Read (`r`)  | 4     |
| Write (`w`) | 2     |
| Execute (`x`)| 1     |

Each digit in a permission number represents a category:
- **First digit**: User (Owner)
- **Second digit**: Group
- **Third digit**: Others

Examples:

| Command        | User  | Group | Others |
|----------------|-------|-------|--------|
| `chmod 755`    | rwx   | r-x   | r-x    |
| `chmod 644`    | rw-   | r--   | r--    |
| `chmod 700`    | rwx   | ---   | ---    |

Common permission sets:

- **755**: User has full access; group and others can read and execute.
- **644**: User has read and write access; group and others can read.
- **777**: Everyone has full access (use with caution).

---

## **6. Practical Tasks**

### **6.1 Default Permissions (`umask`)**

The `umask` command controls the default permissions for newly created files.

```bash
umask 022  # Default permissions: rw-r--r--
```

### **6.2 Managing Script Files and Permissions**

1. **Create a script**:

    ```bash
    touch script.sh
    ```

2. **Make it executable**:

    ```bash
    chmod u+x script.sh
    ```

3. **Run the script**:

    ```bash
    ./script.sh
    ```

---

## **7. Advanced Topics**

### **7.1 ACL (Access Control Lists)**

ACLs provide more fine-grained permissions than standard file permissions, allowing more detailed control over who can access files or directories.

- **Set ACL**:

    ```bash
    setfacl -m u:username:rwx filename
    ```

- **View ACL**:

    ```bash
    getfacl filename
    ```

---

### **7.2 Standard File Permissions**  
Standard file permissions are the basic permissions that apply to files and directories, managed using common commands:

- **`umask`**: Controls default permissions for newly created files.  
- **`chmod`**: Modifies permissions for files and directories.  
- **`chown`**: Changes the owner of a file or directory.  
- **`chgrp`**: Modifies the group ownership of a file or directory.  
- **`chattr`**: Adjusts file attributes to restrict modifications.  
- **`lsattr`**: Lists file attributes of files or directories.  
- **`setfacl`**: Configures Access Control Lists.  
- **`getfacl`**: Retrieves the ACLs for a file or directory.  

---

### **7.3 Standard File Permissions VS ACLs**  
| Feature                | Standard File Permissions | Access Control Lists (ACLs) |
|------------------------|---------------------------|----------------------------|
| Granularity            | Basic (user, group, others) | Fine-grained, specific users/groups |
| Supported Commands     | `chmod`, `chown`, `chgrp`  | `setfacl`, `getfacl`       |
| Flexibility            | Limited to three entities  | Allows multiple permissions per file |


### **7.4 Recursive Changes**

When making changes to permissions, use the `-R` flag for recursive changes.
Here recursive means that it will apply the changes to all files and subdirectories.


Use `chmod`, `chown` and `chgrp` recursively to apply changes to all files and subdirectories.

```bash
chmod -R 755 directory
chown -R user:group directory
chgrp -R group directory
```

---

### **7.5 Finding Files by Permissions**

Find files with specific permissions using `find`:

```bash
find /path -perm 755
```

---

### **7.6 Symbolic Links and Permissions**
Symbolic links are shortcuts to files or directories.

Symbolic links have their own permissions that are typically ignored; permissions on the target file are applied instead.

```bash
ln -s target linkname
ls -l linkname  # Displays link permissions
```

---

### **7.7 Immutable Files**
Immutable files cannot be modified or deleted.

Make files immutable to prevent modification or deletion.

- **Set immutable attribute**:

    ```bash
    chattr +i filename
    ```

- **View attributes**:

    ```bash
    lsattr filename
    ```

---

### **7.8 Masking Permissions with `umask`**
The `umask` command sets the default permissions for newly created files.

Modify default file creation permissions with `umask`. The final permissions are affected by subtracting the `umask` value from the system defaults.

```bash
umask 022  # Default permissions: rw-r--r--
```

---

### **7.9 Octal vs. Symbolic Representation Comparison**

Provide symbolic equivalents for common octal settings to clarify concepts:

| Octal | Symbolic |
|-------|----------|
| 755   | u=rwx,g=rx,o=rx |
| 644   | u=rw,g=r,o=r |
| 700   | u=rwx,g=,o= |

---

### **7.10 Hidden Permissions (CAP_* Capabilities)**

Linux capabilities are a way to grant specific privileges to processes.

Use Linux capabilities to manage fine-grained permissions beyond standard user/group/others.

- Example:

    ```bash
    setcap cap_net_bind_service=+ep /path/to/binary
    ```

---

### **7.11 Effective Permissions and the `stat` Command**

Effective permissions are the permissions that a user or process actually has.

Check effective permissions of a file.

```bash
stat filename
```

---

## **8. Security Best Practices**

- Avoid using `777` permissions unless absolutely necessary.
- Limit write permissions to trusted users.
- Use ACLs for more granular access control.
- Regularly review file permissions to ensure security compliance.
- Use `sudo` wisely and only when necessary.
- Regularly audit and update permissions to stay secure.
- Use `umask` to set default permissions for new files and directories.

