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


