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
# Level 6 → Level 7
- Used `ssh bandit6@bandit.labs.overthewire.org -p 2220` to log into bandit6 and used the password obtained in the previous level.
- Used `find / -user bandit7 -group bandit6 -size 33c` to search for the file which gave alot of files which I couldn't access but one of them was accessable-"/var/lib/dpkg/info/bandit7.password".
- Therefore I used `cat /var/lib/dpkg/info/bandit7.password` to obtain the password.
### Terminal
```bash
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c
find: ‘/drifter/drifter14_src/axTLS’: Permission denied
find: ‘/root’: Permission denied
find: ‘/snap’: Permission denied
find: ‘/tmp’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/3483373/task/3483373/fd/6’: No such file or directory
find: ‘/proc/3483373/task/3483373/fdinfo/6’: No such file or directory
find: ‘/proc/3483373/fd/5’: No such file or directory
find: ‘/proc/3483373/fdinfo/5’: No such file or directory
find: ‘/home/bandit31-git’: Permission denied
find: ‘/home/ubuntu’: Permission denied
find: ‘/home/bandit5/inhere’: Permission denied
find: ‘/home/bandit30-git’: Permission denied
find: ‘/home/drifter8/chroot’: Permission denied
find: ‘/home/drifter6/data’: Permission denied
find: ‘/home/bandit29-git’: Permission denied
find: ‘/home/bandit28-git’: Permission denied
find: ‘/home/bandit27-git’: Permission denied
find: ‘/lost+found’: Permission denied
find: ‘/etc/polkit-1/rules.d’: Permission denied
find: ‘/etc/multipath’: Permission denied
find: ‘/etc/stunnel’: Permission denied
find: ‘/etc/xinetd.d’: Permission denied
find: ‘/etc/credstore.encrypted’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/etc/sudoers.d’: Permission denied
find: ‘/etc/credstore’: Permission denied
find: ‘/dev/shm’: Permission denied
find: ‘/dev/mqueue’: Permission denied
find: ‘/var/log/amazon’: Permission denied
find: ‘/var/log/unattended-upgrades’: Permission denied
find: ‘/var/log/chrony’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/tmp’: Permission denied
find: ‘/var/spool/cron/crontabs’: Permission denied
find: ‘/var/spool/bandit24’: Permission denied
find: ‘/var/spool/rsyslog’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/pollinate’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/cache/apparmor/2425d902.0’: Permission denied
find: ‘/var/cache/apparmor/baad73a1.0’: Permission denied
find: ‘/var/lib/polkit-1’: Permission denied
find: ‘/var/lib/amazon’: Permission denied
/var/lib/dpkg/info/bandit7.password
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/chrony’: Permission denied
find: ‘/var/lib/snapd/void’: Permission denied
find: ‘/var/lib/snapd/cookie’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/ubuntu-advantage/apt-esm/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/update-notifier/package-data-downloads/partial’: Permission denied
find: ‘/var/lib/udisks2’: Permission denied
find: ‘/var/crash’: Permission denied
find: ‘/boot/efi’: Permission denied
find: ‘/boot/lost+found’: Permission denied
find: ‘/sys/kernel/tracing’: Permission denied
find: ‘/sys/kernel/debug’: Permission denied
find: ‘/sys/fs/pstore’: Permission denied
find: ‘/sys/fs/bpf’: Permission denied
find: ‘/run/lock/lvm’: Permission denied
find: ‘/run/systemd/inaccessible/dir’: Permission denied
find: ‘/run/systemd/propagate/systemd-udevd.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-resolved.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-networkd.service’: Permission denied
find: ‘/run/systemd/propagate/irqbalance.service’: Permission denied
find: ‘/run/systemd/propagate/systemd-logind.service’: Permission denied
find: ‘/run/systemd/propagate/chrony.service’: Permission denied
find: ‘/run/systemd/propagate/polkit.service’: Permission denied
find: ‘/run/systemd/propagate/ModemManager.service’: Permission denied
find: ‘/run/systemd/propagate/fwupd.service’: Permission denied
find: ‘/run/systemd/propagate/bolt.service’: Permission denied
find: ‘/run/lvm’: Permission denied
find: ‘/run/log/journal/ec2dd69f90c4a6285216f71caca9bbca’: Permission denied
find: ‘/run/cryptsetup’: Permission denied
find: ‘/run/multipath’: Permission denied
find: ‘/run/screen/S-bandit20’: Permission denied
find: ‘/run/screen/S-bandit27’: Permission denied
find: ‘/run/screen/S-bandit28’: Permission denied
find: ‘/run/screen/S-bandit24’: Permission denied
find: ‘/run/screen/S-bandit17’: Permission denied
find: ‘/run/screen/S-bandit12’: Permission denied
find: ‘/run/screen/S-bandit29’: Permission denied
find: ‘/run/screen/S-bandit23’: Permission denied
find: ‘/run/screen/S-bandit1’: Permission denied
find: ‘/run/screen/S-bandit31’: Permission denied
find: ‘/run/screen/S-bandit21’: Permission denied
find: ‘/run/screen/S-bandit22’: Permission denied
find: ‘/run/screen/S-bandit19’: Permission denied
find: ‘/run/screen/S-bandit30’: Permission denied
find: ‘/run/screen/S-bandit33’: Permission denied
find: ‘/run/screen/S-bandit25’: Permission denied
find: ‘/run/screen/S-bandit16’: Permission denied
find: ‘/run/screen/S-bandit0’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/run/user/11012’: Permission denied
find: ‘/run/user/11001’: Permission denied
find: ‘/run/user/11013’: Permission denied
find: ‘/run/user/11023’: Permission denied
find: ‘/run/user/11016’: Permission denied
find: ‘/run/user/11028’: Permission denied
find: ‘/run/user/11024’: Permission denied
find: ‘/run/user/11027’: Permission denied
find: ‘/run/user/11015’: Permission denied
find: ‘/run/user/11003’: Permission denied
find: ‘/run/user/11020’: Permission denied
find: ‘/run/user/11032’: Permission denied
find: ‘/run/user/11025’: Permission denied
find: ‘/run/user/11026’: Permission denied
find: ‘/run/user/20000’: Permission denied
find: ‘/run/user/11006/systemd/inaccessible/dir’: Permission denied
find: ‘/run/user/11014’: Permission denied
find: ‘/run/user/11021’: Permission denied
find: ‘/run/user/11022’: Permission denied
find: ‘/run/user/11004’: Permission denied
find: ‘/run/user/11005’: Permission denied
find: ‘/run/user/11000’: Permission denied
find: ‘/run/user/11019’: Permission denied
find: ‘/run/user/11008’: Permission denied
find: ‘/run/user/11007’: Permission denied
find: ‘/run/user/11009’: Permission denied
find: ‘/run/user/11031’: Permission denied
find: ‘/run/user/11002’: Permission denied
find: ‘/run/user/11029’: Permission denied
find: ‘/run/user/11011’: Permission denied
find: ‘/run/user/11010’: Permission denied
find: ‘/run/user/11017’: Permission denied
find: ‘/run/chrony’: Permission denied
find: ‘/run/udisks2’: Permission denied
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```
# Level 7 → Level 8
- Used `ssh bandit7@bandit.labs.overthewire.org -p 2220` to log into bandit7 and used the password obtained in the previous level.
- Used `cat data.txt | grep millionth` to obtain the password
### Terminal
```bash
cat data.txt | grep millionth
millionth	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
# Level 8 → Level 9
- Used `ssh bandit8@bandit.labs.overthewire.org -p 2220` to log into bandit8 and used the password obtained in the previous level.
- Used `sort data.txt | uniq -u` to obtain the password where, the `sort` command is like `cat` in that it displays the contents of the file however it sorts the file lexicographically by lines (it reorders them alphabetically so that matching ones are together). The `uniq` command reports or omits repeated lines and by passing it the -u argument we tell it to report only unique lines.
### Terminal 
```bash
sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```
# Level 9 → Level 10
- Used `ssh bandit9@bandit.labs.overthewire.org -p 2220` to log into bandit9 and used the password obtained in the previous level.
- Used `strings data.txt | grep '=' | sort`, where the `strings` command is used to extract human-readable text (printable ASCII and Unicode strings) from binary or non-text files.
- I found "D9========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey" on one line and the "FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey" part seemed like a password which worked on the next level.
### Terminal
```bash
strings data.txt | grep '=' | sort
3JprD========== passwordi
3k=fQ
69}=
7=oc
;c<Q=.dEXU!
D9========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
~de=
~fDV3========== is
N=~[!N
~o=0
p\l=
qC(=	
}========== the
=tZ~07
%"=Y
zA=?0j
zP=
```
Level 10 → Level 11
- Used `ssh bandit10@bandit.labs.overthewire.org -p 2220` to log into bandit10 and used the password obtained in the previous level.
- Used `base64 -d data.txt` to decode the base 64 encoded data in "data.txt" and thus obtained the password.
### Terminal
```bash
base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
### References
- https://www.baeldung.com/linux/cli-base64-encode-decode
# Level 11 → Level 12
- Used `ssh bandit11@bandit.labs.overthewire.org -p 2220` to log into bandit11 and used the password obtained in the previous level.
- Used `cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'` to obtain the password, where the command `tr 'A-Za-z' 'N-ZA-Mn-za-m'` is used for decoding rot13 cipher.
### Terminal
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```
### References
- https://stackoverflow.com/questions/5442436/using-rot13-and-tr-command-for-having-an-encrypted-email-address
# Level 12 → Level 13
- Used `ssh bandit12@bandit.labs.overthewire.org -p 2220` to log into bandit12 and used the password obtained in the previous level.

### Terminal
```bash
bandit12@bandit:~$ mkdir /tmp/adrit
bandit12@bandit:~$ cp data.txt /tmp/adrit

```
### References











  
