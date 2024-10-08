# Digesting Documentation
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college  
## Learning From Documentation
- Started the challenge and entered `/challenge/challenge --giveflag` into the terminal prompt to obtain the flag-
  <img width="519" alt="image" src="https://github.com/user-attachments/assets/2b39f354-990e-42d8-8026-c179aa885c9e">  
  FLag Obtained- **pwn.college{4IDjHTrm7koCX_4-9OcscuH7WsK.dRjM5QDL0YTN0czW}**
## Learning Complex Usage
- Understood that many commands take complex arguements and some commands' arguements take arguements like `find`.
- Started the challenge and entered `/challenge/challenge --printfile /flag` as I wanted to print the "flag" file and thus obtained the flag-  
  <img width="531" alt="image" src="https://github.com/user-attachments/assets/0b1a0270-a4ea-475c-afde-b332cbaabb73">  
  Flag Obtained- **pwn.college{wT-5N0L4-J4ksuODLYwWU72_cEY.dVjM5QDL0YTN0czW}**
## Reading Manuals
- Learnt the `man` command which is short for `manual` and that we can hit 'q' to exit the manpage.
- Started the challenge and used `man challenge` for printing the manual of the `challenge` command and hit q after reading the manual.
  <img width="552" alt="image" src="https://github.com/user-attachments/assets/8211b272-ed53-47c1-bd53-edddba50fe61">  
- Then, I entered `/challenge/challenge --ppruyy 409` into the terminal and obtained the flag-  
  ![image](https://github.com/user-attachments/assets/62d6042f-3fcb-4e48-b4cb-aa2a49af12b9)  
  Flag Obtained- **pwn.college{4pUprBuyZySiuZVGu09TBbSo9LM.dRTM4QDL0YTN0czW}**
## Searching Manuals
- Learnt about searching manuals by the use of "/", "n", "N" and "?".
- Started the challenge and used `man challenge` to see the manual of the `challenge` command. Then I used `/` to search "flag" and used "n" to scroll down and found this-
  ![image](https://github.com/user-attachments/assets/9134043c-b612-4e58-acbc-202031e5201a)  
- Then I pressed "q" to to quit and then entered `/challenge/challenge --ce` to obtain the flag-  
  <img width="586" alt="image" src="https://github.com/user-attachments/assets/fc8d5dd8-2f86-4ba0-8d06-9d2f09a7790e">  
  Flag Obtained- **pwn.college{QX-JxzgkB080VnAAHpj73BV0LQW.dVTM4QDL0YTN0czW}**
## Searching For Manuals
- Understood the use of `man man`.
- Started the challenge and entered `man man` into the terminal which outputted a large manual page and I pressed space which revealed more contents of the manual page.
  <img width="990" alt="image" src="https://github.com/user-attachments/assets/55ecc563-1fc0-4819-bdd5-3b92dae6c445">  
- After seeing the above command I pressed "q" and entered `man -k` into the terminal which was a wrong use of the `man` command, but then I entered `man -k flag` which told me about a command `wpreagveds` which prints the flag
  <img width="1255" alt="image" src="https://github.com/user-attachments/assets/dafaff3e-29d9-44a4-bb33-3dcc4d88191e">  
- Now, I entered `/challenge/challenge --wpreag 214` in the terminal to obtain the flag-  
  <img width="603" alt="image" src="https://github.com/user-attachments/assets/a8911ece-0ac8-4c56-8806-9de149728242">  
  Flag Obtained- **pwn.college{wRSBpKr_UBDLeU2AagvMeUds1fl.dZTM4QDL0YTN0czW}**
## Helpful programs
- Learnt that some programs don't have a man page, but arguments like --help or -h and in rare cases, -?, help, /? might tell us how to run the command/program.
- Started the challenge and used `/challenge/challenge --help` which told me how to use the command along with other arguements-  
  <img width="638" alt="image" src="https://github.com/user-attachments/assets/5fbfacbb-610d-4aee-b4ce-7f9428eaace4">  
- Then I used `/challenge/challenge -p` to find the secret value which was 984 and then I obtained the flag using `/challenge/challenge -g 984`-  
  <img width="588" alt="image" src="https://github.com/user-attachments/assets/fae40a35-778a-40f7-b21a-ae67ff079665">  
  Flag Obtained- **pwn.college{IGdutnV9awtUuKjcgKS8tLM_K_T.ddjM4QDL0YTN0czW}**
## Help for Builtins
- Learnt that we can get a list of shell builtins by using `help` and we can also get help on a specific builtin by passing it as an arguement.
- Started the challenge and used `help challenge` to understand the use of the builtin called "challenge"  
  <img width="531" alt="image" src="https://github.com/user-attachments/assets/884a282a-79ef-404f-be8d-9afb1fd68372">  
- Then I used `challenge --secret ImRWlHgK` to obtain the flag-  
  <img width="426" alt="image" src="https://github.com/user-attachments/assets/74cdefa6-785a-4101-8aa3-ed74c3961d92">  
  Flag obtained- **pwn.college{ImRWlHgKPlA89zI8nZZVcaoncT_.dRTM5QDL0YTN0czW}**








  


  


  
