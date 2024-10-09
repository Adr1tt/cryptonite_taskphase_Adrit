# Practicing Piping
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college
## Redirecting output
- Learnt that we can redirect output to files by using ">".
- Started the challenge and used `echo PWN > COLLEGE` which redirected the output to the file "COLLEGE" and thus obtained the flag-  
  <img width="552" alt="image" src="https://github.com/user-attachments/assets/6122bc54-c32a-48cf-af07-4195d4506a99">  
  Flag Obtained- **pwn.college{o4imSmhbw8Sy_oiJPm3zOJ3gthJ.dRjN1QDL0YTN0czW}**
## Redirecting more output
- Started the challenge and entered `/challenge/run > myflag` into the terminal to redirect output to the "myflag" file and then used the `cat` command to obtain the flag-  
  <img width="653" alt="image" src="https://github.com/user-attachments/assets/71670b33-340d-4694-9d6b-411614952279">  
  Flag Obtained- **pwn.college{cjHbNMbZhdBP7YMKHbCZ9MprPId.dVjN1QDL0YTN0czW}**
## Appending output
- Learnt that we can redirect output in append mode using ">>" instead of using ">".
- Started the challenge and as per the instructions given in the challenge description I used `/challenge/run >> /home/hacker/the-flag` for appending the second part of the flag and then used `cat /home/hacker/the-flag` to obtain the flag-  
  <img width="854" alt="image" src="https://github.com/user-attachments/assets/fe11a404-69df-4515-9a6a-92d99aef06c6">  
  Flag Obtained- **pwn.college{8X_X7ZlhreqaxSoKnBu-tIq50BI.ddDM5QDL0YTN0czW}**
## Redirecting errors
- Learnt about File Descriptor(FD) which is a number the describes a communication channel in Linux.
  - FD 0: Standard Input
  - FD 1: Standard Output
  - FD 2: Standard Error
- Also learnt that when we redirect process communication, we do it by FD number(s) and a ">" without a number implies "1>".
- Also learnt that we can redirect multiple file descriptors at the same time(like this-some_command > output.log 2> errors.log).
- Started the challenge and used `/challenge/run > myflag 2> instructions` which redirected the output to "myflag" and standard error to "instructions".
- Then I used `cat myflag` to obtain the flag-  
  <img width="532" alt="image" src="https://github.com/user-attachments/assets/e32a9ffa-efb0-4f95-845d-130611702976">  
  Flag Obtained- **pwn.College{8VRk]IdAzRDpeHpCK19BdnHD7xq•ddjN1QDL0YTNOczW}**
## Redirecting Input
- Learnt that we can redirect intput to files by using "<".
- Started the challenge and as per the given instructions in the challenge I used `echo COLLEGE > PWN` to redirect output and then used `/challenge/run < PWN` to redirect input, thus obtaining the flag-  
  <img width="542" alt="image" src="https://github.com/user-attachments/assets/71baee87-06ec-426c-9a0c-a5449a579fe1">  
  Flag Obtained- **pwn.college{wbRE01797eZxXQIIWEU1_1eTzVc.dBzN1QDL0YTN0czW}**
## Grepping stored results
- Started the challenge and used `/challenge/run > /tmp/data.txt` to redirect output of /challenge/run to /tmp/data.txt.  
  <img width="858" alt="image" src="https://github.com/user-attachments/assets/b50535b7-5044-4c04-b1eb-79ab6fd6b9f7">  
- Then I used `grep pwn /tmp/data.txt` and thus obtained the flag-  
  ![image](https://github.com/user-attachments/assets/c66d0148-4382-4e38-9a3b-490da2db6493)  
  Flag Obtained- **pwn.college{gxWUnvVC2WBZSTGt_dxQ0-6RSHa.dhTM4QDL0YTN0czW}**
## Grepping live output
- Learnt that we can avoid the need to store results to a file by using the | (pipe) operator. Standard output from the command to the left of the pipe will be connected to (piped into) the standard input of the command to the right of the pipe.
- Started the challenge and used `/challenge/run | grep pwn.college` to obtain the flag-  
  <img width="1052" alt="image" src="https://github.com/user-attachments/assets/d21129f9-39c7-461f-9289-110e5dec55c9">  
  Flag Obtained- **pwn.college{QzbByoJ3FV1QJNkxpMvhjax64_2.dlTM4QDL0YTN0czW}**
## Grepping errors
- Understood that we can redirect a file descriptor to another file descriptor by using `>&`.
- Started the challenge used `/challenge/run 2>& 1|grep pwn.college` to obtain the flag-  
  <img width="1044" alt="image" src="https://github.com/user-attachments/assets/47865070-e6fa-496e-b886-9a915e71b7fc">  
  Flag Obtained- **pwn.college{cmfNN-n24rXA8EgbVa6-M4dToiJ.dVDM5QDL0YTN0czW}**
## Duplicating piped data with tee
- Learnt the `tee` command which duplicates data flowing through your pipes to any number of files provided on the command line.
- Started the challenge and used `/challenge/pwn | tee output | /challenge/college` where `tee output` intercepts the data and then I used `cat output` to understand what the code needs to be.  
  <img width="687" alt="image" src="https://github.com/user-attachments/assets/80657946-e794-4dfc-910f-cc7d6fda2db5">  
- After understanding that I need to pass an arguement with `/challenge/pwn` I used `/challenge/pwn --secret IK2acYy1 | /challenge/college` to obtain the flag-  
  <img width="723" alt="image" src="https://github.com/user-attachments/assets/983bcd11-e6d0-4014-9bf6-fe6e3c927f36">  
  Flag Obtained- **pwn.college{IK2acYy1TaPmRNDZkbT-wV8jGAY.dFjM5QDL0YTN0czW}**
## Writing to multiple programs
- Learnt the concept of "Process Substitution" and "Named pipes".
- Started the challenge and used `/challenge/hack | tee >(/challenge/the) >(/challenge/planet)` which runs the /challenge/hack command, and duplicates its output as input to both the /challenge/the and the /challenge/planet commands and thus I obtained the flag-  
  <img width="749" alt="image" src="https://github.com/user-attachments/assets/18c5d1c0-10c2-4698-b7b5-d89becaaa03a">  
  Flag Obtained- **pwn.college{87J5WfdBVXJ6A3F2CpxNNE_2w6n.dBDO0UDL0YTN0czW}**  
**References-**
  *https://www.gnu.org/software/bash/manual/html_node/Process-Substitution.html*
## Split-piping stderr and stdout
- Started the challenge, and at first I used `/challenge/hack | tee 2> >(/challenge/the) 1> >(/challenge/planet)` which was wrong as it wasn't redirecting the stderr and stdout properly. Then, I entered `/challenge/hack 2> >(/challenge/the) 1> >(/challenge/planet)` into the terminal prompt which gave me the flag-  
  ![image](https://github.com/user-attachments/assets/87b5b583-538f-40e3-a2c2-d33bba89a8e4)  
  Flag Obtained- **pwn.college{gBRtgYEUI2azhsSSF6D6m9lLrPo.dFDNwYDL0YTN0czW}**









 


  

