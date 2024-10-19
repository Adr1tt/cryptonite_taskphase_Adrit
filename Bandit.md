# Bandit-(https://overthewire.org/wargames/)
# Level 0
- Used `ssh bandit0@bandit.labs.overthewire.org -p 2220` and then entered the password:"bandit0"
### Terminal
  ```bash
  adrit@Adrits-MacBook-Air ~ % ssh bandit0@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit0@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!
  ```
# Level 0 → Level 1
- Used `ls` and then used `cat readme` to get the password.
### Terminal
  ```bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

  ```
- Then used `ssh bandit1@bandit.labs.overthewire.org -p 2220` to log into bandit1 and used the password obtained level.
# Level 1 → Level 2
- Used `ls` and then used `cat ./-` to get the password.
### Terminal
  ```bash
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
  ```
### References
- https://stackoverflow.com/questions/42187323/how-to-open-a-dashed-filename-using-terminal
- https://linux.die.net/abs-guide/special-chars.html
# Level 2 → Level 3
- Used `ssh bandit2@bandit.labs.overthewire.org -p 2220` to log into bandit2 and used the password obtained in the previous level.
- Then I used `ls` and then `cat "spaces in this filename"` to obtain the password.
### Terminal
  ```bash
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename"
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
  ```
### References 
- https://linuxhandbook.com/filename-spaces-linux/
# Level 3 → Level 4
- Used `ssh bandit3@bandit.labs.overthewire.org -p 2220` to log into bandit3 and used the password obtained in the previous level.
- Used `ls` then used `cd inhere` and then used `ls -a` to find the hidden file and finally used `cat ...Hiding-From-You` to obtain the password
### Terminal
  ```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```
# Level 4 → Level 5
- Used `ssh bandit4@bandit.labs.overthewire.org -p 2220` to log into bandit4 and used the password obtained in the previous level.
- Used `cd inhere` to change directories then used `ind . -type f ! -executable -exec file {} + | grep 'ASCII text'` to find the human readable files and then used `cat <-file07` to obtain the password
### Terminal
  ```bash
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ find . -type f ! -executable -exec file {} + | grep 'ASCII text'
./-file07: ASCII text
bandit4@bandit:~/inhere$ cat <-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```
### References
- https://www.unix.com/unix-for-dummies-questions-and-answers/11998-how-cat-file-name-starts.html
- https://unix.stackexchange.com/questions/313442/find-human-readable-files
# Level 5 → Level 6
- Used `ssh bandit5@bandit.labs.overthewire.org -p 2220` to log into bandit5 and used the password obtained in the previous level.
- Used `cd inhere`, then used `find . -type f -size 1033c ! -executable -exec file {} + | grep 'ASCII text'` which gave me the file path and then used `cat` to obtain it.
### Terminal
 ```bash
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable -exec file {} + | grep 'ASCII text'
./maybehere07/.file2: ASCII text, with very long lines (1000)
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

  
