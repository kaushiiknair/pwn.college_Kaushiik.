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

## My Solve 
The flag for the aboce challenge is pwn.college{IMa_9_EI3yMVrCPRe4vCRtVl4_r.0VNxEzNxwCN1AzNzEzW}

















