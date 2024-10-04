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
(This was a long one)
- Started the challenge and as instructed I used `cd /` and then `ls` to list files in the "/" directory.
- The following showed up in the terminal-
  <img width="418" alt="image" src="https://github.com/user-attachments/assets/985dbda4-155a-4cd0-89fa-aa24778eaeef">  
- So I used `cat INFO` to read out the contents of the file "INFO" and the following showed up in the terminal-
  <img width="1007" alt="image" src="https://github.com/user-attachments/assets/83b60382-ce19-4992-bdc8-3b4a588c96e7">  
- So then I entered `ls /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Termes/Size1` in the terminal and 2 files were showed and one of them was "README-TRAPPED" so then, I used `cat /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/Gyre-Termes/Size1/README-TRAPPED` to reveal it's contents and this showed up-
  <img width="1020" alt="image" src="https://github.com/user-attachments/assets/323ef400-9f49-48df-b2ed-5566e70b3f36">  
- Then I used `ls /usr/share/autoconf/autotest -a` to reveal the hidden files and a file named ".TIP" came up. Then, I used `cat /usr/share/autoconf/autotest/.TIP` which revealed the next clue
  <img width="578" alt="image" src="https://github.com/user-attachments/assets/b9336c31-e644-4355-9da0-b03b4aae8fb0">  
- Thus, I then entered `ls /opt/linux/linux-5.4/arch/parisc/kernel` in the terminal and many files came up, out of which I used the `cat` command on two files, first was a file named "Makefile" which revealed contents of no use and then I used the `cat` command on a file named "TRACE" which revealed the next clue-
  <img width="1873" alt="image" src="https://github.com/user-attachments/assets/88e65449-b596-4657-87a7-ca0f75e09a05">  
- Then I used `ls /usr/local/lib/python3.8/dist-packages/sympy/strategies/branch/tests` which revealed files and one of them was named "EVIDENCE", so I used `cat /usr/local/lib/python3.8/dist-packages/sympy/strategies/branch/tests/EVIDENCE` to reveal its contents and found the next clue
  <img width="886" alt="image" src="https://github.com/user-attachments/assets/8c0d955c-ba87-4b87-b634-27124bd99da0">  
- Therefore, I used `cd /opt/linux/linux-5.4/drivers/staging/uwb` and then used the `ls` command to list it's files and alot of files showed up and one of them was named "BLUEPRINT" and I used `cd BLUEPRINT` to output it's contents and found the next clue-
  <img width="1234" alt="image" src="https://github.com/user-attachments/assets/78360633-5a9b-49d6-8fa4-1c576fec96a6">  
- Now, I used `ls /opt/linux/linux-5.4/arch/nios2/include/uapi -a` and a file named ".MESSAGE" showed up on which I used the `cat` command to find the next clue-
  <img width="1010" alt="image" src="https://github.com/user-attachments/assets/0cf8e650-fb20-42c9-a722-f0822c5be01c">  
- Now, I used `ls /opt/pt-dump/.git/logs/refs` which revealed multiple files out of which there was a file named "INSIGHT-TRAPPED". Thus I used `cat /opt/pt-dump/.git/logs/refs/INSIGHT-TRAPPED` and found the next clue-


  



  








  
