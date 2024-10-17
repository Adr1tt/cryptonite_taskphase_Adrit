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
- Learnt the `chgrp` command which is used to change the group ownership of a file or directory.
- Started the challenge and used `chgrp hacker /flag` and then used `cat /flag` to obtain the flag-  
  <img width="411" alt="image" src="https://github.com/user-attachments/assets/6a2c9a3b-d918-4dbb-b837-7184a525af10">  
  Flag Obtained- **pwn.college{kWHjSg3cBzYPNlUsRGn5Uzo1LBY.dFzNyUDL0YTN0czW}**
## Fun With Groups Names
- Started the challenge and used the `id` command which gave me the name of the group and then I used the `chgrp` command and obtained the flag using `cat`-  
  <img width="452" alt="image" src="https://github.com/user-attachments/assets/d15faa2c-3d5d-4370-b944-94963df1c578">  
  Flag Obtained- **pwn.college{w7SJu4j6k3oep4ZsA2yc1x8ZnsM.dJzNyUDL0YTN0czW}**
## Changing Permissions
- Learnt the `chmod` command and also learnt that `chmod` allows us to tweak permissions with the mode format of WHO+/-WHAT, where WHO is user/group/other and WHAT is read/write/execute. "+" adds a permission and "-" removes a permission.




