# Chaining Commands
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college
## Chaining with Semicolons
- Learnt that we can use ";" to chain commands. In most contexts, ";" separates commands in a similar way to how Enter separates lines.
- Also learnt when we hit Enter, our shell executes our typed command and, after that command terminates, it gives us the prompt to input another command. The semicolon is analogous, just without the prompt and with us entering both commands before anything is executed.
- Started the challenge and used `/challenge/pwn; /challenge/college` to obtain the flag-  
  <img width="554" alt="image" src="https://github.com/user-attachments/assets/9a88b694-413a-49d2-bf4f-94b38ce422b0">  
  Flag Obtained- **pwn.college{A6z7VPl9UCoYAewHl11SMepgOyb.dVTN4QDL0YTN0czW}**
## Your First Shell Script
- Learnt that a "shell script" is a file in which we can put commands in, and we can run those commands by executing the file
