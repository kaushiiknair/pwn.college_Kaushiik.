# Pondering PATH - 14th Module 

# The PATH Variable 

```
kaushiik-s-nair@kaushiik-s-nair-HP-OmniBook-5-Flip-Laptop-14-fp0xxx:~$ ssh -i key hacker@dojo.pwn.college
Connected!                                                                        
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
Uh oh, looks like I successfully removed the flag! That means you did not 
properly set PATH to keep me from finding 'rm'. Since the flag is gone, you 
will need to re-launch the challenge from the module page! Better luck next 
time.
hacker@path~the-path-variable:~$ 
Connected!                                                                        
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{gvQ527MaIiPtFxl1OLCckyk2oBy.QX2cDM1wCN1AzNzEzW}
```

## My Solve 
The flag for the above challenge is pwn.college{gvQ527MaIiPtFxl1OLCckyk2oBy.QX2cDM1wCN1AzNzEzW}



# Setting PATH

In this challenge we are learning how to set the paths for the functions to be carried out. THis enables us the program to be followed and then when we run the challenge the flag is produced.


```
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{c7BK5B9yVMERZGe4gSydoMtWgFO.QX1cjM1wCN1AzNzEzW}

```

## My Solve
The flag for the above challenge is pwn.college{c7BK5B9yVMERZGe4gSydoMtWgFO.QX1cjM1wCN1AzNzEzW}



# Finding Commands

```
hacker@path~finding-commands:~$ which win
/challenge/paths/5615/win
hacker@path~finding-commands:~$ cat /challenge/paths/5615/win
#!/bin/bash

/bin/fold -s <<< "Search for the flag in the same directory in which I am located!"
hacker@path~finding-commands:~$ cat /challenge/paths/5615/win/flag
cat: /challenge/paths/5615/win/flag: Not a directory
hacker@path~finding-commands:~$ cat /challenge/paths/5615/flag
pwn.college{AYiCpj3GwV3R2ojdBUvSKA5G1Qa.01NzEzNxwCN1AzNzEzW}

```

## My Solve
The flag for the above challenge is pwn.college{AYiCpj3GwV3R2ojdBUvSKA5G1Qa.01NzEzNxwCN1AzNzEzW}



# Adding Commands

```
hacker@path~adding-commands:~$ ls /home/hacker/scripts
ls: cannot access '/home/hacker/scripts': No such file or directory
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
/challenge/run: line 4: win: command not found
It looks like that did not work... Did you set PATH correctly?
hacker@path~adding-commands:~$ cd /home
hacker@path~adding-commands:/home$ la
bash: la: command not found
hacker@path~adding-commands:/home$ ls
hacker
hacker@path~adding-commands:/home$ cd hacker
hacker@path~adding-commands:~$ ls
 COLLEGE   challenge   home           key.pub   not-the-flag   saves      test-file  '~'
 PWN       cmd1        instructions   mybin     out.sh         solve.sh   the-flag
 asdf      flag        key            myflag    overwrites     stdout     x.sh
hacker@path~adding-commands:~$ cd challenges
bash: cd: challenges: No such file or directory
hacker@path~adding-commands:~$ ls
 COLLEGE   challenge   home           key.pub   not-the-flag   saves      test-file  '~'
 PWN       cmd1        instructions   mybin     out.sh         solve.sh   the-flag
 asdf      flag        key            myflag    overwrites     stdout     x.sh
hacker@path~adding-commands:~$ cd challenge
bash: cd: challenge: Not a directory
hacker@path~adding-commands:~$ cd /challenge
hacker@path~adding-commands:/challenge$ ls
DESCRIPTION.md  run
hacker@path~adding-commands:/challenge$ cd /run
hacker@path~adding-commands:/run$ ls
apache2         dojo                      log     screen           sudo     utmp
challenge       firefox-restart-required  mount   sendsigs.omit.d  systemd
current-system  lock                      mysqld  shm              user
hacker@path~adding-commands:/run$ cd ..
hacker@path~adding-commands:/$ nano /home/hacker/scripts/win
hacker@path~adding-commands:/$ cd /home/hacker
hacker@path~adding-commands:~$ mkdir scripts
hacker@path~adding-commands:~$ nano /home/hacker/scripts/win
hacker@path~adding-commands:~$ chmod +x /home/hacker/scripts/win
hacker@path~adding-commands:~$ export PATH=/home/hacker/scripts:$PATH
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{ITmv5B1LiuRLCZLQsPjBvJQZRJ5.QX2cjM1wCN1AzNzEzW}

```



## My Solve
The flag for the above challenge is pwn.college{ITmv5B1LiuRLCZLQsPjBvJQZRJ5.QX2cjM1wCN1AzNzEzW}




# Hijacking Commands

```
hacker@path~hijacking-commands:~$ mkdir ~/mybin
mkdir: cannot create directory ‘/home/hacker/mybin’: File exists
hacker@path~hijacking-commands:~$ nano ~/mybin/rm
hacker@path~hijacking-commands:~$ chmod +x ~/mybin/rm 
hacker@path~hijacking-commands:~$ export PATH=~/mybin:$PATH
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/mybin/rm. Executing!
/home/hacker/mybin/rm: line 3: syntax error near unexpected token `in'
/home/hacker/mybin/rm: line 3: `in nano'
hacker@path~hijacking-commands:~$ nano ~/mybin/rm
hacker@path~hijacking-commands:~$ chmod +x ~/mybin/rm 
hacker@path~hijacking-commands:~$ export PATH=~/mybin:$PATH
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/mybin/rm. Executing!
this is a fake flag
hacker@path~hijacking-commands:~$ nano ~/mybin/rm
hacker@path~hijacking-commands:~$ chmod +x ~/mybin/rm 
hacker@path~hijacking-commands:~$ export PATH=~/mybin:$PATH
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
Found 'rm' command at /home/hacker/mybin/rm. Executing!
this is a fake flag
pwn.college{I1ELjETw4Vy9Pud-5OzxFtsrcSq.QX3cjM1wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{I1ELjETw4Vy9Pud-5OzxFtsrcSq.QX3cjM1wCN1AzNzEzW}




