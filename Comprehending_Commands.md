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
## 

  
