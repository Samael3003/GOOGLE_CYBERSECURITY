
# Interactive Transcript: Changing Permissions in Linux

## Introduction

Hi there! In the previous video, you learned how to check permissions for a user. In this video, we're going to learn about changing permissions.

## Importance of Changing Permissions

When working as a security analyst, there may be many reasons to change permissions for a user. A user may have changed departments or been assigned to a different work group. A user might simply no longer be working on a project that requires certain permissions. These changes are necessary in order to protect system files from being accidentally or deliberately altered or deleted.

## Using the `chmod` Command

Let's explore a related command that helps control this access. In this video, we'll learn about `chmod`. `chmod` changes permissions on files and directories. The command `chmod` stands for change mode.

### Modes for Changing Permissions

There are two modes for changing permissions, but we'll focus on symbolic mode. The best way to learn about how `chmod` works is through an example. I know this has a lot of details, but we'll break this down. Also, please keep in mind that, like many Linux commands, you don't have to memorize the information and can always find a reference.

With `chmod`, you need to identify which file or directory you want to adjust permissions for. This is the final argument, in this case, a file named `access.txt`. The first argument, added directly after the `chmod` command, indicates how to change permissions. Right now, this might seem hard to interpret, but soon we'll understand why this is called symbolic mode.

### Symbolic Mode

Previously, we learned about the three types of owners: user, group, and other. To identify these with `chmod`, we use `u` to represent the user, `g` to represent the group, and `o` to represent other. In this particular example, `g` indicates we will make some changes to group permissions, and `o` to permissions for other. These owner types are separated by a comma in this argument.

### Adding and Removing Permissions

But do we want to add or take away permissions? For this, we use mathematical operators:
- The `+` sign after `g` means we want to add permissions for the group.
- The `-` sign after `o` means we want to take away permissions from other.

### Types of Permissions

We've already learned that `r` represents read permissions, `w` represents write permissions, and `x` represents execute permissions. So in this case, the `w` indicates that we're adding write permissions to the group, and `r` indicates that we are taking away read permissions from other. This is still very complex. But now that we've broken it down, perhaps it doesn't seem quite so much like a foreign language. And remember, you don't have to memorize this all.

## Practical Example

Let's give this new command a try. We'll start out in the logs sub-directory. If we use the `ls -l` command, it will output the permissions for the file. It shows the permissions for the only file in this directory: `access.txt`.

Previously, we learned how to read these permissions:
- The second through fourth characters indicate that the user has read and write permissions.
- The fifth through seventh characters show the group only has read permissions.
- The eighth to tenth characters show that other only has read permissions.

### Adjusting Permissions

We want to ensure analysts in the security group have write permission, but take away read permissions from the owner-type other, so we add write permissions for the group and remove read permissions for other.

```sh
chmod g+w,o-r access.txt
```

Let's run `ls -l` again. This shows a change in the permissions for `access.txt`. Notice how in the middle segment of permissions for the group, `w` has been added to give write permissions. And another change is that the `r` has been removed in the last segment, indicating that read permissions for other have been removed. As mentioned earlier, these hyphens indicate a lack of permissions. Now, other is lacking all permissions.

## Conclusion

Though it requires practice, working in Linux becomes more natural with time. I'm glad you're learning a little more about how to use Linux.
