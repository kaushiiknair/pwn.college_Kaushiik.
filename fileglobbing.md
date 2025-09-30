# File Globbing - Module 5

# Matching with *
In this challenge we learn how to use the * to prevent writing the whole command. It is similar to tricking the command terminal into running the program
 
 ```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
```

## My Solve
The flag for the above challenge is pwn.college{k4haTGpSYTkYAYhwV-x5Ulw7W6-.QXxIDO0wCN1AzNzEzW}



# Matching with ?
Similar to the previous challenge but we cant use c or l and we have to use a '?' instead of a '*'

```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
```

## My Solve 
The flag for the above challenge is pwn.college{snU4wvxdGMwbgaPgP3Bf99QfA8q.QXyIDO0wCN1AzNzEzW}



# Matching with []
For this challenge the [] is meant to be a sort of range for where the files are. For example for the below code, [bash] was give as it matches file_b, file_a, file_s, file_h

```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ ls
file_a  file_d  file_g  file_j  file_m  file_p  file_s  file_v  file_y
file_b  file_e  file_h  file_k  file_n  file_q  file_t  file_w  file_z
file_c  file_f  file_i  file_l  file_o  file_r  file_u  file_x
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
```

## My Solve
The flag for the above challenge is pwn.college{I28zWzXemMGalEeCO1DobP6bZgq.QXzIDO0wCN1AzNzEzW}



# Matching paths with []
I've not understood this fully but im assuming that its asking us to run the command in such a way that the [bash] files output gets saved in another form called files

```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
```

## My Solve
THe flag for the above challenge is pwn.college{w5w0y5kQfAixxtkqs3dycNxvwXQ.QX0IDO0wCN1AzNzEzW}



# Multiple Globs
In this challenge we find out that we can use multiple globs, and it can still run the code

```
hacker@globbing~multiple-globs:~$ ls /challenge/files
amazing      educational  incredible  magical     queenly    uplifting   youthful
beautiful    fantastic    jovial      nice        radiant    victorious  zesty
challenging  great        kind        optimistic  splendid   wonderful
delightful   happy        laughing    pwning      thrilling  xenial
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run /*p
Your expansion did not expand to the requested files (happy optimistic pwning 
splendid uplifting).
Instead, it expanded to:
/tmp
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
```

# My Solve
The flag for the above challenge is pwn.college{cyI_SPasWitPmS6DmMDFzcwVD1b.0lM3kjNxwCN1AzNzEzW}



# Mixing Globs
The challenge is given so that we can get multiple outputs by using multiple globs such as the [] and the * as shown below.
It helps us in making the process of typing out the code short and precise

```
hacker@globbing~mixing-globs:/challenge/files$ ls
amazing      educational  incredible  magical     queenly    uplifting   youthful
beautiful    fantastic    jovial      nice        radiant    victorious  zesty
challenging  great        kind        optimistic  splendid   wonderful
delightful   happy        laughing    pwning      thrilling  xenial
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [epc]
Your expansion did not expand to the requested files (challenging, educational, 
pwning). Instead, it expanded to:
[epc]
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [epc]*
You got it! Here is your flag!
pwn.college{YoCO50_GuKE0vgk0WuidpfTMERm.QX1IDO0wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{YoCO50_GuKE0vgk0WuidpfTMERm.QX1IDO0wCN1AzNzEzW}



# Exclusionary Globbing
In this challenge, we are providing a condition to give us an output and this is done by either using ! or ^ (compatible with older shells).
It also shows us how we can utilise both brackets and ! together.

```
hacker@globbing~exclusionary-globbing:~$ ls /challenge/files
amazing      educational  incredible  magical     queenly    uplifting   youthful
beautiful    fantastic    jovial      nice        radiant    victorious  zesty
challenging  great        kind        optimistic  splendid   wonderful
delightful   happy        laughing    pwning      thrilling  xenial
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
```

## My Solve
The flag for the above challenge is pwn.college{0Dr_XYYWPfXLG6mkIl_Tet3OQtU.QX2IDO0wCN1AzNzEzW}



# Tab Completion
This challenge basically just makes us utilise the tab function which helps us autofill any of the files we want to upload

```
hacker@globbing~tab-completion:~$ cat /challenge/pwncollege​ 
pwn.college{0-4Ku2R-7FjUT7HN2PNpYu5uE_q.0FN0EzNxwCN1AzNzEzW}
```

## My Solve
THe flag for the above challenge is pwn.college{0-4Ku2R-7FjUT7HN2PNpYu5uE_q.0FN0EzNxwCN1AzNzEzW}



# Multiple Options for Tab Completion
## My Solve
The flag for the above challenge is 




# Tab Completion On Commands 
For this challenge we just type the initial letters 'pw' and then press tab to autofill it and then when we process the code the flag is obtained

```
hacker@globbing~tab-completion-on-commands:~$ pwncollege-7095 
Correct! Here is your flag:
pwn.college{wp7jijc-3Sk1oAERFp5U_9e5OEF.0VN0EzNxwCN1AzNzEzW}
```

## My Solve 
The flag for the above solution is pwn.college{wp7jijc-3Sk1oAERFp5U_9e5OEF.0VN0EzNxwCN1AzNzEzW}











