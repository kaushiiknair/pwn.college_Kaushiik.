# Comprehending Commands - Module 3

# Cat: Not the pet, but the command!
IN this challenge we learn how to use the cat command which is short for concatenate and its purpose is commonly used to read out the files. I had to use the cat command to find out which file in the current shell had the flag present and this was possible because of cat command

```
hacker@commands~cat-not-the-pet-but-the-command:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@commands~cat-not-the-pet-but-the-command:/$ cat flag
```

## My Solve
The flag for the above challenge is pwn.college{guKIVwha6ySasFTdSCQJYyCQ5xe.QXxcTN0wCN1AzNzEzW}



# Catting Absolute Paths
Similar to the previous challenge we use the cat command to find the flag by reading the /flag absolute path

```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{kCqdXfcLdYRcIC0zRtOT0p0D_Qq.QX5ETO0wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{kCqdXfcLdYRcIC0zRtOT0p0D_Qq.QX5ETO0wCN1AzNzEzW}


# More catting practice
In this challenge, i couldnt locate the flag just by simply using the cat function but had to use an absolute path as the directory was very long and thepn use the cat function which then supplied me with the flag. It was kind of a trial and error approach.

```
hacker@commands~more-catting-practice:~$ /usr/lib/tcltk/flag.
bash: /usr/lib/tcltk/flag.: No such file or directory
hacker@commands~more-catting-practice:~$ cat /usr/lib/tcltk/flag.
cat: /usr/lib/tcltk/flag.: No such file or directory
hacker@commands~more-catting-practice:~$ cat /usr/lib/tcltk/flag
```

## My Solve 
The flag for the above challenge is pwn.college{YJ8IynkDMvPI1sJpyKEUVa4Wgpf.QXwITO0wCN1AzNzEzW}


# Grepping for a needle in a haystack
For this challenge we obtain a new command called grep which is used on bigger files then what cat is used on. Grep will search for the exact text that we want from the big file. 

```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{kFUX4zgiohfPrxDji4OUrDzHXFm.QX3EDO0wCN1AzNzEzW}
```

## My Solve
Flag for the above challenge is pwn.college{kFUX4zgiohfPrxDji4OUrDzHXFm.QX3EDO0wCN1AzNzEzW}


# Comparing Files
As stated in the challenge itself, we are comparing files to find out the different text in them. The goal is to compare the files and then obtain the flag from the file which contains the real one. This happens as when we compare the two files the difference in content among the two files is that one of them has the real one. We do this by using the diff command.

```
hacker@commands~comparing-files:~$ /challenge/decoys_only.txt
bash: /challenge/decoys_only.txt: Permission denied
hacker@commands~comparing-files:~$ /challenge/decoys_and_real.txt
bash: /challenge/decoys_and_real.txt: Permission denied
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
74a75
```

## My Solve
The flag for the above challenge is pwn.college{EOoNLx5lUnx3_H60ex2HboQBX7J.01MwMDOxwCN1AzNzEzW}



# Listing Files
In this challenge we learn the ls function which is basically to list out the files in all the directories. This challenge just makes us execute this to understand how it works.

```
hacker@commands~listing-files:~$ ls
 challenge   flag   home   key   key.pub   not-the-flag  '~'
hacker@commands~listing-files:~$ /challenge
bash: /challenge: Is a directory
hacker@commands~listing-files:~$ ls /challenge
13259-renamed-run-29625  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/13259-renamed-run-29625
Yahaha, you found me! Here is your flag:
```



## My Solve 
The flag for the above challenge is pwn.college{MNtHPYiN4dWzeIiuEHbpJKfI57j.QX4IDO0wCN1AzNzEzW}


# Touching Files 
In this challenge, we need to learn how to create a new blank file which can be done by using the touch command. We have to create 2 new files using the touch command and then execute the /challenge/run command to obtain the flag

```
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
```

## My solve 
The flag for the above challenge is pwn.college{I-VYAukndeX9eKih3zc4JLs88tW.QXwMDO0wCN1AzNzEzW}



# Removing Files
Sometimes the files might be a lot and to clear it up, we have to use the rm command which can help in clearing or removing the files which arent required. We simply have to use rm file_name to remove the file we want to.

```
hacker@commands~removing-files:~$ ls
 challenge   delete_me   flag   home   key   key.pub   not-the-flag  '~'
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
```

## My Solve
The flag for the above challenge is pwn.college{8jHzvWvDwgyBabtNAlNxas9C6Sq.QX2kDM1wCN1AzNzEzW}



# Moving Files
In this challenge we learn how to move files, and we do this by using the mv command. We have to move /flag file into /tmp/hack-the-planet, and then run the /challenge/check command to obtain the flag

```
hacker@commands~moving-files:~$ ls
 challenge   flag   home   key   key.pub   not-the-flag  '~'
hacker@commands~moving-files:~$ ms /flag /tmp/hack-the-planet
bash: ms: command not found
hacker@commands~moving-files:~$ mv  /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
```

## My Solve
THe flag for the above challenge is pwn.college{AyfyWiz8YNt8tVKdjYRdzk4q7is.0VOxEzNxwCN1AzNzEzW}



# Hidden Files
Some files might be hidden in Linux and cant be accessed when we use ls (list). In those cases we can use ls -a which is used if we want to view files which are hidden. Those files are the ones which start with a " . "

```
hacker@commands~hidden-files:~$ ls
 challenge   flag   home   key   key.pub   not-the-flag  '~'
hacker@commands~hidden-files:~$ ls -a
 .    .bash_history   .config    .local      flag   key       not-the-flag
 ..   .cache          .lesshst   challenge   home   key.pub  '~'
hacker@commands~hidden-files:~$ /challenge/.local
bash: /challenge/.local: No such file or directory
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls
bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ ls -a
.           .flag-315662203424297  challenge  home   lib64   mnt  proc  sbin  tmp
..          bin                    dev        lib    libx32  nix  root  srv   usr
.dockerenv  boot                   etc        lib32  media   opt  run   sys   var
```

## My Solve
The flag for the above challenge is pwn.college{AyfyWiz8YNt8tVKdjYRdzk4q7is.0VOxEzNxwCN1AzNzEzW}



# An Epic Filesystem Quest
This was the longest and hardest challenge I faced amongst all the other challenges as we had to partially combine and use some of the other functions that we learnt from the previous challenges. Based on certain clues we have to choose a directory which may have the flag in it and then we can finally obtain. This challenge is kind of a summary of all the previous challenges ive faced.



# My solve
The flag for the above challenge is pwn.college{8Yc7TkHpXUxJ536ecsQixhM_a4k.QXwUDO0wCN1AzNzEzW}



# Making Directories
This challenge teaches us how to use the mkdir command which helps us make a directory, and its relatively simple. We run mkdir /tmp/pwn and make a college file using the touch command by specifying it in that directory (absolute path) and then we run the /challenge/run command which gives us the flag.

```
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ ls
bin  hsperfdata_root  tmp.4mK6TfTSUV
hacker@commands~making-directories:/tmp$ ls -a
.  ..  .crates.toml  .crates2.json  .dojo  bin  hsperfdata_root  tmp.4mK6TfTSUV
hacker@commands~making-directories:/tmp$ mkdir /tmp/pwn
hacker@commands~making-directories:/tmp$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ ls
college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
```

## My Solve
The flag for the above challenge is pwn.college{0_GfbxDjefeknXBn_BK48omc-ni.QXxMDO0wCN1AzNzEzW}



# Finding Files
This challenge involves us causing an error in the the command terminal by using the ls - /flag command which gives us the files that contain a flag but may not be the one that we are looking for. We have to use trial and error and use the cat function which will read the file and give us the one with the flag.

```
hacker@commands~finding-files:~$ / -name flag
bash: /: Is a directory
hacker@commands~finding-files:~$ / -nameflag
bash: /: Is a directory
hacker@commands~finding-files:~$ /-name flag
bash: /-name: No such file or directory
hacker@commands~finding-files:~$ find /-name flag
find: ‘/-name’: No such file or directory
flag
flag/flag
hacker@commands~finding-files:~$ cat flag/flag
```


## My solve 
The flag for the above challenge is pwn.college{UmG3SkHV6E6rG0AdNiyOWw0cB1D.QXyMDO0wCN1AzNzEzW}


# Linking Files 
As given verbatim on the challenge, the goal is to link two files. Reading one file wouldnt give us the flag and hence we have to link two files which will help us in directing the command to read the end file which is 
/flag /home/hacker/not-the-flag and to do this we use the ln -s command.

```
hacker@commands~linking-files:~$ ln -s
ln: missing file operand
Try 'ln --help' for more information.
hacker@commands~linking-files:~$ /flag
bash: /flag: Permission denied
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
```

## My Solve
The flag for the above challenge is pwn.college{kQ97rWuTQ5uWooOruGX2Ulj4Z_p.QX5ETN1wCN1AzNzEzW}













