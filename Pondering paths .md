# Pondering Paths - Module 2

# The Root
For this challenge we have a filesystem that starts with a / which contains different other directories, files etc. in it.
All we have to do is invoke the / along with the program pwn which will give us the flag. This is basically establishing 
our understanding of absolute paths and how to trace back to files in the system.

```
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
```

## My Solve
The flag for the above challenge is pwn.college{0Gi7NrRkQOKLP6y9vOQq8AtJDaA.QX4cTO0wCN1AzNzEzW}



# Program and Absolute Paths
In this challenge, we take it a step higher in difficulty by having the challenge directory in the root directory which when we run
/challenge/run gives us the flag

```
hacker@paths~program-and-absolute-paths:~$ /challenge
bash: /challenge: Is a directory
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
```

## My Solve
The flag for the above challenge is pwn.college{8PZOZfRH7g-i_qrErfqmiVVJJHU.QX1QTN0wCN1AzNzEzW}



# Position Thy Self
In this challenge we use the change directory (cd) command that helps us change the directory, and locate the files efficiently as in many directories
there are many files. In this case I initially ran the /challenge/run and found out the path which i had to locate the file from and hence i found the flag.

```
hacker@paths~position-thy-self:~$ cd /challenge/run
bash: cd: /challenge/run: Not a directory
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /usr/share/doc
hacker@paths~position-thy-self:/usr/share/doc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
```

## My Solve
THe flag for the above challenge is pwn.college{sVDumzynlB7NuKA_nWvdKPgZV3r.QX2QTN0wCN1AzNzEzW}



# Position Elsewhere
It is similar to the previous challenge but the only thing that differs is that the " ~ " prompt gives us the path that
we need to obtain the flag from. Similarly we have to use the /challenge/run program to find the flag

```
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/aarch64-linux-gnu/include/gnu directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /usr/aarch64-linux-gnu/include/gnu
hacker@paths~position-elsewhere:/usr/aarch64-linux-gnu/include/gnu$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
```

## My Solve
The flag for the above challenge is pwn.college{cCLEgz1EInnm4kOYam5x7DaRdUA.QX3QTN0wCN1AzNzEzW}



# Position Yet Elsewhere
In this challenge, which is similar to the Position Elsewhere challenge, we use the /challenge/run to find out the new prompt to locate the flag.
We change the directory before using cd, to help us locate the flag with better ease.

```
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /var/log directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /var/log
hacker@paths~position-yet-elsewhere:/var/log$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
```

## My Solve
THe flag for the above challenge is pwn.college{AnRU3ohNRJnYFYLolaeUn2gnUtY.QX4QTN0wCN1AzNzEzW}



# Implicit Relative Paths, from /
In this challenge we get the difference between the absolute paths and relative paths. One key difference is that relative paths
dont start with a root, for example "/". 
```
hacker@paths~implicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
```

## My Solve
The flag for the above challenge is pwn.college{wolcA-EtDr6wX20d3sLC-qfvlTH.QX5QTN0wCN1AzNzEzW}



# Explicit Relative Paths, from /
In the previous challenge, the relative path we used is "naked". THe key difference is that in explicit relative paths we use " . " or " .. " at the beginning of the path, i.e. the path is stated. But in the case of implicit, the relative path doesn't use ./ , ../ etc. It is a slightly inferior version than explicit as explicit prevents any sort of mistake incase the path is complex. 

```
hacker@paths~explicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
```

## My Solve
The flag for the above challenge is pwn.college{MZPtEdEszZmwM1SXe4ONvDaKQyW.QXwUTN0wCN1AzNzEzW}



# Implicit Relative Path
This is similar to the previous challenges but just adds a safety factor of not being able to use the /challenge/run command. We just have to use the explicit relative path " . " to run the program. This explicitly tells Linux to execute the program in the current directory

```
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ run
bash: run: command not found
hacker@paths~implicit-relative-path:/challenge$ ./challenge/run
bash: ./challenge/run: No such file or directory
hacker@paths~implicit-relative-path:/challenge$ ./challenge/run
bash: ./challenge/run: No such file or directory
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
```

## My solve
THe flag for the above challenge is pwn.college{Mr1qbyEAXh2JMfvfvIvWDlXqzc0.QXxUTN0wCN1AzNzEzW}



# Home Sweet Home
In this challenge the home directory is /home/hacker 



## My Solve 
THe flag for the above challenge is pwn.college{gkpPzsnbm3mtXYHE-JU-DpNW_QA.QXzMDO0wCN1AzNzEzW}



