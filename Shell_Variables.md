# Shell Variables
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college
## Printing Variables
- Learnt how to use variables with echo command(prepending the variable name with a $).
- Started the challenge and used `echo $FLAG` to obtain the flag-  
  <img width="402" alt="image" src="https://github.com/user-attachments/assets/a11dd144-a0ba-4c1e-aaaf-9527173e67dc">  
  Flag Obtained- **pwn.college{Uqe2d6ZzchKeyWB-O4Du4B5tveY.ddTN1QDL0YTN0czW}**
## Setting Variables
- Learnt how to assign values to variables(using "=").
- Started the challenge and entered `PWN=COLLEGE` into the terminal prompt as per the given instructions and obtained the flag-  
  <img width="484" alt="image" src="https://github.com/user-attachments/assets/185086e6-4196-4f53-bedc-78db0080aebc">  
  Flag Obtained- **pwn.college{gUhOpP-qhliYeM3BTPS2R8SfLKF.dlTN1QDL0YTN0czW}**
## Multi-word Variables
- Learnt about quoting("") which helps the shell in reading multi-word variables as a single token.
- Started the challenge and entered `PWN="COLLEGE YEAH"` into the terminal prompt as per the given instructions and obtained the flag-  
  <img width="486" alt="image" src="https://github.com/user-attachments/assets/bcc63b36-a475-467a-a11d-3e20e7eb7917">  
  Flag Obtained- **pwn.college{AiofBiChg1143hYqyFjOw2JDWdX.dBjN1QDL0YTN0czW}**
## Exporting Variables
- Learnt that by default the variables we set in a shell session are local to that shell process. That is, other commands that we run won't inherit them.
- Also learnt that `sh` invokes a minimal shell implementation as a child of the main shell process.
- Started the challenge and used `PWN=COLLEGE` and then `COLLEGE=PWN` to assign values to the 2 variables and then exported PWN by using `export PWN` and then used `/challenge/run $PWN` to obtain the flag-  
  ![image](https://github.com/user-attachments/assets/9455e085-615c-4b9e-8722-729ce7bf6f07)  
  Flag Obtained- **pwn.college{oUIHTRk8WDke79eBxeE8MqhM7F1.dJjN1QDL0YTN0czW}**
## Printing Exported Variables
- Learnt about the `env` command whihc prints out every exported variable set in the shell.
- Started the challenge and entered `env` into the terminal prompt. In the output there was the "FLAG" variable and the flag was written beside it.  
  <img width="569" alt="image" src="https://github.com/user-attachments/assets/f9335b08-77a8-4fec-bd97-6e722204b574">  
  Flag Obtained- **pwn.college{ITcGgFpR03HcQDF2ty0qCD5Ff7i.dhTN1QDL0YTN0czW}**
## Storing Command Output
- Learnt about command substitution using $().
- Started the challenge and used `PWN=$(/challenge/run)` to store the flag in the variable "PWN" and then used `echo $PWN` to obtain the flag-  
  <img width="560" alt="image" src="https://github.com/user-attachments/assets/abdafa17-d9fc-4adb-98aa-c9529f89f460">  
  Flag Obtained- **pwn.college{48kUjayRkQt-2p8HLeBA1n5uWok.dVzN0UDL0YTN0czW}**
- Resources- https://www.gnu.org/software/bash/manual/html_node/Command-Substitution.html
## Reading Input
- Learnt the `read` command which is used for taking user input and the -p arguement for prompts.
- Started the challenge and used `read PWN` and entered "COLLEGE" into the terminal prompt to obtain the flag-  
  <img width="484" alt="image" src="https://github.com/user-attachments/assets/b6c11a55-93c4-4662-b03f-1a742c9a43b8">  
  Flag Obtained- **pwn.college{4Wc4-YA-sTcN1LxbQkC5TeyWgID.dhzN1QDL0YTN0czW}**
## Reading files
- Learnt how to read a file into an environment variable.
- Started the challenge and used `read PWN < /challenge/read_me` to read "/challenge/read_me" into the "PWN" environment variable and thus obtained the flag-  
  <img width="484" alt="image" src="https://github.com/user-attachments/assets/449595ce-daec-4e6f-97d0-f306dc0d805f">  
  Flag Obtained- **pwn.college{YU1mcK16fDve6YrV3J_3mCGTFe2.dBjM4QDL0YTN0czW}**





