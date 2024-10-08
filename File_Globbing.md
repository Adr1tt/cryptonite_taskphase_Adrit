# File Globbing
- Used the `ssh -i ./key hacker@dojo.pwn.college` command in the terminal to establish connection between the terminal and pwn.college
- Learnt that "Glob" is the common name for a set of Bash features that match or expand specific types of patterns.
## Matching with *
- Learnt that when the shell encounters a * character in any argument, it will treat it as a wildcard and try to replace that argument with any files that match the pattern.
- Also learnt that the * matches any part of the filename except for "/" or a leading "." character.
- Started the challenge and used `cd /ch*` to change my cwd to the "challenge" directory and used `/challenge/run` to obtain the flag-
  <img width="554" alt="image" src="https://github.com/user-attachments/assets/424cc5a2-1493-498b-9441-2b4485362bc2">  
  Flag Obtained- **pwn.college{gtvLvuKjwaBDy9WfJ05RpJMuLs4.dFjM4QDL0YTN0czW}**
## Matching with ?
- Learnt that when the shell encounters a "?" character in any argument, the shell will treat it as single-character wildcard.
- Started the challenge and used `cd /?ha??enge` to change my cwd to the "challenge" directory and used `/challenge/run` to obtain the flag-
  <img width="554" alt="image" src="https://github.com/user-attachments/assets/ebcadf2c-aed8-4be3-ad72-0cb350c24862">  
  Flag Obtained- **pwn.college{MrVduNfyLPjUE3LsiNaAXeEtEmu.dJjM4QDL0YTN0czW}**
## Matching with []
- Learnt that the square brackes are, essentially, a limited form of ?, in that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets.
- Started the challenge and used `cd /challenge/files` to change directories and then entered `/challenge/run file_[bash]` into the terminal prompt as instructed and obtained the flag-
  <img width="531" alt="image" src="https://github.com/user-attachments/assets/268d8ac4-7bf2-4936-961f-62f20f8687f6">  
  Flag Obtained- **pwn.college{Udx2p7ZsUb4kFC9-jhtzZ12kdmx.dNjM4QDL0YTN0czW}**
## Matching paths with []
- Understood that globbing happens on a path basis, so you can expand entire paths with your globbed arguments.
- Started the challenge and as per the instructions given in the challenge description I used `/challenge/run /challenge/files/file_[bash]` to obtain the flag at once-
  <img width="587" alt="image" src="https://github.com/user-attachments/assets/ee0374f8-253f-4b31-bcf7-b9d51ee4f2da">  
  Flag Obtained- **pwn.college{kEyS0kRnjtyNgh0_Y00tsPymTtk.dRjM4QDLOYTN0czW}**
## Mixing globs
- Started the challenge and used `cd /challenge/files` to change directories and then used `ls` to see all the files in my cwd.
- Then according to the instructions in the challenge description I used `/challenge/run [cep]*` to match the files named "challenging", "educational" and "pwning" and thus obtained the flag-
  <img width="574" alt="image" src="https://github.com/user-attachments/assets/fc59568f-6e28-4963-9ba2-5238f82c13eb">  
  Flag Obtained- **pwn.college{kzdnjRAxw6hy7LiHIgQf5GoAWRJ.dVjM4QDLOYTN0czW}**
## Exclusionary globbing
- Learnt that if the first character in the brackets([]) is "!" or "^" (in newer versions of bash), the glob inverts, and that bracket instance matches characters that aren't listed.
- Also learnt that "!" has a different special meaning in bash when it's not the first character of a [] glob, but ^ does not have this problem, but is also not compatible with older shells.
- Started the challenge and used `cd /challenge/files` to change directories.
- Then, according to the given instructions in the challenge I used `/challenge/run [!pwn]*`, where [!pwn]* matches the files which don't start with p,w or n and thus obtained the flag-
  <img width="551" alt="image" src="https://github.com/user-attachments/assets/b67b86b9-2b71-4032-ab07-2980aace33ad">  
  Flag Obtained- **pwn.college{IJ2ly4QrIrwz0rwOLYPw_NJxMVZ.dZjM4QDL0YTN0czW}**


  
