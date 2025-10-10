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

In this challenge, we learn how to use the chmod function to change the permissions on the user, group and world setting. this allowed us to complete a series of 8 challenges by enabling permissions which finally gave us access to the flag.

```
kaushiik-s-nair@kaushiik-s-nair-HP-OmniBook-5-Flip-Laptop-14-fp0xxx:~$ ssh -i key hacker@dojo.pwn.college
No active challenge session; start a challenge!
Connection to dojo.pwn.college closed.
kaushiik-s-nair@kaushiik-s-nair-HP-OmniBook-5-Flip-Laptop-14-fp0xxx:~$ ssh -i key hacker@dojo.pwn.college
Connected!                                                                        
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw----r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-r /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": rw----r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-rw
/usr/bin/chmod: missing operand after ‘g-rw’
Try '/usr/bin/chmod --help' for more information.
NEEDED, BUT UNMET permissions of "/challenge/pwn": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

CURRENT, INCORRECT permissions of "/challenge/pwn": rw----r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

You set the permissions incorrectly! Restarting the game!
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw----r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-r /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": rw----r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod uo-rw /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wx----wx
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ uo+wx
bash: uo+wx: command not found
hacker@permissions~permission-tweaking-practice:~$ chmod uo+wx /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": -wx----wx
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --x----wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-w /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": --x----wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -wx-wx-wx
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ugo+wx /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": -wx-wx-wx
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ----wx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u-wx /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": ----wx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ----w--wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-x /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": ----w--wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -------wx
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-w /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ugo+rwx
chmod: missing operand after ‘ugo+rwx’
Try 'chmod --help' for more information.
hacker@permissions~permission-tweaking-practice:~$ chmod ugo+rwx /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{YZ0Oc46EXuzV9FWAzZP5okaqCEM.QXwEjN0wCN1AzNzEzW}
```

## My Solve 
The flag for the aboce challenge is pwn.college{YZ0Oc46EXuzV9FWAzZP5okaqCEM.QXwEjN0wCN1AzNzEzW}



# Permissions Setting Practice

In this challenge we arelearning how to do the same thing we did in the aboce challenge but in the process utilising the = sign which helps in defining the parameters better.

```
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wx-----x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=-,o=x /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": -wx-----x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --xrwx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=rwx,o=wx /challenge/pwn
NEEDED, BUT UNMET permissions of "/challenge/pwn": --xrwx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

CURRENT, INCORRECT permissions of "/challenge/pwn": -wxrwx-wx
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

You set the permissions incorrectly! Restarting the game!
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wx-----x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=-,o=x /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": -wx-----x
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --xrwx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=rwx,o=wx /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": --xrwx-wx
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-xr-xrw-
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rx,g=rx,o=rw /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": r-xr-xrw-
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwx-w-r-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=w,o=rx /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": rwx-w-r-x
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": r-x-w-r--
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rx,g=w,o=r /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": r-x-w-r--
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r-xrw--wx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rx,g=rw,o=wx /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": r-xrw--wx
* the user does have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --------x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=-,g=-,o=x /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": --------x
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": ---r-----
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=-,g=r,o=- /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=rwx,o=rwx /challenge/pwn
hacker@permissions~permissions-setting-practice:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~permissions-setting-practice:~$ cat /challenge/pwn
hacker@permissions~permissions-setting-practice:~$ cat/flag
bash: cat/flag: No such file or directory
hacker@permissions~permissions-setting-practice:~$ chmod u=rwx,g=rwx,o=rwx /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{AWXZcuEeeLh-cnYOx6UTjqHnrSM.QXzETO0wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{AWXZcuEeeLh-cnYOx6UTjqHnrSM.QXzETO0wCN1AzNzEzW}



# The SUID Bit

The goal for this challenge is to learn how to use the SUID bit which is meant to be for a set user id. 
```
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root! 
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{cJW7jh2nKIUfW5Zdgj6223ouDJ1.QXzEjN0wCN1AzNzEzW}
root@permissions~the-suid-bit:~# exit
exit

```

## My Solve
The flag for the above challenge is pwn.college{cJW7jh2nKIUfW5Zdgj6223ouDJ1.QXzEjN0wCN1AzNzEzW}






