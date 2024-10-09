# Pondering Paths  
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)  

## The Root
- Understood the concept of tree filesystem(starting at /) and directories.
- Started the challenge and entered `/pwn` in the terminal prompt to get the flag  
  ![image](https://github.com/user-attachments/assets/b2d4d97b-bae9-44b0-bdd5-389b5cacc9f8)  
  Flag Obtained- **pwn.college{oZPKIsYpmmn_gh0a3mq58cE2U_V.dhzN5QDL0YTN0czW}**

## Program and absolute paths
- In this challenge we had to execute the **run** file which is said to be in the **challenge** directory which is in the root dictonary(/)
- Started the challenge and entered `/challenge/run` in the terminal prompt to get the flag  
  ![image](https://github.com/user-attachments/assets/002d2136-c741-43b3-ba6d-f8087b1c109f)  
  Flag Obtained- **pwn.college{AjBIcf8QMReH_phm7wKT7vO4eO_.dVDN1QDL0YTN0czW}**
## Position thy self
- Understood that we can navigate around directories by using the cd (change directory) command and passing a path to it as an argument.
- Started the challenge and used `/challenge/run` and the following output is shown in the terminal-
  <img width="441" alt="image" src="https://github.com/user-attachments/assets/00664e78-58b3-486a-8d47-54f8751ca3d0">
- Entered `cd /` to change the directory and used `/challenge/run` to obtain the flag
  ![image](https://github.com/user-attachments/assets/b006b87d-de29-44a1-abf4-767ed6247a3e)
  Flag Obtained- **pwn.college{cH8dQn4Z6VM9HANjX7A6Cdm1fpS.dZDN1QDL0YTN0czW}**
## Position elsewhere
- Started the challenge and used `/challenge/run` and the following output is shown in the terminal-
  ![image](https://github.com/user-attachments/assets/d58545c5-0222-40c8-b960-88303b115116)
  
- Entered `cd /usr/aarch64-linux-gnu/include/gnu` to change the directory and used `/challenge/run` to obtain the flag
  ![image](https://github.com/user-attachments/assets/c0020f50-393b-4f71-80c6-f1c4b3100ecc)
  ![image](https://github.com/user-attachments/assets/9789a679-81e5-4976-85eb-b3cb65288793)
  Flag Obtained- **pwn.college{EXuxMbkxlJfINaUQvAE8_aRwDdW.ddDN1QDL0YTN0czW}**
## Position yet elsewhere
- Started the challenge and used `/challenge/run` to the following output is shown in the terminal-
  <img width="448" alt="image" src="https://github.com/user-attachments/assets/18b79dbd-414a-4325-b7d2-7175909dce7b">
- Entered `cd /etc/apt/sources.list.d` in the terminal prompt to change the directory and used `/challenge/run` to obtain the flag
  <img width="529" alt="image" src="https://github.com/user-attachments/assets/0fc1c806-86dd-4524-bb20-72454b393f1e">  
  Flag Obtained- **pwn.college{Qp84riXpWI153BGSJOsIxGX0AgD.dhDN1QDL0YTN0czW}**
## Implicit relative paths, from /
- Understood the concept of relative paths and cwd(current working directory).
- Started the challenge and used `/challenge/run` and the following output is shown in the terminal-
  <img width="435" alt="image" src="https://github.com/user-attachments/assets/a615c08f-6d46-49df-b32e-3214589b20f1">

- Entered `cd /` in the terminal prompt to change the directory and then entered `challenge/run` (as the hint in the challenge said the relative path starts with "c") to obtain the flag-
  ![image](https://github.com/user-attachments/assets/bacff82b-4ab1-4a7c-b993-ee01cb3e024e)
  Flag Obtained -**pwn.college{4rurRVvFc4IraTKqUMfgxCFq10S.dlDN1QDL0YTN0czW}**
## Explicit relative paths, from /
- Understood the use of "." in relative paths.
- Started the challenge and used `cd /` to change the directory (to `/`) and then entered `./challenge/run` to obtain the flag
  ![image](https://github.com/user-attachments/assets/32c4d024-b0d1-4c1c-bcba-3bdcba5c7412)
  Flag Obtained- **pwn.college{MT65irIkTVSfsu7HPs0DUcvrpZ3.dBTN1QDL0YTN0czW}**
## Implicit relative path
- Understood that Linux explicitly avoids automatically looking in the current directory when you provide a "naked" path.
- Started the challenge and used `cd /challenge` to change the directory and then entered `./run` (because . refers to the current directory) to obtain the flag
  ![image](https://github.com/user-attachments/assets/6766b954-486f-42fe-ac04-ff7e95a0ce23)  
  Flag Obtained- **pwn.college{w1YmjGiKnxOi6zuHPMWnOVDg2G_.dFTN1QDL0YTN0czW}**
## Home sweet Home
- Understood the concept of home directory, where users usually store most of their personal files.
- Understood that "~" is the current working directory and in this case it is the shorthand for `/home/hacker`
- Started the challenge and entered `/challenge/run ~/a` in the terminal prompt where `~/a` is the arguement(which is an absolute path, inside the home directory and has three characters). Therefore a copy of the flag was being written in `/home/hacker/a`. Thus the flag is obtained.  
  <img width="409" alt="image" src="https://github.com/user-attachments/assets/73f7a061-9eb0-44a7-b47d-63af4c168e91">    
  Flag Obtained- **pwn.college{oUK8pxFqquUkXyjEnwycekfx8Qr.dNzM4QDL0YTN0czW}**




  


  

  




  
