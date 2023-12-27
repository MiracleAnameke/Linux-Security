# Linux Security

## Lab Overview

This lab focuses on various aspects of Linux security, including root access, creating users, managing file permissions, and using special permissions like SUID/GUID and sticky bits. The lab is conducted on an Ubuntu server, where students will perform tasks related to user and password management, file attributes, and encryption techniques.

## Preparation

- Download and install Ubuntu for the lab.
- Create a new virtual machine and install Ubuntu.

## Lab Tasks and Screenshots

### Slide 1: SUID/GUID Bits and File Permissions

Task: Log in as a student user, create a directory and file, modify permissions with SUID/GUID bits, and then as the root user, inspect these changes.

- **Screenshot for Slide 1**: Include the `cat /etc/passwd`, `ls -ail` for the created file and directory showing the SUID/GUID bits, and the `uname -a` output.
  <img src="https://i.imgur.com/cZ9welq.png" height="400px" width="auto" alt="SUID/GUID Bits and File Permissions"/>

### Slide 2: Sticky Bit on Directories

Task: As root, create a directory, modify its permissions to include the sticky bit, and demonstrate file creation and deletion by different users within this directory.

- **Screenshot for Slide 2**: Show the directory permissions after adding the sticky bit, the files created by different users, and the attempt to remove files by users other than the owner.
  <img src="https://i.imgur.com/5SjbV8s.png" height="400px" width="auto" alt="Sticky Bit on Directories"/>

### Slide 3: File Attributes - Immutable Attribute

Task: Add the immutable attribute to a file and attempt to modify it as root, showcasing the attribute's effect.

- **Screenshot for Slide 3**: Display the `lsattr` output for the file with the immutable attribute, the attempt (and failure) to remove the file, and the system information with `uname -a`.
  <img src="https://i.imgur.com/ZhgyQYk.png" height="400px" width="auto" alt="File Attributes - Immutable Attribute"/>

### Slide 4: User Password Encryption

Task: Change the password encryption method for the system and demonstrate the differences in password hashes for users.

- **Screenshot for Slide 4**: Show the `cat common-password | grep success=`, `cat shadow | grep student-03`, `cat shadow | grep student-04`, and `uname -a` to illustrate the different hashes.
  <img src="https://i.imgur.com/Xm4fV3S.png" height="400px" width="auto" alt="User Password Encryption"/>

## Lab Questions and Answers

- **Why is there a capital 'S' instead of a lowercase 's'?**: The capital 'S' in the file permissions indicates that while the SUID is active, the file is not executable by the owner. 
- **What happens when the sticky bit is set on a directory?**: Only the file's owner, the directory's owner, or the root user can delete or rename files within that directory. 
- **What is the effect of the immutable attribute?**: Even as root, attempting to remove or modify the file with the immutable attribute set results in an operation denial.
- **How do password encryption changes affect the user?**: Changing the password encryption method (e.g., from sha512 to md5) alters how passwords are stored in the system. New passwords will use the updated algorithm, changing the appearance and security level of password hashes.


