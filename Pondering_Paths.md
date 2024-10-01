# Pondering Paths  
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)  

## The Root
- Understood the concept of tree filesystem(starting at /) and directories
- Started the challenge and entered `/pwn` in the terminal prompt to get the flag
  
  Flag Obtained- **pwn.college{oZPKIsYpmmn_gh0a3mq58cE2U_V.dhzN5QDL0YTN0czW}**
  ![image](https://github.com/user-attachments/assets/b2d4d97b-bae9-44b0-bdd5-389b5cacc9f8)

## Program and absolute paths
- In this challenge we had to execute the **run** file which is said to be in the **challenge** directory which is in the root dictonary(/)
- Started the challenge and entered `/challenge/run` in the terminal prompt to get the flag

  Flag Obtained- **pwn.college{AjBIcf8QMReH_phm7wKT7vO4eO_.dVDN1QDL0YTN0czW}**
  ![image](https://github.com/user-attachments/assets/002d2136-c741-43b3-ba6d-f8087b1c109f)
## Position thy self
- Understood that we can navigate around directories by using the cd (change directory) command and passing a path to it as an argument.
- Started the challenge and entered `cd /` in the terminal prompt because "hacker@paths~position-thy-self:~$" is mentioned in the prompt, therefore I tried changing the directory to the root directory, used `/challenge/run` and obtained the flag.

  Flag Obtained- **pwn.college{cH8dQn4Z6VM9HANjX7A6Cdm1fpS.dZDN1QDL0YTN0czW}**
  ![image](https://github.com/user-attachments/assets/b006b87d-de29-44a1-abf4-767ed6247a3e)
## Position elsewhere
- Started the challenge and used `/challenge/run` and the following output is shown in the terminal-
  ![image](https://github.com/user-attachments/assets/d58545c5-0222-40c8-b960-88303b115116)
  
- Entered `cd /usr/aarch64-linux-gnu/include/gnu` to change the directory and used `/challenge/run` to obtain the flag
  ![image](https://github.com/user-attachments/assets/c0020f50-393b-4f71-80c6-f1c4b3100ecc)
  ![image](https://github.com/user-attachments/assets/9789a679-81e5-4976-85eb-b3cb65288793)
  Flag Obtained- **pwn.college{EXuxMbkxlJfINaUQvAE8_aRwDdW.ddDN1QDL0YTN0czW}**

  

  




  
