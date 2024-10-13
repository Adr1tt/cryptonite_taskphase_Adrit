# Perceiving Permissions
- Learnt that in Linux, files have different permissions or file modes and we can check out permissions of a file or directory using `ls -l`.
- Learnt that in the output of `ls -l`, the first character which can be "d"(represents a directory) or a "-"(represents a normal file).
  The next nine characters are the actual access permissions of the file or directory,
  split into 3 characters denoting the permissions that the user who owns the file (termed the "owner") has to the file,
  3 characters denoting the permissions that the group that owns the file (termed the "group") has to the file,
  and 3 characters denoting the permissions that all other access (e.g., by other users and other groups) has to the file.
- Also learnt that in that nine character sequence the "r" stands for read, "w" stands for write and "x" stands for execute.
- Also learnt that there are two columns showing the user that owns the file and then the group that owns the file.

    
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college 
## Changing File Ownership
- Learnt the `chown` command which can change the owners of a file.
- Started the challenge and used `chown hacker /flag` and then I used `cat /flag` to obtain the flag-  
  <img width="457" alt="image" src="https://github.com/user-attachments/assets/d9b87f08-ddf9-4c88-afd9-97e442fadc2d">  
  Flag Obtained- **pwn.college{QpkLpzmfgRjHE_2MLPx_xbFQipQ.dFTM2QDL0YTN0czW}**
## Groups and Files
- Learnt that files have both an owning user and group. A group can have multiple users in it, and a user can be a member of multiple groups.
- Understood the `id ` command which can be used to see what groups the user is a part of.
- 


