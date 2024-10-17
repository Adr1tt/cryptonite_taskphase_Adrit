# Untangling Users
- Learnt that there are alot of users on a typical Linux system. The full list of users on a Linux system is specified in the /etc/passwd file
    
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college
# Becomging root with su
- Learnt the `su` (the switch user command)
- Started the challenge and entered `su` into the terminal prompt and enetered the password-"hack-the-planet" to become the root user and used `cat /flag` to obtain the flag-  
  <img width="403" alt="image" src="https://github.com/user-attachments/assets/bb89b28e-8d90-4066-863d-c338fc5e4e31">  
  Flag Obtained- **pwn.college{Iqw74CLavV_NX_Tef79jXlj11mR.dVTN0UDL0YTN0czW}**
## Other users with su
- Learnt that we can provide usernames as arguements to `su` to switch to that user.
- Started the challenge and used `su zardus` and entered the password-"dont-hack-me". Then, I used `/challenge/run` to obtain the flag-  
  <img width="437" alt="image" src="https://github.com/user-attachments/assets/29d5ea44-ab26-4d4c-b916-57ee6e51c6d6">  
  Flag Obtained- **pwn.college{colSpOQEHszIvXvJDR6eSBdT362.dZTN0UDL0YTN0czW}**
## Cracking passwords
- Learnt that the passwords for the `su` command were stored in "/etc/passwd" which was moved to "/etc/shadow".
- In the contents of those files- Separated by ":"s, the first field of each line is the username and the second is the password.
 A value of * or ! functionally means that password login for the account is disabled,
  a blank field means that there is no password (a not-uncommon misconfiguration that allows password-less su in some configurations)
- Started the challenge and used `cat /challenge/shadow-leak` and then used `john /challenge/shadow-leak` and waited a few minutes to get the password.
  Then I used `su zardus` and entered the password to change users and used `/challenge/run` to obtain the flag-  
  <img width="929" alt="image" src="https://github.com/user-attachments/assets/cda28fe2-c68a-4b6e-94cb-cea22165092c">  
  Flag Obtained- **pwn.college{Ye_v8f6v8uOhxl8iWqWcpqnHjXi.ddTN0UDL0YTN0czW}**
## Using sudo
- Learnt the `sudo` command and how it's better than `su`. Also learnt that unlike su, rather than authenticating via password,
  sudo relies on policies that it checks to determine the user's authorization run things as root. These policies are defined in /etc/sudoers.
- Started the challenge and used `sudo cat /flag` to obtain the flag-  
  ![image](https://github.com/user-attachments/assets/f1fb0e0b-05c2-4834-9b9a-ff09445e1d72)  
  Flag Obtained- **pwn.college{oZIyyKqFs2AcIedZUZlyIWI4D3c.dhTN0UDL0YTN0czW}**

  


  

  
