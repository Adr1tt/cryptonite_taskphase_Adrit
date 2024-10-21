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
### References
- https://www.geeksforgeeks.org/sort-command-linuxunix-examples/
- https://www.geeksforgeeks.org/uniq-command-in-linux-with-examples/
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
### References
- https://www.javatpoint.com/linux-strings-command
# Level 10 → Level 11
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
- In this level I had to decompress the file data.txt (which was a hexdump) alot of times using the commands `tar`, `gunzip` and `bunzip`.
- Finally after decompressing the file alot of times, an ASCII file was the result which contained the password.

### Terminal
```bash
bandit12@bandit:~$ mkdir /tmp/adrit
bandit12@bandit:~$ cd /tmp/adrit
bandit12@bandit:/tmp/adrit$ cp ~/data.txt .
bandit12@bandit:/tmp/adrit$ ls
data.txt
bandit12@bandit:/tmp/adrit$ file data.txt
data.txt: ASCII text
bandit12@bandit:/tmp/adrit$ xxd -r data.txt > output.bin
bandit12@bandit:/tmp/adrit$ file output.bin
output.bin: gzip compressed data, was "data2.bin", last modified: Thu Sep 19 07:08:15 2024, max compression, from Unix, original size modulo 2^32 574
bandit12@bandit:/tmp/adrit$ mv output.bin output.gz
bandit12@bandit:/tmp/adrit$ gunzip output.gz
bandit12@bandit:/tmp/adrit$ ls
data.txt  output
bandit12@bandit:/tmp/adrit$ file output
output: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/adrit$ mv output output.bz2
bandit12@bandit:/tmp/adrit$ bunzip2 output.bz2
bandit12@bandit:/tmp/adrit$ ls
data.txt  output
bandit12@bandit:/tmp/adrit$ file output
output: gzip compressed data, was "data4.bin", last modified: Thu Sep 19 07:08:15 2024, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/adrit$ mv output output.gz
bandit12@bandit:/tmp/adrit$ gunzip output.gz
bandit12@bandit:/tmp/adrit$ ls
data.txt  output
bandit12@bandit:/tmp/adrit$ file output
output: POSIX tar archive (GNU)
bandit12@bandit:/tmp/adrit$ mv output output.tar
bandit12@bandit:/tmp/adrit$ tar -xf output.tar
bandit12@bandit:/tmp/adrit$ ls
data5.bin  data.txt  output.tar
bandit12@bandit:/tmp/adrit$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/adrit$ mv data5.bin data5.tar
bandit12@bandit:/tmp/adrit$ tar -xf data5.tar
bandit12@bandit:/tmp/adrit$ ls
data5.tar  data6.bin  data.txt  output.tar
bandit12@bandit:/tmp/adrit$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/adrit$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/adrit$ bunzip2 data6.bz2
bandit12@bandit:/tmp/adrit$ ls
data5.tar  data6  data.txt  output.tar
bandit12@bandit:/tmp/adrit$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/adrit$ mv data6 data6.tar
bandit12@bandit:/tmp/adrit$ tar -xf data6.tar
bandit12@bandit:/tmp/adrit$ ls
data5.tar  data6.tar  data8.bin  data.txt  output.tar
bandit12@bandit:/tmp/adrit$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Sep 19 07:08:15 2024, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/adrit$ mv data8.bin data8.gz
bandit12@bandit:/tmp/adrit$ gunzip data8.gz
bandit12@bandit:/tmp/adrit$ ls
data5.tar  data6.tar  data8  data.txt  output.tar
bandit12@bandit:/tmp/adrit$ file data8
data8: ASCII text
bandit12@bandit:/tmp/adrit$ cat data8
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```
### References
- https://www.commandlinux.com/man-page/man1/bunzip2.1.html
- https://www.geeksforgeeks.org/gunzip-command-in-linux-with-examples/
- https://www.geeksforgeeks.org/tar-command-linux-examples/
- https://stackoverflow.com/questions/43724144/hexdump-reverse-command
# Level 13 → Level 14
- Used `ssh bandit13@bandit.labs.overthewire.org -p 2220` to log into bandit13 and used the password obtained in the previous level, which outputted this:
  ```bash
  sshkey.private                                100% 1679     4.6KB/s   00:00
  ```
- Then  I used `chmod 400 sshkey.private` to ensure the private key file has the correct permissions.
- Then used `ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220` to login as bandit14.
- Then used `cat /etc/bandit_pass/bandit14` to obtain the password
### Terminal
```bash
bandit13@bandit.labs.overthewire.org's password: 
sshkey.private                                100% 1679     4.6KB/s   00:00    
(base) adrit@Adrits-MacBook-Air ~ % chmod 400 sshkey.private
(base) adrit@Adrits-MacBook-Air ~ % ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames


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

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
```
### References
- https://www.cloudbolt.io/blog/linux-how-to-login-with-a-ssh-private-key/
- https://www.geeksforgeeks.org/how-to-login-to-ssh-without-a-password-using-private-key/
- https://help.ubuntu.com/community/SSH/OpenSSH/Keys
# Level 14 → Level 15
- Used `ssh bandit14@bandit.labs.overthewire.org -p 2220` to log into bandit14 and used the password obtained in the previous level.
- Used `cat /etc/bandit_pass/bandit14 | nc localhost 30000` to obtain the password.
### Terminal
```bash
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14 | nc localhost 30000
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```
### References
- https://www.geeksforgeeks.org/practical-uses-of-ncnetcat-command-in-linux/
- https://www.cloudflare.com/learning/network-layer/what-is-a-computer-port/
# Level 15 → Level 16
- Used `ssh bandit15@bandit.labs.overthewire.org -p 2220` to log into bandit15 and used the password obtained in the previous level.
- Used `cat /etc/bandit_pass/bandit15` to get the password of the current level.
- Tried to obtain the password for the next level by piping the password of the current level into the `openssl` command.
- Learnt the "-quiet- arguement for `openssl` and used `cat /etc/bandit_pass/bandit15 | openssl s_client -connect localhost:30001 -quiet` to obtain the password.

### Terminal
```bash
bandit15@bandit:~$ cat /etc/bandit_pass/bandit15
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
bandit15@bandit:~$ cat /etc/bandit_pass/bandit15 | openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 9FA96129C15402CC707C595241A9FE2188C029CD9D70F23750E93ADDE801B9BD
    Session-ID-ctx: 
    Resumption PSK: DAA6338F2094DDAA336C2C0DAFA979212668F13FB8F6CC58E548EF2D1E3E095A3FC8F309C80DAF3E6418E307F70CCAE8
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - c0 c6 3d 9e 22 a9 6f a8-d6 08 ea 57 e8 ec 3e f7   ..=.".o....W..>.
    0010 - 4a 2c 78 eb be 0a 82 71-cf 03 8d 2e 5d a0 77 b5   J,x....q....].w.
    0020 - 53 4e c7 a5 48 49 2c 83-8b 10 22 00 3e d1 f5 15   SN..HI,...".>...
    0030 - f9 36 fc 54 dd 6f 87 1a-ad 77 d1 18 7e df e0 01   .6.T.o...w..~...
    0040 - ea e6 1d 01 0f 78 1b 8f-60 73 7b ad ba 60 4c fd   .....x..`s{..`L.
    0050 - 0a 13 0c da 05 fa 80 22-db aa 1e 14 cb a9 e1 d4   ......."........
    0060 - fc 63 62 8b d7 19 4d 0b-f0 45 2e 7e db eb 4a 9b   .cb...M..E.~..J.
    0070 - d4 55 37 32 92 75 04 0e-f2 82 b5 25 9c d7 89 ac   .U72.u.....%....
    0080 - 5b 76 17 c0 fa dd 64 78-81 63 e2 79 98 78 28 aa   [v....dx.c.y.x(.
    0090 - 33 5f 11 4d 29 b7 89 f4-34 f7 57 c8 6d af ee 42   3_.M)...4.W.m..B
    00a0 - cf 85 b8 c4 fe f7 93 12-8a 4a 81 b0 38 b6 0a ff   .........J..8...
    00b0 - 5e 46 88 1f 50 55 c0 97-d1 fd 6d 8d bf 1f e4 e9   ^F..PU....m.....
    00c0 - be 26 67 e1 ac ae 7c 35-2f 4a 7c 03 0a c3 7a fa   .&g...|5/J|...z.
    00d0 - 9a 08 0a c4 a5 9a 36 ed-30 c3 3a 0b 43 f0 5c cb   ......6.0.:.C.\.

    Start Time: 1729441533
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 56B46F274829A33AF3C2D6900119D614D44C2614B7F1F37CB7D75C299F1ADF27
    Session-ID-ctx: 
    Resumption PSK: EB9A4A3A356DAE1B188D750435EE98EC5F75FC76183EDDD331E55DC5E93744D72FE6EB104222AD4C5AAB66799E633611
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - c0 c6 3d 9e 22 a9 6f a8-d6 08 ea 57 e8 ec 3e f7   ..=.".o....W..>.
    0010 - df ff ee ac 2c 05 25 97-72 fb e1 8e ac 4d 83 16   ....,.%.r....M..
    0020 - 23 d5 bf 73 80 f7 d1 d0-a7 ef 18 d7 20 df 70 b6   #..s........ .p.
    0030 - 14 0a 92 28 86 f6 da b8-da 06 c1 b7 3f f9 be 79   ...(........?..y
    0040 - 50 7b 1d 55 6f 59 2a 8b-8f f1 9c 8e f8 26 03 da   P{.UoY*......&..
    0050 - 12 5b f5 a1 17 27 a6 e8-4e 54 8e 9c ab 9d 0d 76   .[...'..NT.....v
    0060 - a8 ae c5 e4 69 57 d4 ad-28 9d b0 ee 23 06 91 3c   ....iW..(...#..<
    0070 - 7b 12 6f 36 b6 81 9b 02-db d9 7b 8f 60 81 93 c5   {.o6......{.`...
    0080 - a6 5f b1 c8 eb 35 5e 1f-6c 06 c2 81 4a dc 2e b4   ._...5^.l...J...
    0090 - 95 e8 1c d6 40 73 0a 9d-2e d5 28 f2 38 6e c2 0a   ....@s....(.8n..
    00a0 - a6 28 e2 a3 93 2a 1a a2-11 a9 a2 7d d6 68 3f e9   .(...*.....}.h?.
    00b0 - fb 8d 7d ab 7f 9f 89 6a-79 67 08 02 8e 12 19 57   ..}....jyg.....W
    00c0 - 7c 2f a0 3c 9c 2a 19 a3-42 ab 0e 98 26 00 47 d5   |/.<.*..B...&.G.
    00d0 - e1 36 c0 fa 33 1a 07 7b-5c 4a 65 da f2 4b ef bf   .6..3..{\Je..K..

    Start Time: 1729441533
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
DONE
bandit15@bandit:~$ cat /etc/bandit_pass/bandit15 | openssl s_client -connect localhost:30001 -quiet
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```
### References
- https://www.geeksforgeeks.org/practical-uses-of-openssl-command-in-linux/
- Man page of "openssl"
# Level 16 → Level 17
- Used `ssh bandit16@bandit.labs.overthewire.org -p 2220` to log into bandit16 and used the password obtained in the previous level.
- Used `nmap localhost -p 31000-32000` to scan for the working ports between 31000-32000. The output had 5 ports and I tried `cat /etc/bandit_pass/bandit16 | openssl s_client -connect localhost:31960 -quiet` for one port which did not work.
- Next I used `cat /etc/bandit_pass/bandit16 | openssl s_client -connect localhost:31790 -quiet` which worked and gave me an RSA Key
### Terminal
```bash
bandit16@bandit:~$ nmap localhost -p 31000-32000
Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-10-20 17:00 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00021s latency).
Not shown: 996 closed tcp ports (conn-refused)
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.08 seconds
bandit16@bandit:~$ cat /etc/bandit_pass/bandit16 | openssl s_client -connect localhost:31960 -quiet
4087F0F7FF7F0000:error:0A0000F4:SSL routines:ossl_statem_client_read_transition:unexpected message:../ssl/statem/statem_clnt.c:398:
bandit16@bandit:~$ cat /etc/bandit_pass/bandit16 | openssl s_client -connect localhost:31790 -quiet
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----
```
### References
- https://www.geeksforgeeks.org/nmap-command-in-linux-with-examples/
# Level 17 → Level 18
- Still logged in as bandit16 I used `mkdir /tmp/adrit1` and `cd /tmp/adrit1` then I used `nano rsa` and copied the RSA Key inside the file.
- Then I used `ls -l` to check permissions and `chmod 600 rsa` to change permissions and finally `ssh -i rsa bandit17@localhost -p 2220` to log in as bandit 17.
- Now, as bandit17 I used `diff passwords.old passwords.new` to find the difference between 2 files
### Terminal
  ```bash
  bandit16@bandit:~$ mkdir /tmp/adrit1
bandit16@bandit:~$ cd /tmp/adrit1
bandit16@bandit:/tmp/adrit1$ nano rsa
Unable to create directory /home/bandit16/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit16@bandit:/tmp/adrit1$ ls -l
total 4
-rw-rw-r-- 1 bandit16 bandit16 1675 Oct 20 17:12 rsa
bandit16@bandit:/tmp/adrit1$ chmod 600 rsa
bandit16@bandit:/tmp/adrit1$ ssh -i rsa bandit17@localhost -p 2220
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit16/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit16/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

!!! You are trying to log into this SSH server with a password on port 2220 from localhost.
!!! Connecting from localhost is blocked to conserve resources.
!!! Please log out and log in again.


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

bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< ktfgBvpMzWKR5ENj26IbLGSblgUG9CzB
---
> x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
```
# Level 18 → Level 19
- I used `ssh bandit18@bandit.labs.overthewire.org -p 2220` to log into bandit18 and used the password obtained in the previous level but it didn't work.
- Then I used `ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"` to directly get the password.
### Terminal 
```bash
adrit@Adrits-MacBook-Air ~ % ssh bandit18@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 

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

Byebye !
(base) adrit@Adrits-MacBook-Air ~ % ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
```
# Level 19 → Level 20
- Used `ssh bandit19@bandit.labs.overthewire.org -p 2220` to log into bandit19 and used the password obtained in the previous level.
- Used `ls` to see the files in my current directory, then used `~/bandit20-do`, which told me to run the command as another user.
- I tried `./bandit20-do cat /etc/bandit_pass/bandit20` and it worked, thus obtaining the password.
### Terminal
```bash
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ~/bandit20-do
Run a command as another user.
  Example: /home/bandit19/bandit20-do id
bandit19@bandit:~$ /bandit20-do cat /etc/bandit_pass/bandit20
-bash: /bandit20-do: No such file or directory
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
```
### References
- https://en.wikipedia.org/wiki/Setuid
- https://www.tutorialspoint.com/setuid-setgid-and-sticky-bits-in-linux-file-permissions
# Level 20 → Level 21
- Used `ssh bandit20@bandit.labs.overthewire.org -p 2220` to log into bandit20 and used the password obtained in the previous level.
- Opened another terminal window and logged in as bandit20.
- Used `cat /etc/bandit_pass/bandit20` which gave me the password obtained previously. Then I used `nc -lvp 9630 < /etc/bandit_pass/bandit20` for listening on a random port "9630"
- Then in the other terminal I used `./suconnect 9630` and obtained the password.
### Terminal 1
```bash
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ ./suconnect
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
bandit20@bandit:~$ ./suconnect 9630
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
```
### Terminal 2
```bash
bandit20@bandit:~$ cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
bandit20@bandit:~$ nc -lvp 9630 < /etc/bandit_pass/bandit20
Listening on 0.0.0.0 9630
Connection received on localhost 49912
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
```
### References
- https://superuser.com/questions/1533731/use-netcat-to-listen-on-a-port-and-send-output-from-a-command-when-a-client-conn
- https://stackoverflow.com/questions/51775230/what-does-connecting-to-own-network-daemon-mean
- man page of `nc` command
# Level 21 → Level 22
- Used `ssh bandit21@bandit.labs.overthewire.org -p 2220` to log into bandit21 and used the password obtained in the previous level.
- Used `ls /etc/cron.d/` , `ls -a /etc/cron.d/` and `ls -l /etc/cron.d/` and found a process called "cronjob_bandit22" running.
- I used `cd /etc/cron.d/` to change directories and used `cat cronjob_bandit22` which told me about "/usr/bin/cronjob_bandit22.sh".
- Then I entered `cronjob_bandit22.sh` into the terminal prompt which did not work.
- After that I used `cd ~` and `cat /etc/cron.d/cronjob_bandit22` again which gave the same output.
- Now, I used `cat /usr/bin/cronjob_bandit22.sh`. The output indicated that the password might be in "/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv"
- Then I used `cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv` to obtain the password.

### Terminal
```bash
bandit21@bandit:~$ ls /etc/cron.d/
cronjob_bandit22  cronjob_bandit24  otw-tmp-dir
cronjob_bandit23  e2scrub_all       sysstat
bandit21@bandit:~$ ls -a /etc/cron.d/
.   cronjob_bandit22  cronjob_bandit24  otw-tmp-dir   sysstat
..  cronjob_bandit23  e2scrub_all       .placeholder
bandit21@bandit:~$ ls -l /etc/cron.d/
total 24
-rw-r--r-- 1 root root 120 Sep 19 07:08 cronjob_bandit22
-rw-r--r-- 1 root root 122 Sep 19 07:08 cronjob_bandit23
-rw-r--r-- 1 root root 120 Sep 19 07:08 cronjob_bandit24
-rw-r--r-- 1 root root 201 Apr  8  2024 e2scrub_all
-rwx------ 1 root root  52 Sep 19 07:10 otw-tmp-dir
-rw-r--r-- 1 root root 396 Jan  9  2024 sysstat
bandit21@bandit:~$  cd /etc/cron.d/
bandit21@bandit:/etc/cron.d$ cat cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:/etc/cron.d$ cronjob_bandit22.sh
chmod: changing permissions of '/tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv': Operation not permitted
/usr/bin/cronjob_bandit22.sh: line 3: /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv: Permission denied
bandit21@bandit:/etc/cron.d$ cd ~
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
```
#  Level 22 → Level 23
- Used `ssh bandit23@bandit.labs.overthewire.org -p 2220` to log into bandit22 and used the password obtained in the previous level.
- Used `ls -l /etc/cron.d` and just like the last level I used `cat /etc/cron.d/cronjob_bandit23` and then `cat /usr/bin/cronjob_bandit23.sh`, which told me what to do in order to get the password.
- I tried following the exact steps by using `myname=$(whoami)` , `mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)` and `cat /etc/bandit_pass/$myname > /tmp/$mytarget`.
- Then I used `echo $mytarget` and and used that value to get the file in "/tmp" by using `cat /tmp/8169b67bd894ddbb4412f91573b38db3`, but the password was the same as the previous level and I tried logging into bandit23 using this password but it was incorrect.
- I understood my mistake, the `whoami` command set the variable "myname" to bandit22 but I needed it to be bandit 23.
- Therefore, I used `mytarget=$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)` and then tried `cat /etc/bandit_pass/bandit23 > /tmp/$mytarget` but the "Permission denied" message showed up.
- Then I used `echo "I am user bandit23" | md5sum | cut -d ' ' -f 1` which gave me the file name in "/tmp" storing the password. Then I used `cat /tmp/8ca319486bfbbc3663ea0fbe81326349` to finally obtain the password.

### Terminal
```bash

bandit22@bandit:~$ ls -l /etc/cron.d
total 24
-rw-r--r-- 1 root root 120 Sep 19 07:08 cronjob_bandit22
-rw-r--r-- 1 root root 122 Sep 19 07:08 cronjob_bandit23
-rw-r--r-- 1 root root 120 Sep 19 07:08 cronjob_bandit24
-rw-r--r-- 1 root root 201 Apr  8  2024 e2scrub_all
-rwx------ 1 root root  52 Sep 19 07:10 otw-tmp-dir
-rw-r--r-- 1 root root 396 Jan  9  2024 sysstat
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ myname=$(whoami)
bandit22@bandit:~$ mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
bandit22@bandit:~$ cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ echo $mytarget
8169b67bd894ddbb4412f91573b38db3
bandit22@bandit:~$ cat /tmp/8169b67bd894ddbb4412f91573b38db3
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
bandit22@bandit:~$ mytarget=$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
bandit22@bandit:~$ cat /etc/bandit_pass/bandit23 > /tmp/$mytarget
-bash: /tmp/8ca319486bfbbc3663ea0fbe81326349: Permission denied
bandit22@bandit:~$ echo "I am user bandit23" | md5sum | cut -d ' ' -f 1
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
```
















  
