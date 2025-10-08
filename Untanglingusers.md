# Untangling Users - Module 10 

# Becoming Root With su
In this challenge, we are learning how to use the su command which helps in finding the root which in turn helps to find the flag.


```
kaushiik-s-nair@kaushiik-s-nair-HP-OmniBook-5-Flip-Laptop-14-fp0xxx:~$ ssh -i key hacker@dojo.pwn.college
Connected!                                                                        
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# ls
 COLLEGE   PWN   asdf   challenge   cmd1   flag   home   instructions   key   key.pub   myflag   not-the-flag   overwrites   saves   stdout   test-file   the-flag  '~'
root@users~becoming-root-with-su:/home/hacker# cat flag
cat: flag: Is a directory
root@users~becoming-root-with-su:/home/hacker# cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{cg2W2JUueuI5NCA6QZbRwFZbzad.QX3YTN0wCN1AzNzEzW}

root@users~becoming-root-with-su:/home/hacker# cat not-the-flag
pwn.college{40UXd90zxzZsLX4Yf3a3AoHfsQq.QX1UDN1wCN1AzNzEzW}


```

## My Solve 
The flag for the above challenge is pwn.college{40UXd90zxzZsLX4Yf3a3AoHfsQq.QX1UDN1wCN1AzNzEzW}



# Others with su
This challenge shows us that the su will start a root shell, and then we use that to switch the user and then we get the flag after running the challenge.


```
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{8hNjDp0I_uChR-3gegvP-TGjPZk.QX2UDN1wCN1AzNzEzW}

```

## My Solve
The flag for the above challenge is pwn.college{8hNjDp0I_uChR-3gegvP-TGjPZk.QX2UDN1wCN1AzNzEzW}



# Cracking Passwords 
For this challenge we are trying to find the correct password or the correct login for zardus. This is done by making the home directory as zardus which would allow us to access the shadow leak file and 
then be able to access the password.

```
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:01 14% 1/3 0g/s 254.8p/s 254.8c/s 254.8C/s zardus@..Zardusg
0g 0:00:00:02 28% 1/3 0g/s 246.1p/s 246.1c/s 246.1C/s sudraz!..bzardus
0g 0:00:00:03 35% 1/3 0g/s 248.5p/s 248.5c/s 248.5C/s zzardus99999..Ozardus
0g 0:00:00:04 48% 1/3 0g/s 251.4p/s 251.4c/s 251.4C/s Mrz99999..zArDuS99999
0g 0:00:00:05 59% 1/3 0g/s 257.9p/s 257.9c/s 257.9C/s Zardus9999991..9999979
0g 0:00:00:06 72% 1/3 0g/s 261.3p/s 261.3c/s 261.3C/s 1999991..z9999961
0g 0:00:00:08 79% 1/3 0g/s 256.3p/s 256.3c/s 256.3C/s Zardus33..z99999000
0g 0:00:00:09 85% 1/3 0g/s 254.8p/s 254.8c/s 254.8C/s Zardus1111..z99999123456
0g 0:00:00:10 93% 1/3 0g/s 254.3p/s 254.3c/s 254.3C/s zardus999992002..zardus1963
0g 0:00:00:11 99% 1/3 0g/s 256.0p/s 256.0c/s 256.0C/s zardus999991915..999991900
0g 0:00:00:12 0% 2/3 0g/s 256.1p/s 256.1c/s 256.1C/s lacrosse..pumpkin
0g 0:00:00:13 0% 2/3 0g/s 258.5p/s 258.5c/s 258.5C/s brenda..keith
0g 0:00:00:14 0% 2/3 0g/s 260.0p/s 260.0c/s 260.0C/s bigdog..francesco
0g 0:00:00:15 0% 2/3 0g/s 260.0p/s 260.0c/s 260.0C/s meggie..seattle
0g 0:00:00:16 0% 2/3 0g/s 261.6p/s 261.6c/s 261.6C/s billy1..december
0g 0:00:00:17 0% 2/3 0g/s 262.6p/s 262.6c/s 262.6C/s keller..nation
0g 0:00:00:18 0% 2/3 0g/s 263.8p/s 263.8c/s 263.8C/s susan1..121212
aardvark         (zardus)
1g 0:00:00:22 100% 2/3 0.04545g/s 264.6p/s 264.6c/s 264.6C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su
WARNING: you are invoking 'su' without specifying a user. This will default to 
the 'root' user, which is not achievable in this challenge.
Password: 
hacker@users~cracking-passwords:~$ su zardus
Password: 
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{USr7PGRnWm_yCItE1TQcJZZcnGk.QX3UDN1wCN1AzNzEzW}
```


## My Solve 
The flag for the above challenge is pwn.college{USr7PGRnWm_yCItE1TQcJZZcnGk.QX3UDN1wCN1AzNzEzW}



# Using Sudo
For the aboce challenge, we are using sudo to obtain the flag file without entering the password for the rootfile or any other user.
It makes it easier then su to access the flag file.

```
hacker@users~using-sudo:~$ sudo
usage: sudo -h | -K | -k | -V
usage: sudo -v [-AknS] [-g group] [-h host] [-p prompt] [-u user]
usage: sudo -l [-AknS] [-g group] [-h host] [-p prompt] [-U user] [-u user] [command]
usage: sudo [-AbEHknPS] [-r role] [-t type] [-C num] [-g group] [-h host] [-p prompt] [-T timeout] [-u user] [VAR=value] [-i|-s] [<command>]
usage: sudo -e [-AknS] [-r role] [-t type] [-C num] [-g group] [-h host] [-p prompt] [-T timeout] [-u user] file ...
hacker@users~using-sudo:~$ sudo ls
 COLLEGE   PWN	 asdf   challenge   cmd1   flag   home	 instructions   key   key.pub   myflag	 not-the-flag   overwrites   saves   stdout   test-file   the-flag  '~'
hacker@users~using-sudo:~$ sudo myflag
sudo: myflag: command not found
hacker@users~using-sudo:~$ sudo cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{cg2W2JUueuI5NCA6QZbRwFZbzad.QX3YTN0wCN1AzNzEzW}

hacker@users~using-sudo:~$ sudo cat not-the-flag
pwn.college{MhmjoGuxVvlVw4wNdXrfcWv0kge.QX4UDN1wCN1AzNzEzW}

```

## My Solve 
THe flag for the above challenge is pwn.college{MhmjoGuxVvlVw4wNdXrfcWv0kge.QX4UDN1wCN1AzNzEzW}







