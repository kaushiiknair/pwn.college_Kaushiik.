# Digesting Documentation - Module 4

# Learning Documentation
In this challenge we use the /challenge/challenge command along with the --give flag to give it an arguement to help us find the flag.
This allows us to obtain the flag for this challenge
```
hacker@man~learning-from-documentation:~$ /challenge/challenge
Incorrect usage! You must pass an argument to me (read the challenge 
description for details).
hacker@man~learning-from-documentation:~$ ls -a
 .    .bash_history   .config    .local      flag   key       not-the-flag
 ..   .cache          .lesshst   challenge   home   key.pub  '~'
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
```

## My Solve
The flag for the above challenge is pwn.college{IPqdJJqTuNnrzwrjNe7PX3THQXb.QX0ITO0wCN1AzNzEzW}



# Learning Complex Usage
For this challenge we use the /challenge/challenge --printfile /challenge/DESCRIPTION.md command to first print out the description
and then simply use the same command but append the end with flag which should give us the result as the goal for this challenge
is just to ensure that we know how to present arguements which are complex

```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile
You must pass a file for --printfile to read!
hacker@man~learning-complex-usage:~$ /challenge/challenge
Incorrect usage! You must pass an argument to me (read the challenge 
description for details).
hacker@man~learning-complex-usage:~$ /challenge/challenge --printflag
Incorrect usage! You passed the wrong argument (read the challenge description 
for details).
hacker@man~learning-complex-usage:~$ /challenge/challenge--printfile
bash: /challenge/challenge--printfile: No such file or directory
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /challenge/DESCRIPTION.md
Correct argument! Here is the /challenge/DESCRIPTION.md file:
While using most commands is straightforward, the usage of some commands can get quite complex.
For example, the arguments to commands like `sed` and `awk`, which we're definitely not getting into right now, are entire programs in an esoteric programming language!
Somewhere on the spectrum between `cd` and `awk` are commands that take arguments to their arguments...

This sounds crazy, but you've already encountered this with the `find` level in [Basic Commands](/linux-luminarium/commands).
`find` has a `-name` argument, and the `-name` argument itself takes an argument specifying the name to search for.
Many other commands are analogous.

Here is this level's documentation for `/challenge/challenge`:

> Welcome to the documentation for `/challenge/challenge`! This program allows you to print arbitrary files to the terminal, when given the `--printfile` argument. The argument to the `--printfile` argument is the path of the flag to read. For example, `/challenge/challenge --printfile /challenge/DESCRIPTION.md` will print out the description of the level!

Given that documentation, go get the flag!
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
```

## My Solve
The flag for the above challenge is pwn.college{4uDo0CjK-L6VW9qEoYxzzKyIv-O.QX1ITO0wCN1AzNzEzW}



# Reading Manuals
In this challenge, we are using the man command which is short for manual. It gives us all sorts of information which would be related
to how some things work on the command terminal. We first use man challenge and rhen from there we get the secret optiion which is
vbuhup 485 to access the flag. We use it as /challenge/challenge --vbuhup 485.

```
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --vbuhup 485
```

## My Solve
The flag for the above challenge is pwn.college{QZvbGuMhLuHJK48UpC5Jbxy1K-O.QX0EDO0wCN1AzNzEzW}


# Searching Manuals
In this challenge, we use the command "man challenge" to go and find the flag using the / command which helps us in finding the flag by inputting /flag. Then it shows us that --gry gives the output of the flag and then we use /challenge/challenge --gry to obtain the flag after clicking q to escape from the manual

```
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --gry
Initializing...
```

## My Solve 
The flag for the above challenge is pwn.college{UfNY0W4x9olw21nsf51k3sCPZWW.QX1EDO0wCN1AzNzEzW}



# Searching For Manuals
In this challenge, we are using the man man command to find different ways to use other man commands and in this case man -k is used as shown below. When we run the program we get a code which we are to run with /challenge/challenge and then we will obtain our flag.

```
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k /challenge/challenge
sdbeyyzrah (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man sdbeyyzrah
hacker@man~searching-for-manuals:~$ /challenge/challenge --sdbeyy 592
```
## My Solve 
THe flag for the above challenge is pwn.college{AsdM_be-5WCyFyRz929r3aPDHhA.QX2EDO0wCN1AzNzEzW}



# Helpful Programs
In this challenge we are using the help command to print a value for us by using the '-p' arguement and then using the '-g' arguement by inserting the value next to it and running it alongside /challenge/challenge to receive the flag

```
hacker@man~helpful-programs:~$ /challenge/challenge -h
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 779
hacker@man~helpful-programs:~$ /challenge/challenge -g 779
```

## My Solve 
The flag for the above challenge is pwn.college{k77RkJd9WuLKYjZAIXt4bZAo7qU.QX3IDO0wCN1AzNzEzW}



# Help for Builtins
We once again use the help command to be presented with different options and this is all "builtin" . After getting the code we use it as shown below. 

```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "EDlubPdP".
hacker@man~help-for-builtins:~$ challenge --secret EDlubPdP
Correct! Here is your flag!
```

## My Solve
The flag for the challenge is pwn.college{EDlubPdP3afpIxRk8HhorbwzXL9.QX0ETO0wCN1AzNzEzW}






# Searching For Manuals

