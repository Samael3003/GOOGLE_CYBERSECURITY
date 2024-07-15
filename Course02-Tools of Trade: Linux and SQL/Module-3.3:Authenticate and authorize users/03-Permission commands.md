
# Permission Commands in Linux

## Overview

In this reading, we will review file permissions and the commands used to display and change them. Additionally, we'll focus on an example of how these commands work together when implementing the principle of least privilege.

## Reading Permissions

In Linux, permissions are represented with a 10-character string. Permissions include:

- **Read (r)**: 
  - For files: the ability to read the file contents.
  - For directories: the ability to read all contents in the directory, including both files and subdirectories.
- **Write (w)**: 
  - For files: the ability to make modifications to the file contents.
  - For directories: the ability to create new files in the directory.
- **Execute (x)**: 
  - For files: the ability to execute the file if it’s a program.
  - For directories: the ability to enter the directory and access its files.

These permissions are assigned to these types of owners:

- **User (u)**: The owner of the file.
- **Group (g)**: A larger group that the owner is a part of.
- **Other (o)**: All other users on the system.

### The 10-Character Permission String

Each character in the 10-character string conveys different information about these permissions. Here's what each character represents:

| Character Position | Example       | Meaning                                    |
|--------------------|---------------|--------------------------------------------|
| 1st                | drwxrwxrwx    | File type (`d` for directory, `-` for file) |
| 2nd                | drwxrwxrwx    | Read permissions for the user              |
| 3rd                | drwxrwxrwx    | Write permissions for the user             |
| 4th                | drwxrwxrwx    | Execute permissions for the user           |
| 5th                | drwxrwxrwx    | Read permissions for the group             |
| 6th                | drwxrwxrwx    | Write permissions for the group            |
| 7th                | drwxrwxrwx    | Execute permissions for the group          |
| 8th                | drwxrwxrwx    | Read permissions for other                 |
| 9th                | drwxrwxrwx    | Write permissions for other                |
| 10th               | drwxrwxrwx    | Execute permissions for other              |

## Exploring Existing Permissions

You can use the `ls` command to investigate who has permissions on files and directories. Here are a few important `ls` options for security analysts:

- `ls -a`: Displays hidden files. Hidden files start with a period (.) at the beginning.
- `ls -l`: Displays permissions to files and directories, along with additional information, including owner name, group, file size, and the time of last modification.
- `ls -la`: Displays permissions to files and directories, including hidden files (a combination of `ls -a` and `ls -l`).

## Changing Permissions

The principle of least privilege is the concept of granting only the minimal access and authorization required to complete a task or function. Not following this principle can create security risks. The `chmod` command can help you manage this authorization.

### Using `chmod`

The `chmod` command changes permissions on files and directories. It requires two arguments:
1. The first argument indicates how to change permissions.
2. The second argument indicates the file or directory that you want to change permissions for.

#### Examples:

- To add all permissions to `login_sessions.txt`:
  ```sh
  chmod u+rwx,g+rwx,o+rwx login_sessions.txt
  ```
- To take all permissions away from `login_sessions.txt`:
  ```sh
  chmod u-rwx,g-rwx,o-rwx login_sessions.txt
  ```
- To set read permissions for `login_sessions.txt` for user, group, and other:
  ```sh
  chmod u=r,g=r,o=r login_sessions.txt
  ```

This command overwrites existing permissions. For instance, if the user previously had write permissions, these write permissions are removed after you specify only read permissions with `=`.

### `chmod` Argument Characters

| Character | Description                                     |
|-----------|-------------------------------------------------|
| `u`       | Indicates changes will be made to user permissions   |
| `g`       | Indicates changes will be made to group permissions  |
| `o`       | Indicates changes will be made to other permissions  |
| `+`       | Adds permissions to the user, group, or other        |
| `-`       | Removes permissions from the user, group, or other   |
| `=`       | Assigns permissions for the user, group, or other    |

Note: When there are permission changes to more than one owner type, commas are needed to separate changes for each owner type. You should not add spaces after those commas.

## Principle of Least Privilege in Action

As a security analyst, you may encounter a situation like this one: There’s a file called `bonuses.txt` within a compensation directory. The owner of this file is a member of the Human Resources department with a username of `hrrep1`. It has been decided that `hrrep1` needs access to this file. But, since this file contains confidential information, no one else in the hr group needs access.

You run `ls -l` to check the permissions of files in the compensation directory and discover that the permissions for `bonuses.txt` are `-rw-rw----`. The group owner type has read and write permissions that do not align with the principle of least privilege.

To remedy the situation, you input:
```sh
chmod g-rw bonuses.txt
```
Now, only the user who needs to access this file to carry out their job responsibilities can access this file.

## Key Takeaways

Managing directory and file permissions may be a part of your work as a security analyst. Using `ls` with the `-l` and `-la` options allows you to investigate directory and file permissions. Using `chmod` allows you to change user permissions and ensure they are aligned with the principle of least privilege.
