# Pondering Paths - Module 2

# The Root
For this challenge we have a filesystem that starts with a / which contains different other directories, files etc. in it.
All we have to do is invoke the / along with the program pwn which will give us the flag. This is basically establishing 
our understanding of absolute paths and how to trace back to files in the system.

## My Solve
The flag for the above challenge is pwn.college{0Gi7NrRkQOKLP6y9vOQq8AtJDaA.QX4cTO0wCN1AzNzEzW}

# Program and Absolute Paths
In this challenge, we take it a step higher in difficulty by having the challenge directory in the root directory which when we run
/challenge/run gives us the flag

## My Solve
The flag for the above challenge is pwn.college{8PZOZfRH7g-i_qrErfqmiVVJJHU.QX1QTN0wCN1AzNzEzW}

# Position Thy Self
In this challenge we use the change directory (cd) command that helps us change the directory, and locate the files efficiently as in many directories
there are many files. In this case I initially ran the /challenge/run and found out the path which i had to locate the file from and hence i found the flag

## My Solve
THe flag for the above challenge is pwn.college{sVDumzynlB7NuKA_nWvdKPgZV3r.QX2QTN0wCN1AzNzEzW}

# Position Elsewhere
It is similar to the previous challenge but the only thing that differs is that the " ~ " prompt gives us the path that
we need to obtain the flag from. Similarly we have to use the /challenge/run program to find the flag

## My Solve
The flag for the above challenge is pwn.college{cCLEgz1EInnm4kOYam5x7DaRdUA.QX3QTN0wCN1AzNzEzW}

# Position Yet Elsewhere
In this challenge, which is similar to the Position Elsewhere challenge, we use the /challenge/run to find out the new prompt to locate the flag.
We change the directory before using cd, to help us locate the flag with better ease.

## My Solve
THe flag for the above challenge is pwn.college{AnRU3ohNRJnYFYLolaeUn2gnUtY.QX4QTN0wCN1AzNzEzW}

# Implicit Relative Paths, from /
In this challenge we get the difference between the absolute paths and relative paths. One key difference is that relative paths
dont start with a root, for example "/". 

## My Solve
The flag for the above challenge is pwn.college{wolcA-EtDr6wX20d3sLC-qfvlTH.QX5QTN0wCN1AzNzEzW}
