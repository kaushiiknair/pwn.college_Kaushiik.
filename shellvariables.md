# Shell Variables

# Printing Variables
We use the $ to prepend the variables

```
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{8I1LVVk1_bk24hs-00fWuOUoSc9.QX3UTN0wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{8I1LVVk1_bk24hs-00fWuOUoSc9.QX3UTN0wCN1AzNzEzW}



# Setting Variables
We can use = to set the variables for the command to be executed

```
hacker@variables~setting-variables:~$ PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{M2DDw2fPlaH48S0Y3t0baucW_Rq.QX5UTN0wCN1AzNzEzW}
```

## My Solve 
The flag for the above challene is pwn.college{M2DDw2fPlaH48S0Y3t0baucW_Rq.QX5UTN0wCN1AzNzEzW}



# Multi Word Variables
In this challenge we use "" to create a single token for the command to execute

```
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{oO6jzNHT67gklRJb27HLhI-gFhD.QXwYTN0wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{oO6jzNHT67gklRJb27HLhI-gFhD.QXwYTN0wCN1AzNzEzW}



# Exporting Variables
We can open mini shells to execute commands and for executing the command we will have to import the variables by establishing a relation.

```
hacker@variables~exporting-variables:~$ PWN=COLLEGE
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ export PWN
You've set the PWN variable to the proper value!
hacker@variables~exporting-variables:~$ COLLEGE=PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ SH
bash: SH: command not found
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
hacker@variables~exporting-variables:~$ sh
sh-5.2$ /challenge/run PWN
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
job! Here is your flag:
pwn.college{4UBCtVcXSoz2DhPz_6HC24nG9Z0.QXyYTN0wCN1AzNzEzW}
```


## My Solve
The flag for the above challenge is pwn.college{4UBCtVcXSoz2DhPz_6HC24nG9Z0.QXyYTN0wCN1AzNzEzW}



# Printing Exported Variables
In this challenge we found out that env is a command that prints out all the variables that are exported

```
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=afae26c2bb966b8eb39038315d188dfdecd457a242538df83c0af904ed0f75ab
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{EQu2d0GYeu5tg3f81DP2NNTSOM5.QX4UTN0wCN1AzNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```


## My Solve
The flag for the above challenge is pwn.college{EQu2d0GYeu5tg3f81DP2NNTSOM5.QX4UTN0wCN1AzNzEzW}



# Storing Command Output
We learnt that we can store commands using a $() and enclosing whatever commands in the ()

```
hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out 
and submit it!
hacker@variables~storing-command-output:~$ echo %PWN
%PWN
hacker@variables~storing-command-output:~$ echo $PWN
pwn.college{IwssgrB7mKdrM6JGcFC9y23K7Bq.QX1cDN1wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{IwssgrB7mKdrM6JGcFC9y23K7Bq.QX1cDN1wCN1AzNzEzW}



# Reading Input
We can use the read command to input values for the given word

```
hacker@variables~reading-input:~$ read PWN
COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{QCizO9_PGGfUnOQ086ds9e-jm8Q.QX4cTN0wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{QCizO9_PGGfUnOQ086ds9e-jm8Q.QX4cTN0wCN1AzNzEzW}



# Reading Files
It helps in reading the files using the built in read command and also redirecting the input


```
hacker@variables~reading-files:~$ read PWN < flag
You invoked 'read', but it looks like you didn't redirect the 
/challenge/read_me file to it!
bash: read: read error: 0: Is a directory
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
```

## My Solve
The flag for the above challenge is pwn.college{gMK8jvYP-zumvCnmMyp9tW4iF1E.QXwIDO0wCN1AzNzEzW}








