# Processes and Jobs  - Module 9


# Listing Process
In this challenge we learn how to use the ps aux ps -ef commands (ps - post snapshot) which shows the background work being done in the terminal. The goal is to find the correct challenge to run
and then run it, which should give us the flag

```
hacker@processes~listing-processes:~$ ps
    PID TTY          TIME CMD
    137 pts/0    00:00:00 ssh-entrypoint
    143 pts/0    00:00:00 bash
    153 pts/0    00:00:00 ps
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 11:52 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 11:52 ?        00:00:00 /run/dojo/bin/sleep 6h
root         132       1  0 11:52 ?        00:00:00 /challenge/1896-run-26386
root         135     132  0 11:52 ?        00:00:00 sleep 6h
hacker       137       0  0 11:52 pts/0    00:00:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       143     137  0 11:52 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       154     143  0 11:54 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   11:52   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0 231708  2560 ?        S    11:52   0:00 /run/dojo/bin/sleep 6h
root         132  0.0  0.0   4132  2560 ?        S    11:52   0:00 /challenge/1896-run-26386
root         135  0.0  0.0   2744  1600 ?        S    11:52   0:00 sleep 6h
hacker       137  0.0  0.0 231576  3520 pts/0    Ss   11:52   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       143  0.0  0.0 231940  4160 pts/0    S    11:52   0:00 /run/dojo/bin/bash --login
hacker       155  0.0  0.0 233600  3840 pts/0    R+   11:54   0:00 ps aux
hacker@processes~listing-processes:~$ /challenge/run
bash: /challenge/run: No such file or directory
hacker@processes~listing-processes:~$ /challenge/1896-run-26386
Yahaha, you found me! Here is your flag:
pwn.college{ssY4ZrPwSbzIUZDvUZgOJWkiGQ6.QX4MDO0wCN1AzNzEzW}
```

## My Solve
The flag for the aboce challenge is pwn.college{ssY4ZrPwSbzIUZDvUZgOJWkiGQ6.QX4MDO0wCN1AzNzEzW}



#  Killing Processes 
In this challenge we have to use the ps -e | grep sleep command to kill the file and that way we can run the /challenge to give us the flag.
We learn how to kill commands.

```
hacker@processes~killing-processes:~$ ps -e | grep sleep
    137 ?        00:00:00 sleep
hacker@processes~killing-processes:~$ /challenge/dont_run
^C
hacker@processes~killing-processes:~$ kill 137
hacker@processes~killing-processes:~$ /challenge/dont_run
^C        
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{MDGv_1r0YoEMSH6TXZOmCgrPbjy.QXyQDO0wCN1AzNzEzW}
```

## My Solve 
The flag for the above challenge is pwn.college{MDGv_1r0YoEMSH6TXZOmCgrPbjy.QXyQDO0wCN1AzNzEzW}



# Interrupting processes
In this challenge we learn how to use the ctrl-c command as a hotkey to stop the command from running or to exit forcefully.

```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{gSQI39Y4Wqe9UQBlscktDaxjzXw.QXzQDO0wCN1AzNzEzW}
```

## My Solve 
The flag for the above challenge is pwn.college{gSQI39Y4Wqe9UQBlscktDaxjzXw.QXzQDO0wCN1AzNzEzW}



# Killing Misbehaving processes
In this challenge we learn how to use the kill function to kill certain processes that might impact/ interfere with our work.

```
hacker@processes~killing-misbehaving-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.3  0.0   1056   640 ?        Ss   12:13   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.2  0.0 231708  2560 ?        S    12:13   0:00 /run/dojo/bin/sleep 6h
root         137  0.0  0.0   4132  1600 ?        S    12:13   0:00 /bin/bash /challenge/.init
root         138  0.0  0.0   4132  1600 ?        S    12:13   0:00 /bin/bash /challenge/.init
root         139  0.0  0.0   5204  3520 ?        S    12:13   0:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
root         140  0.0  0.0   2744  1600 ?        S    12:13   0:00 sleep 6h
root         141  0.0  0.0   2744  1600 ?        S    12:13   0:00 sleep 6h
hacker       142  0.4  0.0  13516  9280 ?        Ss   12:13   0:00 /usr/bin/python /challenge/decoy
hacker       144  0.3  0.0 231576  3520 pts/0    Ss   12:13   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       150  0.0  0.0 231972  3840 pts/0    S    12:13   0:00 /run/dojo/bin/bash --login
hacker       160  0.0  0.0 233600  3840 pts/0    R+   12:14   0:00 ps aux
hacker@processes~killing-misbehaving-processes:~$ kill 142
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
^C 
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{HfOWEsmsc867n80I3RrobRFuXWxHvl8CRVV.ki8sLjP.9OG}
pwn.college{-KfP76AbbbSdbiwI8O.6bfAdCqQjYifYK-fMov2QFXaoECP}
pwn.college{gb.-hwgjrG-43T-n9AEVoi72LRsVlfKmXpLyeRGuzPQZNZm}
pwn.college{GcuZUgBdTbH24gLLULmQpPc0qsdSYJrYTx726BCsP8NzY0N}
pwn.college{vAr9N-chKT0kH304QNU4xHX12oymkvj5C.S5RWwUTkFXl28}
pwn.college{fJ086bdQyTGBVIVbmgkRsqOXxZU3j-SPGq9jU9B-rsxEbm9}
pwn.college{dEPOkI9xGB5-vZhdya4FhwNaP9xO.g3vuN.cd3BRiBuuHHG}
pwn.college{ae-76VpeMJY0ZWrVo27iDsV3O6DNKmpfqZtxu4ccTku5kIo}
pwn.college{EsYwiKz84NYgRhpL9zNzXAsPzrpQwnkJGxaElkro9zao2AJ}
pwn.college{u7w25DGhbvgQDxOIp7l3rSOtYZDbc0H6g44Pf6LtOvG.rOJ}
pwn.college{eqcr8ItyrwjBuwYE1sgt4OB6eHlKFekPVsD-w8FOVOZlAIw}
pwn.college{sj6MsBetkePAUFH2Vd8P9pbwWFW7lGnEOwH-pqswRKoFfRL}
pwn.college{wOKMOB51isDQ4Zn.Ao31gZacil3hoH4qA4kf4aZNPOpLFQ0}
pwn.college{Ngg3TE58A3Z5BmE5WEy.Mo8PUAxtkIf1G1G1Cao.poKnGK.}
pwn.college{lPRUlAkenXqBIO4FZxbSMcQusw3N1vjzI3fUJG-hcIJMSp3}
pwn.college{JjUgwEp.ogn6VOnI8NMsFz1h3eZ94Jkam7NwqPhbRxrGqyY}
pwn.college{QxwWAp5TFhnD-HfrffHntnXwHPgIzUaDVN4uEh.7naAn4J5}
pwn.college{x30RUiBbiG9Uacvsmr6iVTyh8ThBnApdCJWYRAtNXQI8QpE}
pwn.college{IfiKf5Evr98rcBExa9wrVr5HuV6Uqsdf7z4QZcVzfFwc3kl}
pwn.college{Xg5rhKiAuCRRJKnNreHzsar6sKejWR0Y4aMPOwacB9vZUVf}
pwn.college{x5Xj5rqGvoOc3e9OEZl4OGHNgOoEIZqJFMKH1zBg4t9KpXH}
pwn.college{a9BrEhyNW3VjVGLB7nqUWLfpuJr63LHP0VElKS08d2LNPMP}
pwn.college{crD9fM2.4spFREIQ0fjLAIA1mhoOn1-qPj.gqUuwGmeGRuT}
pwn.college{QNpwyRRZR3dgGoN4qR50Vtv7RkGNzKBr.8.ThLertWqpi4q}
pwn.college{Zh4C8DrKsoMSLjUVzvun7iHF8TBO6pZ5aj6UE2acFCOm346}
pwn.college{ejcTsTaS30N4faa.TnbPuEJAY3X0XDSQ0nu-7J.NzFzppYc}
pwn.college{Po-w3LRz8zzc7VFGekuYCmekReH6RjKwBzM7MEgYal8qd9W}
pwn.college{j.8YJl1a3jUYUV7Onh1VbIjEcholI96Sfp6fNmnaSdpoG0M}
pwn.college{UEfS.f8ndNh4OiKFMY0v-jNP7Rg5I4ZllkmkFKnjBA8z-5D}
pwn.college{bvmWj3UQ7PKybKWBw2iaOlc0fFnsQy0bGdY.CnGhl19ydFP}
pwn.college{ZCh0Bxi47cwv6-.rsaJSpPEFwKoyZqUJd3w5Z79igEc6nKz}
pwn.college{wlfFFaCxMyRjB3D7t7Ach.PWWO0LzsdEVJwmZEyOtil66m6}
pwn.college{GjeV31ctxp4rMDrQPtpdytacwtA935W4CvEJzPxhW-9h3su}
pwn.college{hnhdpWvSHZf9Uve-2s6seJVaqewlwd3AHCie8DGnQ-3ncs6}
pwn.college{00k27eYrMn06c6KyW1-qSjG5.D9RwQQWKpb4yUZfvKw0Vib}
pwn.college{.efRtv1DSXWp3jRHhZmbbLzruhxvOksU64wigAmefGpnsgI}
pwn.college{Onwyhii0GSxtB1-WR-XoUhXketoMpjJlg8nPVdqlXhDIEG0}
pwn.college{L1ZjInaFyvgd-6GTwZGBu.uEFzSc9YpzcD2r0Fs9A2sR-Xj}
pwn.college{ZVEhw5fEN4vTM7DnTzC6C4sJoWPB4E0r-x5u7dhpYAhs8ug}
pwn.college{B6s-Y7b6HdUKJk.rCCRxGV885.adpGP-ehdlgoaKLuKn.VM}
pwn.college{OCmheM2pJdvhWAhVcIuNtGgDQH-oLp6W3iEZlarKfFBEx.t}
pwn.college{McqGHOx338ZB9urb0tdkgXMT5xTn0Pjv2onPVRzPioNOVpY}
pwn.college{yLe7zvhn8TkNJnbyozySbs1yjvfPiKWrGJ6uKiAK8OPb.Ks}
pwn.college{WiOV-hFK0rrMCCLAtFKhaVTTX2u1ReAn1kkNgjhaPNlcK4U}
pwn.college{73Ceg5DkVgvjPTFz1WFrI4xXWhl-50KFbiAXFGQ40itB0JE}
pwn.college{ELrCDh.SS0xnWAC1-OQXjvNx39O16o2WxOu8Bt572KXz8sa}
pwn.college{9c-zo2FqVOi8P4Mhqt4.pFRNEZSuZd.whHLfSUE.BydeyHr}
pwn.college{qFSbvev0ADB3I.IGb3FeYMmUwYd0kU8oOylI2WF0eNTdg70}
pwn.college{kdrXWkSMiS5EPc9pGRLIH07APb5DaMi2RoXxNUIGXXmgRWS}
pwn.college{E3WVAHtNGIO5VToyUPiOsLK5SY.WhfBLHFyz2Rrm03PUZpK}
pwn.college{Z7fa9qyrNASPN-eVCOGeqXu19SzcrqYbG6V4fX71LnsBL3m}
pwn.college{nvqsUTvQlKWFfHBdrAqJ26vHoymh49wuy1Cc9WitJIMJERg}
pwn.college{ImujfWkrsNDKsoFNn7M2LDMfFNoZLA188CdRNgcWbTzm61P}
pwn.college{zMHrpTnSj.21gRUNhfsIl9s3Dn7UrgGwSiQzvTd48ZNdEwr}
pwn.college{VOVDf.kI1KKPnPpQPE01AtvRVfu171cCC-hnhLVo9jJLEel}
pwn.college{.zoKuQwD8V6ZAKS1wPlD4kgEsvAhCqVrd8WGzrgg7ynTfBk}
pwn.college{G0frIR3mWDj7nrlifI0JA-Wj2yQPek0iJiKOWA0M5pftBud}
pwn.college{mMe2iZiacGmnt3v9bBl665kFZ1uelTSTHNF8w2GSoEp7tEY}
pwn.college{51yFLimOTAMcuLMf6vdAl.4MYkDsiHNnRRYLp-hbj2nqWm3}
pwn.college{QpyjvNWDMhqqvB5whm2R.inyncvNinv9SymE0ZtDXzAnkdJ}
pwn.college{qujGo0Fr3.HFRTs3cAOwgFqgFTenz0Y5TE9H-cCdLW4srIb}
pwn.college{n2iJ6sWnYN.ooQmG5EYaS79riTiPCJfah4BRa6E.3Mk5Dt1}
pwn.college{PJKBlJcxg-j5QQPmAyYSRORcJ5iZPdKDlpPNYqL5su2ubDA}
pwn.college{uKJqA0d38mBwcrZZsxKDc6Xzf4MM76aOHRdsezXmIG62gR5}
pwn.college{BjmWfnxqKN2okR5OMqjXYTRkF7h5BuTI.GNEXV19Vc8J.Ie}
pwn.college{wAfQS0geFGqJO9.uC6-GLzIu1.yWDudcICbLTxY7AmASPD-}
pwn.college{6QH-UXu4J8WXD.MakVbegmVt.mdK7kLbhfVDUbmHq1YtF3w}
pwn.college{0vcx7vi1kN4H6gq.So6ykKIIXbKLIZXfJ4Vcig9Vglq2.08}
pwn.college{1lAk8lVqmTtHlBd2Ao7E4n0mEGSKLFC.xmgpmgK-AXBjvEc}
pwn.college{uXZsgl-cYWLP1V8.GiXLqkWrxVKHKsLqgwXdMGJ69IoGzLt}
pwn.college{A9mKsheXleL5pcaU3N2KXSEpXjK50gyZ.sgwRGiWekb-jAv}
pwn.college{VxjnHNl95iMM9IOKQP6Ho9g.GYoRbM73LlBox1xAGDP7210}
pwn.college{oZtXAL7VGGg87hDjidbJ0omv7rQNc-XwBFH407kPBWsx4PQ}
pwn.college{Uf8IJTxAaYBZ8daZIUI0EFAftrKRVm2ME8ieB-aadPNCvyJ}
pwn.college{C-2eFyD0J3rDo5XbvwK9pkdbiNllMBCq7GWqJSxPzQunkLQ}
pwn.college{F8.M4ldwceODvmWecAyZPPCYeydDlDL8Xx5u7PEnUHLLje8}
pwn.college{5KhgxgXDoatAFHiAdYUMO-eA88M1D8xm0fJ9DGkTQN1roa.}
pwn.college{6yxCjJmO2gHmWZ11bjdk-fsds.zxFbiW1.rZDkIpnZ-h4Jm}
pwn.college{MNSxOacZIrSKm6xlEn2lynwief6yzP-InaFL83PBeokeJwz}
pwn.college{t8aTVZK583U9Ucqcz2ID1Tk96XujqqrDqP6NL4gjymj2vNP}
pwn.college{zeOcVl6DBqA8kkTpA70fLkdklnA1hwRHLFP4JhRiQ--BJyL}
pwn.college{ntz4jwP.DmhsET27CHAWfORY35WxcI1b.Jao0dBGIQF4JnV}
pwn.college{T.bSyiDT9TFfU.gaTpm2FAmFDLgAIzbyZcOO4Z7fZhsftAt}
pwn.college{XgysE2syWHi2.ttyMmGr.ux2kpaHqyvlVjad0qtFldxc.Zz}
pwn.college{3HIoqIInMuA0el0bKlKX2vAXSnYlaCrM3FoFQCyCWBTk0vT}
pwn.college{vK21r1U6hhb.V.2VlenOaqIr62MMC9vhDTC4oh6fJifYUZz}
pwn.college{rQ7MGQecxpCcMd4eUHf-WOHhLWbxLtESrUaGswOEfD2GoBB}
pwn.college{SA3eXALUwvDsUiEMQ7GmAXX7n5LkGIcVCSEqvZbjuJXBYpy}
pwn.college{KLTDauMH27ST9HY07LQISAlsFtD8XTspLVH2GZBp8G7z0fu}
pwn.college{xR6KzfeR9plykIINnHwuuFn4SZUWsR6OclpoO3pYz-sr0jM}
pwn.college{1Coq-zLIEhq38JwokMsUJCcBk9UJPKJI.myXLr6hT7GjS-Z}
pwn.college{NtQJvKkq7Wgik0QcLoar1r6yApweVX7vISkV6nqre1KAM1a}
pwn.college{fIDbNY-reKt5k9j-fw6MnuzMB8-5tE86Kz-DsKvmZx40.HD}
pwn.college{lvjn8-LXMsddCm8lJq-HoyYRdvduVUdY6SzVfj3gIhOrp0y}
pwn.college{hGswrgDpcJHka24m3xqyxJPVJG922c3UJesAhZ.ERrq9-qi}
pwn.college{MDzCOvRUSMCA6VKSJpdBYvPNgQwp3z1rUHVyjfXuJ8OEU6x}
pwn.college{hOo2bWe67-WBDLeQbGxQ6DJCZH3l8dC.xd9QG.rOLQgKraI}
pwn.college{2KSzYQHF6rzw2..ZLfL-cy6GS-LFYjeGEF8kbCWSfMrG9wz}
pwn.college{yOHQXVZhH2pnWU0jrwJIAc-eEqj0wCSl9h8Yne4QKZbX7Rb}
pwn.college{nXWcwjL0LsKvmDLEmAjWBdspx8RNLjcm1YzBaRICjqeFn5A}
pwn.college{3UzEqv10347ywGpzOy-QaZVEACBGDv-9my7Ik4diUTlT8xG}
pwn.college{3Apu6pFUkoq9IdXyHOEafkdWV5t5aN6j3adYX-.HKK4c.dB}
pwn.college{vk7FoHoR5hrREhVm17f.-jPrEiPO-eGMkMwkP.UiaW0ZwJ6}
pwn.college{4aYZPGMe3.qPUpk81xt6ptgegfFSD3MjRXx7BAJsyW9KXDY}
pwn.college{KvqEkznantSLRCuou7hn0KWGYgiLROaHCXU5NZ3dNa0uGmo}
pwn.college{u7phNRKo40XhEcVU9T3oo6kyt5MDBTO.d-ymI4ktAfXV0GR}
pwn.college{elput5Xz3eLXtjX9RYd9cgTwblzkaikoOgQs9IMvT7gayhm}
pwn.college{ak0kT67ewVAyn6iGN92n9mXt5vBhJWCDCqOlqVfnM.Ox.eA}
pwn.college{wAy7ZmBzJJmbTJK096qqmJEhEsN5NMwoOH19PcF4hd47qLJ}
pwn.college{k-F53blFmp2DKqMo2LL83cbehvPuxHidAKlqgqouzG7bQo4}
pwn.college{NpX38n2bftxRMP9iHaxMdQvIv246JYAJUDwzbPpH6HygLpB}
pwn.college{4T1FU6PH1QHU-y5gnZF9ryhbCO4wIBNDfX0OC.SXHOHT86x}
pwn.college{RgrJkUgf4FvS.TRUgo7K1xEU44.w56dMpfwmIxwwccIAow3}
pwn.college{SkJaGSTtkgHpiKa18iPs5FoPr6sXsVmX1wGOusDGZ3rfhvA}
pwn.college{ZxEQCYjiy0Ds3LZmPilLGjWlRCDq2EUxvvW20Xn1unxlJqs}
pwn.college{CeEUmGzQMURTA-h22D5Bx.s-qtQE9gzZxGOAhDPFy.aRa8a}
pwn.college{FqPa0QWKsC7vOB9LNMI1BQiJpztvYmxK51YselTRI05xkCe}
pwn.college{Q8zY3FeJdMUda1TG5YXkkHWafzl207mIPri58fhYP.BZKaV}
pwn.college{CERFkyQRT3olv5gmhd.YI8BLn9FXmo3rbBsZloXb3yolLTM}
pwn.college{y7604oUQuLuoVjhArsVIfI5vQLXKDHpRXyNaHtZRAEsHY5A}
pwn.college{1oUttFCdFeAT2cvWqWo482I.Fbz50uDSvo15BTrqcDsWrAN}
pwn.college{Z3tmCLJdbUbJu86uLqV-gUjiRtUOk5yvgfwQOPsAZcBMJSd}
pwn.college{bF9HybuhaOURGQzACmykezxlfJXOEgZJWg-9x7u.DVSbFd1}
pwn.college{fgAsk2PZYdxgDl6Pxrw2NV0CKEZ5Y9DWgiTJamJKCavTczb}
pwn.college{vHf36GSoBk1gXsexO.0UWxfJ.gB9rCAFUE8G6xQra6YemxP}
pwn.college{K8qMGWWbqpMl1gbfBB1O4FCTRyjUcedFBjPXSZh8Khsoh42}
pwn.college{OVnqD31aSqjuYtrgvunWJ24d0SgHOJzooMlXXeE61-hGA1m}
pwn.college{26X5eTDlkuzpLoBmH9S-oBR.AUt1PBNxDM2...cxlLH5z3B}
pwn.college{.5lkM0OsndCvPertUEaWNvxIb5q93ozEepSeK2Sm6MdnV-A}
pwn.college{Ua6rFTzITUlp767ZhodNv.su3br329qjoctGpU9jSuWk8TA}
pwn.college{IO.vzyFiGYV7rChtvrgcSx0fm-zh9SzzZA.ffEWKsjYsq2Q}
pwn.college{ZLoTjdMn2-0hfUJ.jV-x9puRmSxCaj5K3mOtQ7KjA5BIwzn}
pwn.college{KSYVOGIe-MYUMxFCzTsgC2xLfkxReFTnI9xA3aNQcvauoeI}
pwn.college{DhALzHHPlqM6PdoVb4glx5TdoZdadc5buWb6mge6BU8pPsi}
^C
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ /challenge/run /tmp/flag_fifo
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ /challenge/run/tmp/flag_fifo
bash: /challenge/run/tmp/flag_fifo: Not a directory
hacker@processes~killing-misbehaving-processes:~$ /tmp/flag/fifo
bash: /tmp/flag/fifo: No such file or directory
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{gNYeq6N1isGBXex73VzVX3DpkpW.0FNzMDOxwCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{gNYeq6N1isGBXex73VzVX3DpkpW.0FNzMDOxwCN1AzNzEzW}



# Suspending Process
For this challenge we had use the ctrl z command which is different from the ctrl c as it suspends the process rather than kill it.


```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         140     129  0 12:22 pts/0    00:00:00 bash /challenge/run
root         142     140  0 12:22 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         140     129  0 12:22 pts/0    00:00:00 bash /challenge/run
root         147     129  0 12:23 pts/0    00:00:00 bash /challenge/run
root         149     147  0 12:23 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{0ZkH5BtyyEFT2b3vMIlnfKS6j9E.QX1QDO0wCN1AzNzEzW}
```

## My Solve 
The flag for the above challenge is pwn.college{0ZkH5BtyyEFT2b3vMIlnfKS6j9E.QX1QDO0wCN1AzNzEzW}



# Resuming Processes
In this challenge we learn how to resume a challenge that we had suspended previously and this helps in us obtaining the flag

```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ 
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{EaVAlyKcLb3G4KWImiseVecLXJA.QX2QDO0wCN1AzNzEzW}
Don't forget to press Enter to quit me!

Goodbye!
hacker@p
```

## My Solve 
The flag for the above challenge is pwn.college{EaVAlyKcLb3G4KWImiseVecLXJA.QX2QDO0wCN1AzNzEzW}



# Backgrounding Processes 
In this challenge we learn that we can even resume background functions by using the bg command, and by doing this and opening another /challenge/run and resuming that we obtain the command.


```
hacker@processes~backgrounding-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   12:28   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0 231708  2560 ?        S    12:28   0:00 /run/dojo/bin/sleep 6h
hacker       123  0.0  0.0 231576  3520 pts/0    Ss   12:28   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       129  0.0  0.0 231940  4160 pts/0    S    12:28   0:00 /run/dojo/bin/bash --login
hacker       139  0.0  0.0 233600  3840 pts/0    R+   12:29   0:00 ps aux
hacker@processes~backgrounding-processes:~$ bg
bash: bg: current: no such job
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         140 S+   bash /challenge/run
root         142 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   12:28   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0 231708  2560 ?        S    12:28   0:00 /run/dojo/bin/sleep 6h
hacker       123  0.0  0.0 231576  3520 pts/0    Ss   12:28   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       129  0.0  0.0 231940  4160 pts/0    S    12:28   0:00 /run/dojo/bin/bash --login
root         140  0.0  0.0   5788  3200 pts/0    T    12:30   0:00 bash /challenge/run
hacker       147  0.0  0.0 233600  3840 pts/0    R+   12:30   0:00 ps aux
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         140 S    bash /challenge/run
root         151 S    sleep 6h
root         152 S+   bash /challenge/run
root         154 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{4Ew4qyAEHPhrZ_5G957detBzACo.QX3QDO0wCN1AzNzEzW}
```

## My Solve
The flag for the above challenge is pwn.college{4Ew4qyAEHPhrZ_5G957detBzACo.QX3QDO0wCN1AzNzEzW}



# Foregrounding Processes
In this challenge, we learn how to foreground processes by using the fg command which helps us in bringing the proccess back to what it was, if it had been suspended


```
hacker@processes~foregrounding-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.1  0.0   1056   640 ?        Ss   12:35   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0 231708  2560 ?        S    12:35   0:00 /run/dojo/bin/sleep 6h
hacker       123  0.0  0.0 231576  3520 pts/0    Ss   12:35   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       129  0.0  0.0 231940  4160 pts/0    S    12:35   0:00 /run/dojo/bin/bash --login
hacker       140  0.0  0.0 233600  3840 pts/0    R+   12:36   0:00 ps aux
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.

hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{YRJAdTj9w3cZL_atxM8lDV6KHkw.QX4QDO0wCN1AzNzEzW}
```


## My Solve
The flag for the above challenge is pwn.college{YRJAdTj9w3cZL_atxM8lDV6KHkw.QX4QDO0wCN1AzNzEzW}



# Starting Backgrounded Processes 

```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run
You've started me in the foreground! You must start me in the background (by 
appending '&' to the command) to get the flag!
hacker@processes~starting-backgrounded-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   12:41   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0 231708  2560 ?        S    12:41   0:00 /run/dojo/bin/sleep 6h
hacker       123  0.0  0.0 231576  3520 pts/0    Ss   12:41   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       129  0.0  0.0 231940  4160 pts/0    S    12:41   0:00 /run/dojo/bin/bash --login
hacker       144  0.0  0.0 233600  3840 pts/0    R+   12:44   0:00 ps aux
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 145
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{gTJLQQ1iryEDtcCN-5OgN9tjR0y.QX5QDO0wCN1AzNzEzW}

```

## My Solve
The flag for the above challenge is pwn.college{gTJLQQ1iryEDtcCN-5OgN9tjR0y.QX5QDO0wCN1AzNzEzW}



# Process Exit Codes

The challenge was to retrieve the exit code returned by the /challenge/get-code and then use the /challenge/submit-code with the error code as an arguement.
This helps us in learning about how to use the echo $? command

```
hacker@processes~process-exit-codes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   12:49   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0 231708  2560 ?        S    12:49   0:00 /run/dojo/bin/sleep 6h
hacker       125  0.0  0.0 231576  3520 pts/0    Ss   12:49   0:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qzyms72zld1-bash-interactive-5.2p37/bin/bash /run/dojo/bin/ssh-entrypoint
hacker       131  0.0  0.0 231940  4160 pts/0    S    12:49   0:00 /run/dojo/bin/bash --login
hacker       146  0.0  0.0 233600  3840 pts/0    R+   12:58   0:00 ps aux
hacker@processes~process-exit-codes:~$ echo $?
0
hacker@processes~process-exit-codes:~$ /challenge/run
bash: /challenge/run: No such file or directory
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo %?
%?
hacker@processes~process-exit-codes:~$ echo $?
0
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
190
hacker@processes~process-exit-codes:~$ /challenge/190
bash: /challenge/190: No such file or directory
hacker@processes~process-exit-codes:~$ /challenge/submit-code 
You must run /challenge/submit-code with the exit code you retrieved from 
/challenge/get-code as the first argument:

Usage: /challenge/submit-code [EXIT_CODE]
hacker@processes~process-exit-codes:~$ /challenge/submit-code 190
CORRECT! Here is your flag:
pwn.college{kKR89XvIWXK62lcCl6pua9J13UZ.QX5YDO1wCN1AzNzEzW}

```

## My Solve 
The flag for the above challenge is pwn.college{kKR89XvIWXK62lcCl6pua9J13UZ.QX5YDO1wCN1AzNzEzW}

