# Pondering PATH
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college
## The PATH Variable
- Learnt that there is a special shell variable, called PATH, that stores a bunch of directory paths in which the shell will search for programs corresponding to commands. If we blank out the variable, bash cannot find the ls command.
- Started the challenge and entered `PATH=""` into the terminal prompt to blank out the variable and then used `/challenge/run` which couldn't access the `rm` command and gave me the flag-  
  <img width="405" alt="image" src="https://github.com/user-attachments/assets/68ae9ead-be3f-4224-866d-2d305fedb8fb">
  Flag Obtained- **pwn.college{U6nO2i5u9qqNJ6E4vDR2wH5NVkl.dZzNwUDL0YTN0czW}**
## Setting PATH
- Learnt that by adding directories to or replacing directories in the PATH variable, we can expose programs to be launched using their bare name which exist only in that directory.
- Started the challenge and entered `PATH=/challenge/more_commands/` into the terminal prompt (as the `win` command exists in /challenge/more_commands/) and then used `/challenge/run` which invoked the `win` command by it's bare name and thus I obtained the flag-  
  <img width="462" alt="image" src="https://github.com/user-attachments/assets/b939cca2-66f6-48d4-bc04-d53394eb3170">  
  Flag Obtained- **pwn.college{YocLk9ILPadNfzjY9C79NklfshU.dVzNyUDL0YTN0czW}**
## Adding Commands
- Learnt the `export` command, which if used like this- `export PATH=/home/hacker:$PATH` adds the directory "/home/hacker" to PATH without removing its previous directories.
- Started the challenge and used `touch win` to create the file, then used `chmod ugo=rwx win` to change permissions and used `nano win` and wrote "cat /flag" in it's contents.
- Then I used `export PATH=/home/hacker:$PATH` to appent the "home/hacker directory" to the PATH variable since it contained "win", and then used `echo $PATH` just to make sure that the directory was added.
- Finally I used `/challenge/run` to obtain the flag-  
  <img width="783" alt="image" src="https://github.com/user-attachments/assets/6f3f5863-f03c-40ea-9dcb-1fffc0d212d3">  
  Flag Obtained- **pwn.college{UiUjt90-3VtqcrhY39Mb9neXlcX.dZzNyUDL0YTN0czW}**
## Hijacking Commands
- Started the challenge and used `touch rm` to create a fake rm file in my current working directory "/home/hacker", then used `chmod ugo=rwx` to change permissions.
- Then I used `nano rm` and wrote "/bin/cat /flag" in it's contents so that it gives us the flag.
- Then I used `export PATH=/home/hacker:$PATH` to add my current working directory to the PATH variable so that when I use `/challenge/run` it accesses the fake rm file.
- Then used `/challenge/run` to obtain the flag-  
  <img width="459" alt="image" src="https://github.com/user-attachments/assets/31156fa3-87dc-4e59-9144-e79210a10b8f">  
  Flag Obtained- **pwn.college{0qhNeHUCL-2RBo_fEPnmQFaU3Yp.ddzNyUDL0YTN0czW}**


