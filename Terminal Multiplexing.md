# Terminal Multiplexing

# Launching Screen

Teaches us how to open the screen

```
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{UPksv7lgnBXI5kwakvNo84oBfV4.0VN4IDOxwCN1AzNzEzW}

```

## My Solve 
The flag for the above challenge is pwn.college{UPksv7lgnBXI5kwakvNo84oBfV4.0VN4IDOxwCN1AzNzEzW}



# Detaching and Attaching 

Teaches us how to detach and reattach on screen which will help us obtain the flag

```
hacker@terminal-multiplexing~launching-screen:~$ screen
[screen is terminating]
hacker@terminal-multiplexing~launching-screen:~$ 
Connected!                                                                        
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 139.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 139.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
[detached from 139.pts-0.terminal-multiplexing~detaching-and-attaching]
```

```
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Your screen session is still attached!

You need to detach from your screen session first.
Press Ctrl-A then d to detach.
hacker@terminal-multiplexing~detaching-and-attaching:~$
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{USL6OWiF47-RTTHcDYTNHeam7Aa.0lN4IDOxwCN1AzNzEzW}
Yes! Flag is: pwn.college{USL6OWiF47-RTTHcDYTNHeam7Aa.0lN4IDOxwCN1AzNzEzW}

```

## My Solve 
The flag for the above challenge is pwn.college{USL6OWiF47-RTTHcDYTNHeam7Aa.0lN4IDOxwCN1AzNzEzW}



# Finding Sessions
We learn how to use a new different command screen -ls to list all the screens that are running and then later attaching them.


```
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
	139.pts-0.terminal-multiplexing~detaching-and-attaching	(Remote or dead)
	144.session_051c6f3c0f5d91dd	(Detached)
	147.session_9ae0842254d2fe5c	(Detached)
	150.session_3464bc67c105c1f3	(Detached)
4 Sockets in /home/hacker/.screen.
hacker@terminal-multiplexing~finding-sessions:~$ screen -r 150
[detached from 150.session_3464bc67c105c1f3]
```

```
hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{Qsp_MgyGRdpF7i4ZvZ-URGODFXF.01N4IDOxwCN1AzNzEzW}
pwn.college{Qsp_MgyGRdpF7i4ZvZ-URGODFXF.01N4IDOxwCN1AzNzEzW}

```


## My Solve
The flag for the above challenge is pwn.college{Qsp_MgyGRdpF7i4ZvZ-URGODFXF.01N4IDOxwCN1AzNzEzW}



# Switching Windows 

```
hacker@terminal-multiplexing~switching-windows:~$ screen -r
[detached from 135.challenge_session]
```


```
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{gXE9TanHusYNr5l8jMD4Ig0bg43.0FO4IDOxwCN1AzNzEzW}
> MSG
Excellent work! You found window 0!
Here is your flag: pwn.college{gXE9TanHusYNr5l8jMD4Ig0bg43.0FO4IDOxwCN1AzNzEzW}

```

## My Solve
The flag for the above challenge is pwn.college{gXE9TanHusYNr5l8jMD4Ig0bg43.0FO4IDOxwCN1AzNzEzW}



# Detaching and Attaching (tmux)

```
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux ls
error connecting to /tmp/tmux-1000/default (No such file or directory)
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux -r
tmux: unknown option -- r
usage: tmux [-2CDlNuVv] [-c shell-command] [-f file] [-L socket-name]
            [-S socket-path] [-T features] [command [flags]]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 1)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux attach
[detached (from session 1)]
```

```
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Your tmux session is still attached!

You need to detach from your tmux session first.
Press Ctrl-B then d to detach.
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ cat /flag
cat: /flag: Permission denied
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{YmLpU9JMplaAX3-eFVwwTMaH74F.0VO4IDOxwCN1AzNzEzW}
Congratulations, here is your flag: pwn.college{YmLpU9JMplaAX3-eFVwwTMaH74F.0VO4IDOxwCN1AzNzEzW}
```

## My Solve 
The flag for the above challenge is pwn.college{YmLpU9JMplaAX3-eFVwwTMaH74F.0VO4IDOxwCN1AzNzEzW}



# Switching Windows (tmux)



```
│ hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG                                                                                                                          │
│ > Excellent work! You found window 0!                                                                                                                                                      │
│ > Here is your flag: pwn.college{kGbG2lsxun7x4CqhiMLq40ylTB3.0FM5IDOxwCN1AzNzEzW                                                                                                           │
│ }                                                                                                                                                                                          │
│ > MSG                                                                                                                                                                                      │
│ Excellent work! You found window 0!                                                                                                                                                        │
│ Here is your flag: pwn.college{kGbG2lsxun7x4CqhiMLq40ylTB3.0FM5IDOxwCN1AzNzEzW}
```



## My Solve
The flag for the above challenge is pwn.college{kGbG2lsxun7x4CqhiMLq40ylTB3.0FM5IDOxwCN1AzNzEzW} 





































