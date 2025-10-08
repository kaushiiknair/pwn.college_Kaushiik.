# Data Manipulation - Module 8



# Translating Characters
For the above challenge, the learning objective is tr which is translating the character provided in the first arguement with the other letter mentioned after tr.
it can handle multiple characters for editing

```
hacker@data~translating-characters:~$ echo OWB | tr O P
PWB
hacker@data~translating-characters:~$ echo OWN | tr O P
PWN
hacker@data~translating-characters:~$ echo PWM.COLLAGE | tr MA NE
PWN.COLLEGE
hacker@data~translating-characters:~$ /challenge/run
Your case-swapped flag:
PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZnXWcn1aZnZeZw}

hacker@data~translating-characters:~$ echo PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZnXWcn1aZnZeZw} | tr pwn college
 
PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZlXWcl1aZlZeZo}
hacker@data~translating-characters:~$ echo PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZnXWcn1aZnZeZw} | tr pwn.college
tr: missing operand after ‘pwn.college’
Two strings must be given when translating.
Try 'tr --help' for more information.
hacker@data~translating-characters:~$ echo PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZnXWcn1aZnZeZw} | tr PWN.COLLEGE pwn.college
pwn.college{iukiqYkXFQD5nwwHVlMxqwzu1tc.01mXeZnXwcn1aZnZeZw}
hacker@data~translating-characters:~$ echo PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZnXWcn1aZnZeZw} | tr PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZnXWcn1aZnZeZw} pwn.college{IUKIQyKxfqd5nwwhvLmXQwZU1Tc.01MxEzNxwCN1AzNzEzW
pwn.college{IUKIQyKxfqd5nwwhvLmXQwZU1Tc.01MxEzNxwCN1AzNzEzWW
hacker@data~translating-characters:~$ echo PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZnXWcn1aZnZeZw} | tr PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZnXWcn1aZnZeZw} pwn.college{IUKIQyKxfqd5nwwhvLmXQwZU1Tc.01MxEzNxwCN1AzNzEzW}
pwn.college{IUKIQyKxfqd5nwwhvLmXQwZU1Tc.01MxEzNxwCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is PWN.COLLEGE{iukiqYkXFQD5NWWHVlMxqWzu1tC.01mXeZnXWcn1aZnZeZw}



# Deleting Characters
In this challenge we are learning how to use the translate and delete function together by eliminating any other character in the code that we dont want.
In this case we eliminated the % and ^ from the flag 

```
hacker@data~deleting-characters:~$ echo PAWN | tr -d A
PWN
hacker@data~deleting-characters:~$ /challenge/run
Your character-stuffed flag:
p%w^n^%.%co%l^%le^g%e%{c^S^%E^%cp^%F^V^%f^o^%3E%V^%R^H^o^6^Z%h^%4^%l%l^K2^%f%S_%1^.%0%F^%N%x^%E^%z^N^%x^%w^%C%N1%A^z^%N^z^%E%z^%W}^%%
hacker@data~deleting-characters:~$ echo p%w^n^%.%co%l^%le^g%e%{c^S^%E^%cp^%F^V^%f^o^%3E%V^%R^H^o^6^Z%h^%4^%l%l^K2^%f%S_%1^.%0%F^%N%x^%E^%z^N^%x^%w^%C%N1%A^z^%N^z^%E%z^%W}^%% | tr -d % ^
 
tr: extra operand ‘^’
Only one string may be given when deleting without squeezing repeats.
Try 'tr --help' for more information.
hacker@data~deleting-characters:~$ echo p%w^n^%.%co%l^%le^g%e%{c^S^%E^%cp^%F^V^%f^o^%3E%V^%R^H^o^6^Z%h^%4^%l%l^K2^%f%S_%1^.%0%F^%N%x^%E^%z^N^%x^%w^%C%N1%A^z^%N^z^%E%z^%W}^%% | tr -d %^
pwn.college{cSEcpFVfo3EVRHo6Zh4llK2fS_1.0FNxEzNxwCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{cSEcpFVfo3EVRHo6Zh4llK2fS_1.0FNxEzNxwCN1AzNzEzW}



# Deleting Newlines
FOr this challenge we utilise the tr, -d and the /n commands to delete the newline spaces given for the flag. 

```
hacker@data~deleting-newlines:~$ /challenge/run
Your line-split flag: 
p
w
n
.
col
l
ege
{
I
Ma
_
9
_EI3
y
M
V
r
C
P
R
e
4vC
R
tVl
4_
r.0
VNx
E
z
N
xwC
N
1
A
z
N
zEzW}

hacker@data~deleting-newlines:~$ tr -d "\n"
^C
hacker@data~deleting-newlines:~$ /challenge/run | tr -d "\n"
Your line-split flag: pwn.college{IMa_9_EI3yMVrCPRe4vCRtVl4_r.0VNxEzNxwCN1AzNzEzW}
```

## My Solve 
The flag for the aboce challenge is pwn.college{IMa_9_EI3yMVrCPRe4vCRtVl4_r.0VNxEzNxwCN1AzNzEzW}



# Extracting the first line with head
In this challenge we are using the piping function and the head functio to connect the first 7 line in the /challenge/pwn to the /challenge/college. This gives us the complete flag and then we print it out

```
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn
Refusing to print codes to a terminal! Pipe me.
hacker@data~extracting-the-first-lines-with-head:~$ cat /challenge/pwn | head -n 7
#!/opt/pwn.college/bash

if [ -t 1 ]
then
  echo 'Refusing to print codes to a terminal! Pipe me.'
  exit 1
fi
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college 
Congratulations, you piped the right codes!
pwn.college{w6Mw17aAmy28kjtneX-QObdKaaw.0lNxEzNxwCN1AzNzEzW}
```


## My Solve
The flag for the above challenge is pwn.college{w6Mw17aAmy28kjtneX-QObdKaaw.0lNxEzNxwCN1AzNzEzW}



# Extracting specific sections of text 
In this challenge we utilise the piping function and then we use it along with the -d and cut function to extract a particular part of a file by using the -f (which helps in specifying the column) and then using the translate function to remove the spacings.

```
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run
31916 p
6117 w
21891 n
9326 .
18196 c
32446 o
10988 l
27763 l
9871 e
14280 g
25241 e
16237 {
3867 U
22516 P
2264 y
20990 k
32298 H
10890 e
31828 D
7624 f
26007 9
17707 o
5989 K
8641 t
12471 H
18695 -
2329 f
20345 J
7370 g
5245 D
20554 8
12161 M
26374 S
18124 I
3266 L
10417 j
7998 f
10652 u
21724 5
19313 .
3233 0
16061 1
7929 N
28693 x
31508 E
3453 z
9456 N
7021 x
14875 w
29428 C
1695 N
28377 1
31700 A
17688 z
24546 N
5420 z
4147 E
2787 z
27125 W
4246 }
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 1 /challenge/run | tr -d "\n"
#!/opt/pwn.college/bashcatdonehacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 /challenge/run | tr -d "\n"
#!/opt/pwn.college/bash/flagdonehacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{UPykHeDf9oKtH-fJgD8MSILjfu5.01NxEzNxwCN1AzNzEzW}
```


## My Solve
The flag for the above challenge is pwn.college{UPykHeDf9oKtH-fJgD8MSILjfu5.01NxEzNxwCN1AzNzEzW} 



# Sorting Data 
We use the sort function on the file to arrange all the flags in the file in an alphabetical order. This helps us in finding the flag which is mentioned to be at the bottom
```
hacker@data~sorting-data:~$ sort /challenge/flags.txt
ovn.cnlkefe{sYAmdiNGz2hGHbGhJJyTrlh3-bX.0EM0MDNwwCN0AyNzDyW}
owm.colldfe{rYAldiNGz2hFIbGhKIyUslh2-cY.0FL0MCNxvCN0AzNzEzW}
owm.colldge{rYAmeiNGz2hGIcGhKJyUrlh2-cY.0FM0MDOwwBN0AzMzEyV}
owm.collegd{sYAmehMGy2iGIcGgKJyUslh3-cY.0FL0MDNxwCN1AzNzEyV}
owm.college{sYAleiNGz2iGIbGhKJyUskh3-cY.0FL0LCOxwCN1AzNzEzW}
owm.college{sYAmdiMFy2iGIcGhKJxUrlh3-cY.0FM0MCOwwCN0AzNzDzV}
own.boklegd{sYAlehNGz2iGIcFhKJyUskh3-cY.0FM0MDOxwBM1AzNzDzV}
own.bolkdgd{sYAleiNFz2hFIcGhKJyUslg2-cY.0EM0MDOxwBN1AzNzDzV}
own.cnllefe{rXAmeiMFz1iGIcGgJJyUrkh3-bY.0FM0MDOwwCM1AzNzDzW}
own.colkdge{sXAmeiMGy1iGHbGhKJyUslg3-cY.0EM0MCOwwCN0AzNzEzV}
own.colkefe{sYAmeiNGy2iGIcGhJIyUslh3-cY.0FM0LDNxwBN0AzNzEzW}
own.colkegd{sYAleiNGz2iGIcFhKJyUslh3-bX.0FL0MCNxwCM0AzNzEyW}
own.colldge{sYAmeiNGz2iGIcGgKJyUslh2-cY.0FM0MDOxwCM1AzNzEzW}
own.collefd{sYAleiNFz2iGIcFhKJyUrlh3-cY.0FL0MDNxwCN1AzNzEzW}
own.collefe{sYAmeiMGz2iGIcFhKJxUrlh2-cY.0FL0MDOxwCM1AyNzEzW}
own.college{rYAmdiNGz2hGIbFgKJyUskh3-cY.0FM0MCOxwCN1AzMzDzV}
own.college{rYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0MDOwwCN1AzNzEzW}
own.college{sXAleiNGz2hGIcGgKJyUrlh3-cX.0FM0MDOxwCN1AyNzEzW}
own.college{sYAmehNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCM1AzNzEzW}
pvm.bollege{sXAmeiMGz2iFHbGhKJxTrlh2-bY.0FL0LDOxwCN0AyMzDzW}
pvm.collefd{sYAmeiNFz2iGHcFgKJxUskh2-cY.0EM0LCNwwCN0AyNyEzW}
pvm.collefe{sYAmeiNGz2iGIbFhKJyUskg3-cY.0EM0LCOxvCN1AzNyEzW}
pvn.bnlkegd{sYAmeiNFz2iGIbFhKJyUslh3-cY.0FM0MDNxwCM0AzNzDyW}
pvn.cnkldfe{sYAmeiMGz2iGHcGhKJxTslh3-cY.0FM0MDNxvCM1AyNzDzV}
pvn.cnklegd{sXAmdhMFz1iFHbFhKJyUskh2-cY.0EM0MDNwwCN0AyMzEzV}
pvn.colkege{sXAmdiNFz1iGIcGhKJyTslh3-bY.0EM0MDOxvCN1AzMzEzW}
pvn.colldge{rXAmehNGz1hGIbGhKJxUslh3-cY.0FM0MDOxvBM0AzNzEzW}
pvn.colldge{rYAldiMFy2iGIcGhKJyUslg3-cY.0FL0MDOxwCN0AyNzEyW}
pvn.collefe{sXAleiNGz2iFIcFhKJyTskh3-cY.0FM0MDOxwCN0AzMyEzW}
pvn.college{rYAmeiNGz2iGIcGhKIyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pvn.college{sYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pwm.bolkege{sYAlehMGz2iGIcFhJIyTskh2-bY.0EL0MDOwwCN1AyMzEzW}
pwm.bolldfe{sYAlehNFz1hGIcGgJJyTslh2-cX.0FM0LDOxvCN1AyNzEyV}
pwm.cnkkege{sXAmeiNGy2hGIbGgKJyTslh3-cY.0FM0LDOxvCN0AzNzDyV}
pwm.cnllegd{rYAlehMGz2iFIbGhKIxUslg3-bY.0FM0MDOxwBN1AzNyEzV}
pwm.colkdfe{sYAmeiMFy1hGHcGhKJxUslh3-bY.0FM0MDNxvCM1AzNzEyW}
pwm.colldge{sYAmeiNGz2iGIbGhJJxUskh3-cY.0FM0MDOxwCN1AzNzEzV}
pwm.collefe{sYAmeiNGy1hGIcFgKIyUslg3-bY.0FM0MDOxvCN1AzNzEzW}
pwm.college{sYAlehNGz2iGHcGhKJyUslh3-cY.0FM0MDOxwCN1AzMzEyV}
pwm.college{sYAmehNFy2hGIcGhKIyUslh3-cY.0FM0MDOxwCN1AzNzEzV}
pwm.college{sYAmeiNGz1iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pwm.college{sYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pwn.bnlkege{sYAmeiNGz2iFIcGhKIxUslh2-bY.0EM0MCOxwBM1AzNzEzV}
pwn.bnllege{sYAmeiMFz2iGIcGhKIxUrlh3-cX.0FM0MDOwwBN1AzNyEyW}
pwn.bokldge{sYAmdiNGz2hFIcGhKJxUslh3-cX.0FM0MDOxwCN1AzNzEzW}
pwn.boklege{sXAmeiNFz2iGIcFhKJyUslh3-cY.0FL0MDOxwCN1AyNyEzW}
pwn.bolkegd{sXAmdiNGz2hFIcGgKJyUslg2-cY.0FL0MDOxvCN1AyNyEzV}
pwn.bolkege{sXAleiNGz2iGIcGhKJyTrkh3-cY.0FM0MDOxvCN1AzNzEzV}
pwn.bolldgd{sXAmeiNGz2iGIcGhKJyTrkh3-cY.0FM0LDOxwCN1AzNzEzV}
pwn.bolldge{sXAmeiNGy1iGIcGhKJyUslh3-bY.0FL0MDOwwCN1AzNzEzW}
pwn.bollegd{sYAmeiNFz2iGIcGhKJyUslh3-cY.0FM0MCNxwCM1AzNzEzW}
pwn.bollegd{sYAmeiNGy2iGIcGhKIyUslg3-cY.0FM0MDOwvCN1AzNzEzV}
pwn.bollege{sYAmeiNGz1iGIcGhKJyUslh3-cY.0FM0MCOxwCN1AzNzEzW}
pwn.cnkkefe{rYAmeiNFz1iFIbGgKJyTrkh2-cY.0EL0MDOxwBM0AzNzEzV}
pwn.cnkkege{rYAmdhNGy2iGIbGhKJyTslh3-cX.0FL0MCNwwCM1AzMzEzV}
pwn.cnkldfe{rYAmdhNGz2hGHbGhKJxTslg2-cX.0FL0LCOxvCM0AzNzEzW}
pwn.cnlkege{sXAldiNFz2iGIcGgJJxTskh3-cY.0FM0MDOxwCN1AyNzEzV}
pwn.cnlldge{sYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0LDOxwCN1AzNzEzW}
pwn.cnllege{rXAmeiNGz2iGIcGhKJxUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pwn.cnllege{sYAmehNGz2iGIcGhKJyUskh2-cX.0FM0MDOxwBN0AzMzEyW}
pwn.cnllege{sYAmeiNGy2iFIcGhJJyTslh3-cY.0FM0MDOwwCN1AzNzDzV}
pwn.cnllege{sYAmeiNGy2iGIcGhKJyUslh3-cY.0FM0MDOxvCN1AzNzEzW}
pwn.cnllege{sYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pwn.cokkefe{sXAmeiNFz1iGIcGhJJyUskh3-cX.0FM0MDOxwCN1AzNyDzW}
pwn.cokkegd{sYAleiNGz2iGIcGhKIyUslh3-cY.0FM0MDOxwCM1AyNzDzW}
pwn.cokldge{sXAmeiNGy2iGIcGgKJyUrlh3-cY.0FL0MDOxwCN1AzNzDzV}
pwn.coklegd{sXAmdhMGz2iGIbGgKIxUskh2-cY.0FM0LDOxwCM1AzNyDzW}
pwn.coklege{sYAmeiNGz2iFIcGhJJxUrlh3-cY.0FM0MDOxwCN1AyMzEzW}
pwn.coklege{sYAmeiNGz2iGIbGhKJxUslh3-cY.0FM0MDOxwCN0AzNzEzW}
pwn.colkegd{sXAmeiNGz1iGIbGhKJyUskh3-cY.0FM0MDNxwBN1AzNzEyW}
pwn.colkegd{sYAmehNGy2iGHcFhJJxUslg2-cX.0FM0MDNxvCN0AyMzDzW}
pwn.colkege{sYAmdiNGy2hGHcGhJJyTskh3-bY.0FM0MCOxwCM1AzNzDzV}
pwn.colkege{sYAmeiMGz2iGIcGhKJyTslg3-cX.0FM0MDOwwBN1AzNzEzW}
pwn.colkege{sYAmeiNGy2iFIcFhJJyUslh2-cY.0FM0MCOxwCN1AzNzEzW}
pwn.colldge{sYAleiNGy2iGIcGhKJyUslh3-cY.0FM0MDOwvCN0AzNzEzV}
pwn.collefe{sYAmehNGy1iGIcFgKIxUslg3-bY.0FM0MDOxwCN1AzNzEzW}
pwn.college{rYAmdiMGz1iGIcGgJJyUrlh3-cY.0FM0LDOxwBN1AzNzDzV}
pwn.college{rYAmdiNGz1iGIcGhJJyUrlh3-cY.0FM0MDOxwCN1AzNzEzV}
pwn.college{rYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pwn.college{sYAldiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pwn.college{sYAleiNGz2iGIcGhKJyUslg3-cY.0FM0MDOxwCN1AzNzEzW}
pwn.college{sYAleiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzDzW}
pwn.college{sYAleiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pwn.college{sYAmdiNGz2iGIcGhJJyUslh3-cY.0EM0MCOwvCN1AzNyEyW}
pwn.college{sYAmdiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
pwn.college{sYAmehNGz2iGIcGhKJyTslh3-cX.0FM0LDOxwCN1AzNzEzW}
pwn.college{sYAmeiNFz2iGIcGhKJyUslh2-cY.0FM0MDOxwBN1AzNzEzW}
pwn.college{sYAmeiNGy2iGHcGhJIyUslh3-cX.0FM0MDOwwCN1AzNzEzV}
pwn.college{sYAmeiNGy2iGIcGhKJyUslh3-cY.0FM0LDNxwCN1AzNzEzW}
pwn.college{sYAmeiNGz1iGIcGhKJxUslh3-cY.0FM0MDOxwCN1AzMzEzW}
pwn.college{sYAmeiNGz2iFIcFhKJyTslh3-cY.0FM0MDOxwCN1AyNzEzW}
pwn.college{sYAmeiNGz2iGHcGgKIyUrlh3-bY.0FM0MCOxwCN1AzNzDyW}
pwn.college{sYAmeiNGz2iGIcGhKJxUrlh3-cY.0FM0MDOxwCM0AzNyEzW}
pwn.college{sYAmeiNGz2iGIcGhKJyTslh3-cY.0FM0MDOxwCN1AzNyEzW}
pwn.college{sYAmeiNGz2iGIcGhKJyUrkh3-bY.0FM0MDOxvCN1AzNzDzW}
pwn.college{sYAmeiNGz2iGIcGhKJyUslh3-cX.0FM0MDOxwCN1AzNzEzW}
pwn.college{sYAmeiNGz2iGIcGhKJyUslh3-cY.0EM0MDOxwCN1AyNzEzW}
pwn.college{sYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0LDOwwCN1AzMzEzW}
pwn.college{sYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0MDNxwCN1AzMyEyW}
pwn.college{sYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN0AzNzEzV}
pwn.college{sYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
```


## My Solve 
The flag for the above challenge is pwn.college{sYAmeiNGz2iGIcGhKJyUslh3-cY.0FM0MDOxwCN1AzNzEzW}
























