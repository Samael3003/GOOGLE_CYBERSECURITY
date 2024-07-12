
# Lecture Notes: Navigating the Linux File System

## Introduction

Understanding how to navigate the Linux file system is crucial for utilizing the Linux command line effectively. As a security analyst, you will frequently interact with server logs and need to manage files and directories without a graphical user interface.

## The Linux File System

- **Filesystem Hierarchy Standard (FHS)**: Organizes data within the Linux OS. It is a hierarchical system where everything grows and branches out from the root directory.
- **Root Directory**: The highest-level directory in Linux, designated by a single slash (`/`). All other subdirectories branch out from the root.

### File System Structure

- **Example Path**: `/home/analyst`
  - The first slash (`/`) indicates the root directory.
  - `home` is a subdirectory branching from the root.
  - `analyst` is a subdirectory within `home`.

## Essential Commands for Navigation

### `pwd` (Print Working Directory)

- **Purpose**: Displays the current directory you are working in.
- **Usage**: 
  ```sh
  pwd
  ```
  - **Output**: The path to the current directory.

### `ls` (List)

- **Purpose**: Displays the names of files and directories in the current working directory.
- **Usage**: 
  ```sh
  ls
  ```
  - **Output**: Names of files and directories.

### `cd` (Change Directory)

- **Purpose**: Navigates between directories.
- **Usage**: 
  ```sh
  cd directory_name
  ```
  - **Note**: No output if successful. Use `pwd` to confirm the change.

## Example: Using Navigation Commands

1. **Print Working Directory**:
   ```sh
   pwd
   ```
   - **Output**: `/home/analyst`

2. **List Files and Directories**:
   ```sh
   ls
   ```
   - **Output**: `logs oldreports projects reports updates.txt`

3. **Change to Logs Directory**:
   ```sh
   cd logs
   ```
   - **No Output**. Use `pwd` to confirm:
     ```sh
     pwd
     ```
     - **Output**: `/home/analyst/logs`

## Reading File Content

As a security analyst, reading file content is essential for tasks such as identifying potential vulnerabilities and investigating unauthorized access.

### `cat` (Concatenate)

- **Purpose**: Displays the full content of a file.
- **Usage**: 
  ```sh
  cat file_name
  ```
  - **Example**: `cat access.txt`

### `head`

- **Purpose**: Displays the beginning of a file (default: first 10 lines).
- **Usage**: 
  ```sh
  head file_name
  ```
  - **Example**: `head access.txt`

## Example: Reading File Content

1. **Display Full Content**:
   ```sh
   cat access.txt
   ```
   - **Output**: Full contents of `access.txt`.

2. **Display First 10 Lines**:
   ```sh
   head access.txt
   ```
   - **Output**: First 10 lines of `access.txt`.

## Conclusion

Learning to navigate the Linux file system using these essential commands is crucial for security analysts. You will use these commands to locate and analyze logs, manage files, and perform various security-related tasks. Next, we will explore how to manage the system effectively.
