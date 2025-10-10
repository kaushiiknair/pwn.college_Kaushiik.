# Chaining Commands - Module 12


# Chaining with Semicolons

In this challenge we are learning how to chain the command using semicolon
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{U1yox1c9-BWVL5YhZX-EkM4uSOc.QX1UDO0wCN1AzNzEzW}
```

## My Solve 
The flag for the above challenge is pwn.college{U1yox1c9-BWVL5YhZX-EkM4uSOc.QX1UDO0wCN1AzNzEzW}



# Building On Success

We learn how to use the && command as it helps us in running the second command only when the first command runs.
```
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: pwn.college{8IJTyoClgsfQFsLAUSk-O6ZpLyX.0lM0MDOxwCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{8IJTyoClgsfQFsLAUSk-O6ZpLyX.0lM0MDOxwCN1AzNzEzW}



# Handling Failure 

We learn how to chain commands using ||, but unlike && it executes the second one only if the first one fails.
```
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{k5oGUyrQDLdOsjU7Ov2Q6hz4EfX.01M0MDOxwCN1AzNzEzW}

```

## My Solve
The flag for the above challenge is pwn.college{k5oGUyrQDLdOsjU7Ov2Q6hz4EfX.01M0MDOxwCN1AzNzEzW}



# Your First Shell Script

In this challenge, we are using the nano x.sh command to run the further commands in the shell which will be then executed when we use bash x.sh.
```
kaushiik-s-nair@kaushiik-s-nair-HP-OmniBook-5-Flip-Laptop-14-fp0xxx:~$ ssh -i key hacker@dojo.pwn.college
Connected!                                                                        
hacker@chaining~your-first-shell-script:~$ /challenge/pwn
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
I appreciate the enthusiasm, but you can stop after the second command! 
Instead, you're trying to run 'bash x.sh'...
hacker@chaining~your-first-shell-script:~$ /challenge/pwn
hacker@chaining~your-first-shell-script:~$ /challenge/college
hacker@chaining~your-first-shell-script:~$ bash x.sh
I appreciate the enthusiasm, but you can stop after the second command! 
Instead, you're trying to run 'bash x.sh'...
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{oqgIF3_qjs7goLLdyzqQ60l9do_.QXxcDO0wCN1AzNzEzW}

```

## My Solve 
The flag for the above challenge is pwn.college{oqgIF3_qjs7goLLdyzqQ60l9do_.QXxcDO0wCN1AzNzEzW}



# Redirecting Script Output 

In this challenge we are just learning how to use the bash x.sh command the piping function together, whcih will help us achieve the complete solution i.e. the flag.

```
hacker@chaining~redirecting-script-output:~$ nao out.sh
bash: nao: command not found
hacker@chaining~redirecting-script-output:~$ nano out.sh
hacker@chaining~redirecting-script-output:~$ /challenge/solve | nano out.sh
Standard input is not a terminal
^C   
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{0rukfCT1ra1JSrlKTlTAmhl5iTE.QX4ETO0wCN1AzNzEzW}
```


## My Solve 
The flag for the above challenge is pwn.college{0rukfCT1ra1JSrlKTlTAmhl5iTE.QX4ETO0wCN1AzNzEzW}



# Executable Shell Scripts



```
hacker@chaining~executable-shell-scripts:~$ /cha;;enge/solve
bash: syntax error near unexpected token `;;'
hacker@chaining~executable-shell-scripts:~$ /challenge/solve
You must make a shellscript in your home directory that will launch 
/challenge/solve, make it executable, and invoke it without explicitly 
specifying 'bash'!
hacker@chaining~executable-shell-scripts:~$ nano x.sh
hacker@chaining~executable-shell-scripts:~$ ls -l
total 56
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
-rw-r--r-- 1 hacker hacker  35 Oct 10 15:37  out.sh
-rw------- 1 hacker hacker   0 Sep 30 15:20  overwrites
-rw------- 1 hacker hacker   0 Sep 30 15:20  saves
-rw------- 1 hacker hacker   7 Sep 30 12:00  stdout
-rw------- 1 hacker hacker   0 Oct  8 12:55  test-file
-rw------- 1 hacker hacker 437 Sep 30 15:20  the-flag
-rw-r--r-- 1 hacker hacker  18 Oct 10 15:44  x.sh
-rw------- 1 root   hacker  60 Sep 30 09:47 '~'
hacker@chaining~executable-shell-scripts:~$ ./x.sh
bash: ./x.sh: Permission denied
hacker@chaining~executable-shell-scripts:~$ chmod ugo+x x.sh
hacker@chaining~executable-shell-scripts:~$ x.sh
bash: x.sh: command not found
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{IZRTayBvZVxChhzf38YpGuBNco7.QX0cjM1wCN1AzNzEzW}

```


## My Solve 
THe flag for the above solution is pwn.college{IZRTayBvZVxChhzf38YpGuBNco7.QX0cjM1wCN1AzNzEzW}



# Understanding Shebangs

In this challenge, we are learning how to use shebangs which is going to the shell and inputting #!/bin/bash.

```
hacker@chaining~understanding-shebangs:~$ nano /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod ugo+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /home/hacker/solve.sh
/home/hacker/solve.sh: line 1: /bin/bash./script.sh: No such file or directory
hacker@chaining~understanding-shebangs:~$ /challenge/run
Error: /home/hacker/solve.sh doesn't start with a proper shebang!
The first line should be: #!/bin/bash
There's no shebang at all in your script.
hacker@chaining~understanding-shebangs:~$ nano /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod ugo+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /home/hacker/solve.sh
bash: /home/hacker/solve.sh: cannot execute: required file not found
hacker@chaining~understanding-shebangs:~$ nano /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ nano /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod ugo+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /home/hacker/solve.sh
bash: /home/hacker/solve.sh: cannot execute: required file not found
hacker@chaining~understanding-shebangs:~$ nano /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ nano /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod ugo+x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /home/hacker/solve.sh
hack the planet!
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Your script did not give the expected output.
Expected: hack the planet
Got: hack the planet!
hacker@chaining~understanding-shebangs:~$ nano /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /home/hacker/solve.sh
hack the planet
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{cnPyK0zapln-8o6o84kz0gHhW2s.0VOzMDOxwCN1AzNzEzW}
```

## My Solve 
The flag for the above challenge is pwn.college{cnPyK0zapln-8o6o84kz0gHhW2s.0VOzMDOxwCN1AzNzEzW}



# Scripting With Arguements 
In this challenge we are slowly getting adapted to using the shell to run commands which are going on in the background.
This is done by using arguements together with the nano command and obtaining the flag

```
hacker@chaining~scripting-with-arguments:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Not quite right!
Expected: college_VVwYqMXuf4 pwn_qHFSXFal7s
Got: First Arguement: college_VVwYqMXuf4
Second Arguement: pwn_qHFSXFal7s
hacker@chaining~scripting-with-arguments:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Not quite right!
Expected: college_vpVGHPGkF1o pwn_VZTKCg3twqk
Got: First Arguement: college_vpVGHPGkF1o pwn_VZTKCg3twqk
hacker@chaining~scripting-with-arguments:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{IVwIruK68ROmm6Wvx8fqSxEkQHu.0VNzMDOxwCN1AzNzEzW}
```
## My Solve
The flag for the above challenge is pwn.college{IVwIruK68ROmm6Wvx8fqSxEkQHu.0VNzMDOxwCN1AzNzEzW}



# Scripting with conditionals

Similar to the previous challenges but in this case we are applying certain coditions and those include using [] and if, fi commands


```
hacker@chaining~scripting-with-conditionals:~$ nano /home/hacker/solve.sh 
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Test failed for input 'pwn'
Expected: 'college'
Got: '/home/hacker/solve.sh: line 3: [pwn: command not found'
hacker@chaining~scripting-with-conditionals:~$ nano /home/hacker/solve.sh 
hacker@chaining~scripting-with-conditionals:~$ nano /home/hacker/solve.sh 
hacker@chaining~scripting-with-conditionals:~$ nano /home/hacker/solve.sh 
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{s6bdFZ4-qFUYbN46p3RNgYlABwA.0lNzMDOxwCN1AzNzEzW}

```

## My Solve 
The flag for the above challenge is pwn.college{s6bdFZ4-qFUYbN46p3RNgYlABwA.0lNzMDOxwCN1AzNzEzW}



# Scripting With Default Cases

Similar to the baove challenge we are using conditions but in this case we are using default cases 
```
hacker@chaining~scripting-with-default-cases:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{EHeV-Kym5sGReSgWol0LhiGcGrS.01NzMDOxwCN1AzNzEzW}
```

```
  GNU nano 8.4                                                                        /home/hacker/solve.sh                                                                                   
#!/bin/bash

if [ "$1" = pwn ]
then

     echo "college"

else

   echo "nope"
fi
```


## My Solve
The flag for the above challenge is pwn.college{EHeV-Kym5sGReSgWol0LhiGcGrS.01NzMDOxwCN1AzNzEzW}



# Scripting With Multiple Conditions

In this challenge we are learning how to give different cases for the output by utlisiing the elif, if and then function,
read
```
hacker@chaining~scripting-with-multiple-conditions:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Test failed for input 'hack'
Expected: 'the planet'
Got: '/home/hacker/solve.sh: line 3: [: hack==: unary operator expected
unknown'
hacker@chaining~scripting-with-multiple-conditions:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Test failed for input 'hack'
Expected: 'the planet'
Got: '/home/hacker/solve.sh: line 3: [: hack==: unary operator expected
unknown'
hacker@chaining~scripting-with-multiple-conditions:~$ nano /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{I2lWJqQi5Cu1AqG7LliNrWeRnRB.0FOzMDOxwCN1AzNzEzW}
```

```
  GNU nano 8.4                                                                        /home/hacker/solve.sh                                                                                   


if [ "$1" == "hack" ]
then
    echo "the planet"
elif [ "$1" == "pwn" ]
then
    echo "college"
elif [ "$1" == "learn" ]
then
    echo "linux"
else
    echo "unknown"
fi
```


## My Solve 
The flag for the above challenge is pwn.college{I2lWJqQi5Cu1AqG7LliNrWeRnRB.0FOzMDOxwCN1AzNzEzW}



# Reading Shell Scripts 

THis challenge enables us to assign a password and then use that password from the shell to access the file which contained the flag.

```
kaushiik-s-nair@kaushiik-s-nair-HP-OmniBook-5-Flip-Laptop-14-fp0xxx:~$ ssh -i key hacker@dojo.pwn.college
Connected!                                                                        
hacker@chaining~reading-shell-scripts:~$ nano /challenge/run
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
	echo "CORRECT! Your flag:"
	cat /flag
else
	echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ read GUESS

hacker@chaining~reading-shell-scripts:~$ nano /challenge/run
hacker@chaining~reading-shell-scripts:~$ /challenge/run/sh
bash: /challenge/run/sh: Not a directory
hacker@chaining~reading-shell-scripts:~$ /challenge/run/.sh
bash: /challenge/run/.sh: Not a directory
hacker@chaining~reading-shell-scripts:~$ /challenge/run.sh
bash: /challenge/run.sh: No such file or directory
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
	echo "CORRECT! Your flag:"
	cat /flag
else
	echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ /challenge/run

Read the /challenge/run file to figure out the correct password!
hacker@chaining~reading-shell-scripts:~$ /challenge/run 
GUESS
Read the /challenge/run file to figure out the correct password!
hacker@chaining~reading-shell-scripts:~$ /challenge/run 
HACK THE planet
Read the /challenge/run file to figure out the correct password!
hacker@chaining~reading-shell-scripts:~$ /challenge/run 
hack the PLANET
CORRECT! Your flag:
pwn.college{IK_YY0AnQSeZekkZD_l9ZSLvZTg.0lMwgDOxwCN1AzNzEzW}
```


## My Solve
The flag for the above challenge is pwn.college{IK_YY0AnQSeZekkZD_l9ZSLvZTg.0lMwgDOxwCN1AzNzEzW}





