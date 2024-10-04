# Comprehending Commands
Used the ssh -i ./key hacker@dojo.pwn.college command in the terminal to establish connection between the terminal and pwn.college
## cat: not the pet, but the command!
- Learnt the `cat` command which is used for reading out files and it can concatenate multiple files if multiple arguments are provided.
- Started the challenge and entered `cat flag` in the terminal prompt to read out the contents of the flag file, thus obtaining the flag
  ![image](https://github.com/user-attachments/assets/1db03e24-8215-4890-bb18-96159dfbb49d)  
  Flag Obtained- **pwn. collegefQQ8pB_-WU8zzXXHNF5JWyhk2B1G. dFzN1QDL®YTN0czW}**
## catting absolute paths
- Understood that we can specify cat's arguements as absolute paths.
- Started the challenge and entered `cat /flag` in the terminal prompt where /flag is the absolute path and thus obtained the flag
  <img width="404" alt="image" src="https://github.com/user-attachments/assets/75124c35-1366-41ea-b5b2-3929fef92760">  
  Flag Obtained- **pwn.college{A4xKFhxmb6Wig-brWszjleTNaQS.dlTM5QDL0YTN0czW}**
## more catting practice
- On starting the challenge the absolute path of the flag containing file was shown.
- I used `cat /usr/lib/php/flag` to read out the contents of the flag file thus obtaining the flag
  <img width="543" alt="image" src="https://github.com/user-attachments/assets/454a36ce-fa7d-4190-b987-27a1897ad779">  
  Flag Obtained- **pwn.college{AUZ4xEJsVl6NlbVwYAxnfwri8Oa.dBjM5QDL0YTN0czW}**
## grepping for a needle in a haystack
- Learnt the `grep` command and that it can be used for searching a file for lines of text containing a specific sequence of characters(string).
- Started the challenge and entered `grep pwn.college /challenge/data.txt` where "pwn.college" is the arguement since flags start with "pwn.college" and this obtained the flag  
  <img width="639" alt="image" src="https://github.com/user-attachments/assets/4c85cfea-def5-4e69-a186-96d19dc97c49">  
  Flag Obtained- **pwn.college{E6uCKutXNvpcn9OvxMpaRy-djks.ddTM4QDL0YTN0czW}**
## listing files
- Learnt the `ls` command and that it will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided.
- Started the challenge and entered `cd /challenge` into the terminal prompt to change the directory and then used `ls` to list the files in the current directory.
- Two files showed up, then I used `./32713-renamed-run-12966` to run the file named "32713-renamed-run-12966" and thus obtained the flag  
  ![image](https://github.com/user-attachments/assets/1fd4961a-f042-4cc4-a36f-2da54a60569a)  
  Flag Obtained- **pwn.college{kcQHxwVf2Y7ICgTv57V_KpUCT03.dhiM4QDL0YTN0czW}**
## touching files
- Learnt that we can create a new, blank file by touching it with the `touch` command.
- Started the challenge and entered `cd /tmp` into the terminal prompt and used `touch pwn` and `touch college` to create 2 files.
- Then used `ls` to check the created files and used `/challenge/run` to obtain the flag.
  ![image](https://github.com/user-attachments/assets/d3c991f0-b0fa-4b46-80cb-ce0acdc5c109)  
  Flag Obtained- **pwn.college{MVy7CeirXECPKU-qPEEHUofo56. dBzM4QDL0YTN0czW}**
## removing files
- Learnt the `rm` command which is used to remove files.
- Started the challenge and entered `ls` which showed 2 files and one of them is "delete_me".
- Then I entered `rm delete_me` to remove that file and then entered `/challenge/run` to obtain the flag.  
  <img width="405" alt="image" src="https://github.com/user-attachments/assets/faa584fc-5bdf-4ddb-abfa-b5f4401fdf00">
  Flag Obtained- **pwn.college{EkpSn33bcYZAh4Epam6uwCWpm1Y.dZTOwUDL0YTN0czW}**
## hidden files
- Understood that Linux has a convention where files that start with a . don't show up by default in `ls` and we need to use `ls -a` to view them.
- Started the challenge and used `cd /` to change the directory(to /) and then used `ls -a` to show the hidden files.
- A file named ".flag-296222717518961" was shown and I used `cat .flag-296222717518961` to display its contents and thus obtained the flag  
  <img width="454" alt="image" src="https://github.com/user-attachments/assets/d3ef39e2-5926-4a35-bb03-93cc930959ff">  
  Flag Obtained- **pwn.college{gjV9KEtTZdCcRG-VsMA3XU_Df-D.dBTN4QDL0YTN0czW}**
## An Epic Filesystem Quest
- 





  
