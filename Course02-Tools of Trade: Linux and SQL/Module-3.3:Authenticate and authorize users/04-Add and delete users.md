
# Adding and Deleting Users in Linux

## Introduction
- **Authentication**: The process of verifying a user's identity within the system.
- **Access Control**: Not all users should have access; it's essential to manage user permissions effectively.

## User Management
- **Adding Users**: Necessary for new hires or changes in organizational structure.
- **Deleting Users**: Important for users leaving the organization or changing groups to maintain security.

## Root User
- **Definition**: The root user, or superuser, has elevated privileges to modify the system.
- **Root Privileges**: Regular users have limitations that root users do not.
- **Temporary Root Access**: Individuals can be temporarily granted root privileges for specific tasks.

### Risks of Using Root
- **Security Risks**: The root account is a prime target for malicious actors; logins should be disabled.
- **Irreversible Mistakes**: Running commands as root increases the risk of severe errors, such as accidental deletions.
- **Accountability Issues**: Actions taken as root cannot be easily tracked to individual users.

## Solution: `sudo`
- **Purpose**: `sudo` temporarily grants elevated permissions to specific users without full root access.
- **Usage**: `sudo` allows users to execute commands as an elevated user after entering their password.
- **Sudoers File**: Users must be granted sudo access via the configuration file called the sudoers file.

## Adding Users with `useradd`
- **Command**: `useradd` is used to add users to the system.
- **Example**: To add a user named `salesrep7`, use:
  ```bash
  sudo useradd salesrep7
  ```
- **Success Indication**: A new Bash cursor without an error message indicates successful execution.

## Deleting Users with `userdel`
- **Command**: `userdel` deletes users from the system.
- **Example**: To delete `salesrep7`, use:
  ```bash
  sudo userdel salesrep7
  ```
- **Success Indication**: Similar to adding a user, success is indicated by a new Bash cursor without an error message.

## Conclusion
- Managing user accounts responsibly with `sudo` is crucial for maintaining a secure system. Use elevated privileges judiciously.
