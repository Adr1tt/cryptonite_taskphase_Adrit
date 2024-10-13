# Processes and Jobs
Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college
## Listing Processes
- Learnt the `ps` command which stands for "Process Snapshot" or "process status" and also learnt about Standard syntax arguements like -e, -f and -ef, and the BSD syntax arguements like a, u, x and aux.
- Started the challenge and used `ps -ef` to list all processes running. Then, I saw "/challenge/18491-run-9761" in the list and entered `/challenge/18491-run-9761` into the terminal prompt to obtain the flag-  
  <img width="985" alt="image" src="https://github.com/user-attachments/assets/a4869630-6369-48a4-87c3-e703416c2e76">  
  Flag Obtained- **pwn.college{gCv9SJaxOACsV3Mupt0maVfsBZn.dhzM4QDL0YTN0czW}**
## Killing Processes
- Learnt how to terminate processes using the `kill` command and passing the PID(Process ID) as it's arguement.
- Started the challenge and used `ps -ef| grep dont_run` to finnd the PID of the process:-"/challenge/dont_run" and then used `kill` to terminate it. Then, I used `/challenge/run` to obtain the flag-  
  <img width="552" alt="image" src="https://github.com/user-attachments/assets/8680c89a-0eba-4f80-afaf-5d112f817ab2">  
  Flag Obtained- **pwn.college{8u9w0VEwchcrsDKMx9bupthuS6I.dJDN4QDL0YTN0czW}**
## Interrupting Processes
- Learnt that terminals have a hotkey for interrupting processes- Ctrl-C (e.g., holding down the Ctrl key and pressing C) sends an "interrupt" to whatever application is waiting on input from the terminal and, typically, this causes the application to cleanly exit.
- Started the challenge and used `/challenge/run` and then pressed Ctrl+C to interrupt the process and obtain the flag-  
  <img width="551" alt="image" src="https://github.com/user-attachments/assets/554268a7-363e-4428-95a4-ef6d7adc8cf4">  
  Flag Obtained- **pwn.college{k2CwohaXYUHHeNn9_kr-HdlbchI.dNDN4QDL0YTN0czW}**
## Suspending Processes
- Learnt that we can suspend processes to the background with Ctrl-Z.
- Started the challenge and used `/challenge/run`, then used Ctrl+Z to suspend the process and then again used `/challenge/run` to obtain the flag-  
  <img width="540" alt="image" src="https://github.com/user-attachments/assets/e41c9cda-404e-402b-bab0-28cc654ad942">  
  Flag Obtained- **pwn.college{8LZtJOcSwnwk4BD2smpHeEoPBq1.dVDN4QDL0YTN0czW}**
## Resuming Processes
- Learnt that we can resume processes(in the foreground) by using the `fg` command.
- Started the challenge and used `/challenge/run` to initiate the process and then used Ctrl+Z to suspend it. Now, I entered `fg` into the terminal prompt to resume the process and obtain the flag-  
  <img width="553" alt="image" src="https://github.com/user-attachments/assets/fd09b0a7-c2da-498a-921e-ebc31d1d3b52">  
  Flag Obtained- **pwn.college{0Dxri4xLw6_3DsE0GqCfopWj2T1.dZDN4QDL0YTN0czW}**
## Backgrounding Processes
- Understood the `bg` command which can resume processes in the background.
- Started the challenge and used `/challenge/run` to initiate the process and then used Ctrl+Z to suspend it. Now, I entered `bg` into the terminal prompt to resume the process in the background. I had to use `/challenge/run` again to obtain the flag-  
  <img width="567" alt="image" src="https://github.com/user-attachments/assets/e4f2e9a0-3e9d-4ef2-870f-f26d2f3ace03">  
  Flag Obtained- **pwn.college{ouRuZKwgHXABsclQxhaiWOegWjS.ddDN4QDL0YTN0czW}**
## Foregrounding Processes
- Learnt that we can foreground a backgrounded process using `fg`.
- Started the challenge and used `/challenge/run` and then used Ctrl+Z to suspend it and `bg` to background it. Finally I used `fg` to foreground the process and hit enter to obtain the flag-  
  <img width="567" alt="image" src="https://github.com/user-attachments/assets/2749909f-d768-4788-add4-a6f8b11755e6">  
  Flag Obtained- **pwn.college{w4-lGVlz7Nyx4h2nrzcn_BKIIUA.dhDN4QDL0YTN0czW}**
## Starting Backgrouded Processes
- Learnt that we can directly start backgrounded processes by using appending a "&" to the command.
- Started the challenge and used `/challenge/run &` to start the "/challenge/run" process in the background and thus obtained the flag-  
  ![image](https://github.com/user-attachments/assets/8f73801a-d8a5-4559-96ac-2db20de4dfce)  
  Flag Obtained- **pwn.college{EHucP50-KSHZURaw6tApvyvgqgI.dlDN4QDL0YTN0czW}**
## Process Exit Codes
- Learnt that every shell command, including every program and every builtin, exits with an exit code when it finishes running and terminates which can be used by the shell, or the user of the shell (that's you!) to check if the process succeeded in its functionality.
- Also learnt that we can access the exit code of the most recently-terminated command using the special "?" variable.
- Also learnt that commands that succeed typically return 0 and commands that fail typically return a non-zero value, most commonly 1 but sometimes an error code that identifies a specific failure mode.
- Started the challenge and used `/challenge/get-code` which exited with an error code and then used `echo $?` to get that code and finally used `/challenge/submit-code 89` (where 89 was the error code) to obtain the flag-  
  <img width="452" alt="image" src="https://github.com/user-attachments/assets/a8eadde6-3b34-44d1-9cdf-28cd8fdf1653">  
  Flag Obtained- **pwn.college{0dHGvFynW-bD4slrdMG5HFrLn_e.dljN4UDL0YTN0czW}**










