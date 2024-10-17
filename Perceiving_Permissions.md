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
- Started the challenge and used `chmod o+r /flag` to change the permission of the flag file so I can `cat` it, then I used `cat /flag` to obtain the flag-  
  <img width="452" alt="image" src="https://github.com/user-attachments/assets/1f233271-ede3-41d6-be5e-59cc9e6f497c">  
  Flag Obtained- **pwn.college{8p0KoaWZQj3ouBUrgRYzEog2d5t.dNzNyUDL0YTN0czW}**
## Executable Files
- Started the challenge and used `chmod o+x /challenge/run` to change permissions and then used `/challenge/run`, but it didnt work. Then I used `ls -l /challenge/run` to see the owner of the file and found that it was hacker, therefore I used `chmod u+x /challenge/run` and then used `/challenge/run` to obtain the flag-  
  <img width="463" alt="image" src="https://github.com/user-attachments/assets/5ed93154-071b-4450-9456-b092e90785bf">  
  Flag Obtained- **pwn.college{EL9VuCDrxbu1PV-Z2n-vYFi66Os.dJTM2QDL0YTN0czW}**
## Permission Tweaking Practice
- Started the challenge and went through 8 rounds of changing permissions, and finally at the end I needed the change the permissions of the "/flag" file (also I used `ls -l /flag` to see who owned the flag file) and `cat` it to obtain the flag
``` bash
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 0 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-r--r-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o+x /challenge/pwn
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rw-r-xr-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+x /challenge/pwn
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": rw-r-xr-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxrwxr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+x,g+w /challenge/pwn
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": rwxrwxr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r--r--r-x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ug-wx
/usr/bin/chmod: missing operand after ‘ug-wx’
Try '/usr/bin/chmod --help' for more information.
NEEDED, BUT UNMET permissions of "/challenge/pwn": r--r--r-x
* the user does have read permissions
                                                                                                                                                                Connected!
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 0 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-r--r-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o+x /challenge/pwn
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rw-r-xr-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+x /challenge/pwn
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": rw-r-xr-x
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxrwxr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+x,g+w /challenge/pwn
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": rwxrwxr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r--r--r-x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ug-wx /challenge/pwn
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": r--r--r-x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r--r--r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-x /challenge/pwn
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": r--r--r--
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-rw-rw-
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ugo+w /challenge/pwn
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": rw-rw-rw-
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-rwxrw-
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g+x /challenge/pwn
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": rw-rwxrw-
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-rwx-w-
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o-r /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ ls -l /flag
---------- 1 hacker hacker 58 Oct 17 15:09 /flag
hacker@permissions~permission-tweaking-practice:~$ chmod u+r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{0sAGDSyumY6sjknChp7TDm-X_EO.dBTM2QDL0YTN0czW}
```
Obtained Flag- **pwn.college{0sAGDSyumY6sjknChp7TDm-X_EO.dBTM2QDL0YTN0czW}**
## Permissions Setting Practice
- Learnt that we can overwrite permissions using "=" and that we can zero out permissions with "=-".
- Started the challenge and went through 8 rounds of changing permissions, and finally at the end I needed the change the permissions of the "/flag" file (also I used `ls -l /flag` to see who owned the flag file) and `cat` it to obtain the flag
```bash
  hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 0 (of 8)!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwx-w-rw-
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=w,o=rw /challenge/pwn
You set the correct permissions!
Round 1 (of 8)!

Current permissions of "/challenge/pwn": rwx-w-rw-
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -w---x-wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=x,o=wx /challenge/pwn
You set the correct permissions!
Round 2 (of 8)!

Current permissions of "/challenge/pwn": -w---x-wx
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rwxrwxr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod a=rwx,o-w /challenge/pwn
You set the correct permissions!
Round 3 (of 8)!

Current permissions of "/challenge/pwn": rwxrwxr-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": rw---xrw-
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod uo=rw,g=x /challenge/pwn
You set the correct permissions!
Round 4 (of 8)!

Current permissions of "/challenge/pwn": rw---xrw-
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -------w-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=-,g=-,o=w /challenge/pwn
You set the correct permissions!
Round 5 (of 8)!

Current permissions of "/challenge/pwn": -------w-
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": --xrwx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=rwx,o=wx /challenge/pwn
You set the correct permissions!
Round 6 (of 8)!

Current permissions of "/challenge/pwn": --xrwx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r---w-rw-
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=w,o=rw /challenge/pwn
You set the correct permissions!
Round 7 (of 8)!

Current permissions of "/challenge/pwn": r---w-rw-
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wxr--r--
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,go=r /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ ls -l /flag
---------- 1 hacker hacker 58 Oct 17 15:41 /flag
hacker@permissions~permissions-setting-practice:~$ chmod u+r /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{o8e1kQNOCPy35soD4mz3bVkrzhc.dNTM5QDL0YTN0czW}
```
Flag Obtained- **pwn.college{o8e1kQNOCPy35soD4mz3bVkrzhc.dNTM5QDL0YTN0czW}**
## The SUID Bit
- Learnt that the "Set User ID" (SUID) permissions bit allows the user to run a program as the owner of that program's file.
- The s part in place of the executable bit means that the program is executable with SUID.
- The s part in place of the executable bit means that the program is executable with SUID. It means that, regardless of what user runs the program (as long as they have executable permissions), the program will execute as the owner user (in this case, the root user).
- As the owner of a file, we can set a file's SUID bit by using `chmod u+s [program]`.
- Started the challenge and used `chmod u+s /challenge/getroot` and then `/challenge/getroot` to spawn a root shell and then used `cat /flag` to obtain the flag-  
  ![image](https://github.com/user-attachments/assets/b5ee7195-ca0e-4870-bdc6-83e2e8fbba14)  
  pwn.college{YoS2jhTjd80stN96eonrjqnBLEY.dNTM2QDL0YTN0czW}






