# Chaining Commands
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college
## Chaining with Semicolons
- Learnt that we can use ";" to chain commands. In most contexts, ";" separates commands in a similar way to how Enter separates lines.
- Also learnt when we hit Enter, our shell executes our typed command and, after that command terminates, it gives us the prompt to input another command. The semicolon is analogous, just without the prompt and with us entering both commands before anything is executed.
- Started the challenge and used `/challenge/pwn; /challenge/college` to obtain the flag-  
  <img width="554" alt="image" src="https://github.com/user-attachments/assets/9a88b694-413a-49d2-bf4f-94b38ce422b0">  
  Flag Obtained- **pwn.college{A6z7VPl9UCoYAewHl11SMepgOyb.dVTN4QDL0YTN0czW}**
## Your First Shell Script
- Learnt that a "shell script" is a file in which we can put commands in, and we can run those commands by executing the file.
- Since I didn't properly understand the usage of a shell script, I surfed the web trying to understand it. Here are the resources-
  - https://www.freecodecamp.org/news/shell-scripting-crash-course-how-to-write-bash-scripts-in-linux/
  - https://www.geeksforgeeks.org/introduction-linux-shell-shell-scripting/
  - https://www.tutorialspoint.com/unix/shell_scripting.htm
- Thus, I learnt the `nano` command.
- Started the challenge and used `touch x.sh` to create the shell script.
- Then used `ls -l x.sh` to see it's permissions and used `chmod u+rwx` to change permissions and used `nano x.sh` to open the editor where I saved the commmands "/challenge/pwn; /challenge/college" and used Ctrl+O to save and Ctrl+X to exit  
  <img width="427" alt="image" src="https://github.com/user-attachments/assets/9b055925-eb23-4be6-9c1d-30fa7a97630e">  
- Then I ran the shell script using `bash x.sh` and obtained the flag-  
  <img width="480" alt="image" src="https://github.com/user-attachments/assets/4515f173-a5ec-49fb-9407-990a01b93f99">  
  Flag Obtained- **pwn.college{IbUlDdKwrzUoSma0a_xO4XpKgei.dFzN4QDL0YTN0czW}**
## Redirecting Script Output
- Learnt how to redirect script output.
- Started the challenge and used bash `x.sh | /challenge/solve`, as I had already written the commands required in "x.sh" in the previous challenge, and thus obtained the flag-  
  <img width="520" alt="image" src="https://github.com/user-attachments/assets/2b38a514-0fde-437b-a466-5dc46c74f4ee">  
  Flag Obtained- **pwn.college{MKyvO7sF5dUMI2q-CrSh-4y7uAm.dhTM5QDL0YTN0czW}**
## Executable Shell Scripts
- Learnt that if a shell script is executable then we can run it without calling `bash` and by using its relative/absolute path directly.
- Started the challenge and used `touch script.sh` to create a shell script then used `chmod u+rwx script.sh` to change it's permissions and used `nano script.sh` to edit it's contents and write "/challenge/solve" in it. Then I used `./script.sh` to run the shell script and obtained the flag-  
  <img width="460" alt="image" src="https://github.com/user-attachments/assets/166cffbe-d271-4ebb-b65f-5b144f2892f6">  
  Flag Obtained- **pwn.college{Qo_i4_DLv06Jca0uE6mOeEzra9Y.dRzNyUDL0YTN0czW}**




    
