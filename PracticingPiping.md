# Practicing Piping - MODULE 6

# Redirecting Output
In this challenge, we are redirecting our output to a different output by using  " > " sign 

```
hacker@piping~redirecting-output:~$ echo hi > asdf
hacker@piping~redirecting-output:~$ cat asdf
hi
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
```
## My Solve 
THe flag for the above challenge is pwn.college{MECbD572rSUumKXqcThB6kl5LMg.QX0YTN0wCN1AzNzEzW}



# Redirecting More Output
This challenge is just a step above the previous challenge which is for redirecting larger output.

```
hacker@piping~redirecting-more-output:~$ /challenge/run flag > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{4YQBgI2rUXJZgeGppFOa_eOfmKU.QX1YTN0wCN1AzNzEzW}
```

## My Solve
The flag for the other challenge is pwn.college{4YQBgI2rUXJZgeGppFOa_eOfmKU.QX1YTN0wCN1AzNzEzW}



# Appending Output
Rather than the Truncate (>) arguement we use the append (>>) arguement to prevent us from overwriting the code.

```
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{cnr9xk2zk0hUWWdLRdxqeh7ju6K.QX3ATO0wCN1AzNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
```

## My Solve
The flag for the above challenge is pwn.college{cnr9xk2zk0hUWWdLRdxqeh7ju6K.QX3ATO0wCN1AzNzEzW}



# Redirecting Errors
This is similar concept of redirecting but this time using it on errors as mentioned in the challenge

```
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{cg2W2JUueuI5NCA6QZbRwFZbzad.QX3YTN0wCN1AzNzEzW}
```

## My Solve 
The flag for the above challenge is pwn.college{cg2W2JUueuI5NCA6QZbRwFZbzad.QX3YTN0wCN1AzNzEzW}



# Redirecting Input
In this challenge we are redirecting the PWN file as a standard input, which when read, submits the COLLEGE value, which is the flag

```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
```

## My Solve
The flag for the challenge is pwn.college{wJPT_thYLW_s3lI45gqej0P00zy.QXwcTN0wCN1AzNzEzW}



# Grepping Stored Results
In this challenge, we are redirecting the outpiut to /tmp/data.txt and then we grep for pwn (as it is the starting of our flag) which filters out the flag for us from that file

```
hacker@piping~grepping-stored-results:~$ /challenge/run > tmp/data.txt
bash: tmp/data.txt: No such file or directory
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn /tmp/data.txt
pwns
pwn
pwn.college{wQ5NMrS59ubuOzsJAhVavas7H8c.QX4EDO0wCN1AzNzEzW}
pwning
pwned
```

## My Solve
The flag for the above challenge is pwn.college{wQ5NMrS59ubuOzsJAhVavas7H8c.QX4EDO0wCN1AzNzEzW}



# Grepping Live Output
It is a better way than the previous method, as it does not save its results to the other file and it just compares the prompt from the left side to the right side and then gives us the final output. In this case the prompt was pwn so all outputs starting with pwn got printed

```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATN#ESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwns
pwn.college{UWe2WZZ17FwCiBCwoDo8ByuHz87.QX5EDO0wCN1AzNzEzW}
pwn
pwned
pwning
```

## My Solve
The flag for the above challenge is pwn.college{UWe2WZZ17FwCiBCwoDo8ByuHz87.QX5EDO0wCN1AzNzEzW}



# Grepping Output
We learn how to use a new arguement which is 2>& 1 and it is basically used to redirect stderr to stdout and then pipe the stdout and stderr to get the proper result which is the flag.

```
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{YZoWsZqxiS9usQGkq7_ES0cKTae.QX1ATO0wCN1AzNzEzW}
pwns
pwn
pwned
pwning
```

## My Solve
The flag for the above solution is pwn.college{YZoWsZqxiS9usQGkq7_ES0cKTae.QX1ATO0wCN1AzNzEzW}



# Filtering with grep -v
grep -v is an inverting output command which gives the final output as something that doesnt match. 

```
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{Qsbxz8ryZ38nn2D0UX5FGo5ZfFG.0FOxEzNxwCN1AzNzEzW}
hacker@piping~filtering-with-grep-v:~$ 
```

## My Solve
The flag for the above challenge is pwn.college{Qsbxz8ryZ38nn2D0UX5FGo5ZfFG.0FOxEzNxwCN1AzNzEzW}



# Duplicating Piped Data with TEE

```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee cmd1 | /challenge/college
Processing...
WARNING: you are overwriting file cmd1 with tee's output...
The input to 'college' does not contain the correct secret code! This code 
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the 
output of 'pwn' and figure out what the code needs to be.
hacker@piping~duplicating-piped-data-with-tee:~$ cat cmd1
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "kPW97V-9"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret kPW97V-9 | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{kPW97V-9y7blQnoUsZ2P6cBqE57.QXxITO0wCN1AzNzEzW}
```

## My Solve
THe flag for the above challenge is pwn.college{kPW97V-9y7blQnoUsZ2P6cBqE57.QXxITO0wCN1AzNzEzW}



# Process Substitution For Input


```
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
78a79
> pwn.college{YYnrmdT06qKRGX38iUwcJKWf1dw.0lNwMDOxwCN1AzNzEzW}
```

## My Solve
THe flag for the above challenge is > pwn.college{YYnrmdT06qKRGX38iUwcJKWf1dw.0lNwMDOxwCN1AzNzEzW}



# Writing to multiple programs

```
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/the) >(/challenge/planet)
This secret data must directly and simultaneously make it to /challenge/the and 
/challenge/planet. Don't try to copy-paste it; it changes too fast.
2046212684434009
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{cAQiSRZDnuDt0ybuRXdEiwaAKGq.QXwgDN1wCN1AzNzEzW}
```

## My Solve
THe flag for the above challenge is pwn.college{cAQiSRZDnuDt0ybuRXdEiwaAKGq.QXwgDN1wCN1AzNzEzW}



# Split piping stderr and stdout 


```
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack > >(/challenge/planet ) 2> >( /challenge/the )
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{MZYqn5x9hHmq3KIR2XbecHCYVvp.QXxQDM2wCN1AzNzEzW}
```

## My Solve
THe flag for the above challenge is pwn.college{MZYqn5x9hHmq3KIR2XbecHCYVvp.QXxQDM2wCN1AzNzEzW}



# Named Pipes
FOr this challenge we have to use two terminals to get the necessary flag, i.e final output. by using the cat /tmp/flag_fifo


```
Terminal 1

hacker@piping~named-pipes:~$ mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo! 
Bash will now try to open the FIFO for writing, to pass it as the stdout of 
/challenge/run. Recall that operations on FIFOs will *block* until both the 
read side and the write side is open, so /challenge/run will not actually be 
launched until you start reading from the FIFO!
^C
hacker@piping~named-pipes:~$ ^C
hacker@piping~named-pipes:~$ cat flag_fifo
cat: flag_fifo: No such file or directory
hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
^C
hacker@piping~named-pipes:~$ /challenge/run
The stdout of /challenge/run does not seem to point to a FIFO!
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo! 
Bash will now try to open the FIFO for writing, to pass it as the stdout of 
/challenge/run. Recall that operations on FIFOs will *block* until both the 
read side and the write side is open, so /challenge/run will not actually be 
launched until you start reading from the FIFO!
hacker@piping~named-pipes:~$ 


Temrminal 2
kaushiik-s-nair@kaushiik-s-nair-HP-OmniBook-5-Flip-Laptop-14-fp0xxx:~$ ssh -i key hacker@dojo.pwn.college
Connected!                                                                        
hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at 
/tmp/flag_fifo! Here is your flag:
pwn.college{Ey1f1kCBiDy2d3JZ6lWv88GxE_9.01MzMDOxwCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{Ey1f1kCBiDy2d3JZ6lWv88GxE_9.01MzMDOxwCN1AzNzEzW}
















