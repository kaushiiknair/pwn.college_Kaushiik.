# Perceiving Permissions - Module 11


# Changing File Ownership
In this challenge we are beginning to understand the basics of coding by figuring out how to use the chown command to change the root user and access files that onlky the root user can see.
We change the ownership first and then we use the cat /flag function to obtain the flag.

```
hacker@permissions~changing-file-ownership:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~changing-file-ownership:~$ ls -l
total 48
-rw-r--r-- 1 hacker hacker   4 Sep 30 11:52  COLLEGE
-rw-r--r-- 1 hacker hacker   8 Sep 30 15:49  PWN
-rw-r--r-- 1 hacker hacker   3 Sep 30 11:51  asdf
-rw-r--r-- 1 hacker hacker   0 Sep 26 12:58  challenge
-rw-r--r-- 1 root   hacker  77 Sep 30 16:13  cmd1
drwxr-xr-x 1 hacker hacker   8 Sep 30 04:15  flag
-rw-r--r-- 1 hacker hacker   0 Sep 26 13:55  home
-rw-r--r-- 1 hacker hacker 829 Sep 30 15:25  instructions
-rw------- 1 hacker hacker 484 Sep 22 13:47  key
-rw-r--r-- 1 hacker hacker 112 Sep 22 13:47  key.pub
-rw-r--r-- 1 hacker hacker  95 Sep 30 15:25  myflag
lrwxrwxrwx 1 hacker hacker   5 Sep 27 14:28  not-the-flag -> /flag
-rw-r--r-- 1 hacker hacker   0 Sep 30 15:20  overwrites
-rw-r--r-- 1 hacker hacker   0 Sep 30 15:20  saves
-rw-r--r-- 1 hacker hacker   7 Sep 30 12:00  stdout
-rw-r--r-- 1 hacker hacker   0 Oct  8 12:55  test-file
-rw-r--r-- 1 hacker hacker 437 Sep 30 15:20  the-flag
-rw-r--r-- 1 root   hacker  60 Sep 30 09:47 '~'
hacker@permissions~changing-file-ownership:~$ chown hacker not-the-flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{Q0OFxPc0IrJzgeDYxrRobqzBKT4.QXxEjN0wCN1AzNzEzW}

```

## My Solve 
The flag for the above challenge is pwn.college{Q0OFxPc0IrJzgeDYxrRobqzBKT4.QXxEjN0wCN1AzNzEzW}



# Groups and Files
Similar to the previous problem we are changing the root group so that we can access the file containing the flag, which is done 
by using the ls -l command and then finding the group

```
hacker@permissions~groups-and-files:~$ ls -l
total 48
-rw-r--r-- 1 hacker hacker   4 Sep 30 11:52  COLLEGE
-rw-r--r-- 1 hacker hacker   8 Sep 30 15:49  PWN
-rw-r--r-- 1 hacker hacker   3 Sep 30 11:51  asdf
-rw-r--r-- 1 hacker hacker   0 Sep 26 12:58  challenge
-rw-r--r-- 1 root   hacker  77 Sep 30 16:13  cmd1
drwxr-xr-x 1 hacker hacker   8 Sep 30 04:15  flag
-rw-r--r-- 1 hacker hacker   0 Sep 26 13:55  home
-rw-r--r-- 1 hacker hacker 829 Sep 30 15:25  instructions
-rw------- 1 hacker hacker 484 Sep 22 13:47  key
-rw-r--r-- 1 hacker hacker 112 Sep 22 13:47  key.pub
-rw-r--r-- 1 hacker hacker  95 Sep 30 15:25  myflag
lrwxrwxrwx 1 hacker hacker   5 Sep 27 14:28  not-the-flag -> /flag
-rw-r--r-- 1 hacker hacker   0 Sep 30 15:20  overwrites
-rw-r--r-- 1 hacker hacker   0 Sep 30 15:20  saves
-rw-r--r-- 1 hacker hacker   7 Sep 30 12:00  stdout
-rw-r--r-- 1 hacker hacker   0 Oct  8 12:55  test-file
-rw-r--r-- 1 hacker hacker 437 Sep 30 15:20  the-flag
-rw-r--r-- 1 root   hacker  60 Sep 30 09:47 '~'
hacker@permissions~groups-and-files:~$ chgrp hacker not-the-flag
hacker@permissions~groups-and-files:~$ cat /flag
pwn.college{s04XbDaXkTFbIrr44shgF9ovLfQ.QXxcjM1wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{s04XbDaXkTFbIrr44shgF9ovLfQ.QXxcjM1wCN1AzNzEzW}



# Fun with Groups Names
In this challenge we are changing the group name as it is different, but just simply repeating what we have done in the previous steps.
We are learning how to efficiently use the chgrp command and use that to input the correct id which will give us the flag.

```
hacker@permissions~fun-with-groups-names:~$ ls -l
total 48
-rw-r--r-- 1 hacker grp25352   4 Sep 30 11:52  COLLEGE
-rw-r--r-- 1 hacker grp25352   8 Sep 30 15:49  PWN
-rw-r--r-- 1 hacker grp25352   3 Sep 30 11:51  asdf
-rw-r--r-- 1 hacker grp25352   0 Sep 26 12:58  challenge
-rw-r--r-- 1 root   grp25352  77 Sep 30 16:13  cmd1
drwxr-xr-x 1 hacker grp25352   8 Sep 30 04:15  flag
-rw-r--r-- 1 hacker grp25352   0 Sep 26 13:55  home
-rw-r--r-- 1 hacker grp25352 829 Sep 30 15:25  instructions
-rw------- 1 hacker grp25352 484 Sep 22 13:47  key
-rw-r--r-- 1 hacker grp25352 112 Sep 22 13:47  key.pub
-rw-r--r-- 1 hacker grp25352  95 Sep 30 15:25  myflag
lrwxrwxrwx 1 hacker grp25352   5 Sep 27 14:28  not-the-flag -> /flag
-rw-r--r-- 1 hacker grp25352   0 Sep 30 15:20  overwrites
-rw-r--r-- 1 hacker grp25352   0 Sep 30 15:20  saves
-rw-r--r-- 1 hacker grp25352   7 Sep 30 12:00  stdout
-rw-r--r-- 1 hacker grp25352   0 Oct  8 12:55  test-file
-rw-r--r-- 1 hacker grp25352 437 Sep 30 15:20  the-flag
-rw-r--r-- 1 root   grp25352  60 Sep 30 09:47 '~'
hacker@permissions~fun-with-groups-names:~$ chgrp grp25352 not-the-flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{s783fDIljdL-IuVGRz6mx44HY9F.QXycjM1wCN1AzNzEzW}

```
## My Solve
The flag for the above challenge is pwn.college{s783fDIljdL-IuVGRz6mx44HY9F.QXycjM1wCN1AzNzEzW}



# Changing Permissions
In this challenge we learnt that we can use r - user/group/other for reading the file (or list the directory), w - user/group/other for modifying the files (or create/delete files in the directory), x - user/group/other can execute the file as a program (or can enter the directory, e.g., using cd)

```
hacker@permissions~changing-permissions:~$ chmod g+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~changing-permissions:~$ chmod go+r /flag
hacker@permissions~changing-permissions:~$ ls -l
total 48
-rw------- 1 hacker hacker   4 Sep 30 11:52  COLLEGE
-rw------- 1 hacker hacker   8 Sep 30 15:49  PWN
-rw------- 1 hacker hacker   3 Sep 30 11:51  asdf
-rw------- 1 hacker hacker   0 Sep 26 12:58  challenge
-rw------- 1 root   hacker  77 Sep 30 16:13  cmd1
drwx------ 1 hacker hacker   8 Sep 30 04:15  flag
-rw------- 1 hacker hacker   0 Sep 26 13:55  home
-rw------- 1 hacker hacker 829 Sep 30 15:25  instructions
-rw------- 1 hacker hacker 484 Sep 22 13:47  key
-rw------- 1 hacker hacker 112 Sep 22 13:47  key.pub
-rw------- 1 hacker hacker  95 Sep 30 15:25  myflag
lrwxrwxrwx 1 hacker hacker   5 Sep 27 14:28  not-the-flag -> /flag
-rw------- 1 hacker hacker   0 Sep 30 15:20  overwrites
-rw------- 1 hacker hacker   0 Sep 30 15:20  saves
-rw------- 1 hacker hacker   7 Sep 30 12:00  stdout
-rw------- 1 hacker hacker   0 Oct  8 12:55  test-file
-rw------- 1 hacker hacker 437 Sep 30 15:20  the-flag
-rw------- 1 root   hacker  60 Sep 30 09:47 '~'
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{cCF9tOMMvr1I25VSLhC0kD2PMP6.QXzcjM1wCN1AzNzEzW}
```
## My Solve 
The flag for the above challenge is pwn.college{cCF9tOMMvr1I25VSLhC0kD2PMP6.QXzcjM1wCN1AzNzEzW}



# Executable Files
In this challenge we learn how to execute files and this is done by using the x in chmod. 
```
hacker@permissions~executable-files:~$ chmod o-x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
bash: /challenge/run: Permission denied
hacker@permissions~executable-files:~$ chmod u+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{UcWlUxtgHDUxJ_NWIhw8xCxHOPT.QXyEjN0wCN1AzNzEzW}
```

## My Solve 
The flag for the above challenge is pwn.college{UcWlUxtgHDUxJ_NWIhw8xCxHOPT.QXyEjN0wCN1AzNzEzW}



# Permission Tweaking Practice 




