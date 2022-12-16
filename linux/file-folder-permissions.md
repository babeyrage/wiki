# File & Folder Permissions

Which file would be accessed by which user is decided by two factors in Linux:

-   File ownership
-   File permission

Every file and directory in Linux has three kinds of owners:

### User

User is the owner of the file. When you create a file, you become the owner of the file. 

### Group

Every user is part of a certain group(s). A group consists of several users and this is one way to manage users in a multi-user environment.

### Other

‘Other’ can be considered as a super group with all the users on the system. Basically, anyone with access to the system belongs to this group.

In other words, ‘User’ is a single user, Group is a collection of users and Other consists of all the users on the system.

## File permissions in Linux

Every file and directory in Linux has the following three permissions for all the three kinds of owners:

**Permissions for files**

-   Read – Can view or copy file contents
-   Write – Can modify file content
-   Execute – Can run the file (if its executable)

**Permissions for directories**

-   Read – Can list all files and copy the files from directory
-   Write – Can add or delete files into directory (needs execute permission as well)
-   Execute – Can enter the directory

If you use the *ls* command with option -l on a file, you’ll see an output like this:

```bash
-rwxrw-r-- 1 abhi itsfoss 457 Aug 10 11:55 agatha.txt
```

![[Pasted image 20221120153420.png]]

-   **File type**: Denotes the type of file. d means directory, – means regular file, l means a [symbolic link](https://linuxhandbook.com/symbolic-link-linux/).
-   **Permissions**: This field shows the permission set on a file. I’ll explain it in detail in the next section.
-   **Hard link count**: Shows if the file has [hard links](https://linuxhandbook.com/hard-link/). Default count is one.
-   **User**: The user who owns the files.
-   **Group**: The group that has access to this file. Only one group can be the owner of a file at a time.
-   **File size**: Size of the file in bytes.
-   **Modification time**: The date and time the file was last modified.
-   **Filename**: Obviously, the name of the file or directory.

Each letter denotes a particular permission:

-   r : Read permission
-   w : Write permission
-   x : Execute permission
-   – : No permission set

Permissions are always in the order of read, write and execute, i.e., rwx. And then these permissions are set for all three kind of owners (see the ownership section) in the order of User, Group and Other.

![[Pasted image 20221120153700.png]]

## Change file permissions in Linux

You can use [chmod](https://linux.die.net/man/1/chmod) command for changing the permissions on a file in Linux.

There are two ways to use the chmod command:

-   Absolute mode
-   Symbolic mode

### Using chmod in absolute mode

In the absolute mode, permissions are represented in numeric form (octal system to be precise). In this system, each file permission is represented by a number.

-   r (read) = 4
-   w (write) = 2
-   x (execute) = 1
-   – (no permission) = 0

| Number    | Permission |
| --------- | ---------- |
| 0         | ---        |
| 1         | --x        |
| 2         | -w-        |
| 3 (2 + 1) | -wx        |
| 4         | r--        |
| 5 (4 + 1) | r-x        |
| 6 (4 + 2) | rw-        |
| 7 (4 + 3) | rwx           |

```bash
chmod 666 text.txt
```

This will give the text file permissions of rw-rw-rw-

### Using chmod in symbolic mode

The problem with the absolute mode is that you should always provide three numbers for all the three owners even if you want to change the  permission set for just one owner.

In symbolic mode, owners are denoted with the following symbols:

-   u = user owner
-   g = group owner
-   o = other
-   a = all (user + group + other)

The symbolic mode uses mathematical operators to perform the permission changes:

-   + for adding permissions
-   – for removing permissions
-   = for overriding existing permissions with new value