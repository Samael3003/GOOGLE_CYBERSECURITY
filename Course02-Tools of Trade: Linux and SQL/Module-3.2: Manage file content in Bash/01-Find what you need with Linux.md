
# Navigating Linux and Reading File Content

## Filesystem Hierarchy Standard (FHS)

The Filesystem Hierarchy Standard (FHS) is crucial in Linux for organizing data. It defines how directories, directory contents, and other storage are structured in the operating system.

### FHS Hierarchy

- **Root Directory**: Represented by a single slash (`/`). It is the highest-level directory in Linux, with all subdirectories branching out from it.
- **Standard FHS Directories**:
  - **/home**: Contains user-specific subdirectories.
  - **/bin**: Stands for "binary" and contains executable files.
  - **/etc**: Stores system configuration files.
  - **/tmp**: Holds temporary files, commonly used by attackers due to open modification access.
  - **/mnt**: Used for mounting media like USB drives and hard drives.

### User-Specific Subdirectories

- Subdirectories under `/home` are specific to users. For example, `/home/analyst` and `/home/analyst2`.
- User directories can be represented with a tilde (`~`). For instance, `/home/analyst/logs` can be written as `~/logs`.

## Navigating the File System

Key commands for navigating the file system in Linux are `pwd`, `ls`, and `cd`.

### `pwd` (Print Working Directory)

- **Purpose**: Displays the current directory.
- **Usage**:
  ```sh
  pwd
  ```
  - **Output**: Absolute path of the current directory.

### `ls` (List)

- **Purpose**: Lists files and directories in the current working directory.
- **Usage**:
  ```sh
  ls
  ```
  - **Output**: Names of files and directories.
- **Note**: Use an argument for listing contents of a different directory.
  ```sh
  ls /home/analyst/projects
  ls projects
  ```

### `cd` (Change Directory)

- **Purpose**: Changes the current directory.
- **Usage**:
  ```sh
  cd directory_name
  cd /home/analyst/logs
  cd ..
  ```
  - **Note**: `cd ..` moves up one level in the directory structure.

## Reading File Content

Essential commands for reading file content are `cat`, `head`, `tail`, and `less`.

### `cat` (Concatenate)

- **Purpose**: Displays the full content of a file.
- **Usage**:
  ```sh
  cat file_name
  ```
  - **Example**: `cat updates.txt`

### `head`

- **Purpose**: Displays the beginning of a file (default: first 10 lines).
- **Usage**:
  ```sh
  head file_name
  head -n number_of_lines file_name
  ```
  - **Example**: `head updates.txt`, `head -n 5 updates.txt`

### `tail`

- **Purpose**: Displays the end of a file (default: last 10 lines).
- **Usage**:
  ```sh
  tail file_name
  ```
  - **Example**: `tail updates.txt`

### `less`

- **Purpose**: Returns the content of a file one page at a time.
- **Usage**:
  ```sh
  less file_name
  ```
  - **Example**: `less updates.txt`

- **Keyboard Controls**:
  - Space bar: Move forward one page
  - b: Move back one page
  - Down arrow: Move forward one line
  - Up arrow: Move back one line
  - q: Quit and return to the previous terminal window

## Filtering in Linux

As a security analyst, filtering is an important skill. Here are key commands for filtering data in Linux.

### `grep` (Global Regular Expression Print)

- **Purpose**: Searches a specified file and returns all lines containing a specified string.
- **Usage**:
  ```sh
  grep string file_name
  ```
  - **Example**:
    ```sh
    grep OS updates.txt
    ```
  - **Description**: Searches for the string "OS" in `updates.txt` and returns lines containing "OS".

### Piping

- **Purpose**: Sends the standard output of one command as standard input to another command for further processing.
- **Symbol**: `|` (pipe character)
- **Usage Example**:
  ```sh
  ls | grep string
  ```
  - **Description**: Sends the output of `ls` to `grep` to filter files containing "string".

### Piping with `grep`

- **Example**:
  ```sh
  ls /home/analyst/reports | grep users
  ```
  - **Description**: Lists all files in `/home/analyst/reports` and filters those containing the word "users".

## Key Takeaways

- **Navigation Commands**: `pwd`, `ls`, and `cd` are essential for navigating the Linux file system.
- **Reading File Content**: `cat`, `head`, `tail`, and `less` are crucial for reading file content.
- **Filtering**: Use `grep` to search for specific strings within files and combine with piping to filter command outputs effectively.

Understanding these commands and the structure of the FHS is vital for performing tasks efficiently as a security analyst.
