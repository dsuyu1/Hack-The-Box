## Introduction
<br>
<img src="https://i.imgur.com/Z2OyMPq.png">
<br><br>

Meow is the first box I pwned in Hack The Box. It is the easiest lab in the Hack The Box penetration testing lab learning path. 
## Steps
To pwn Meow, I had to first use the `ping` command to verify the connection to the machine and `nmap -sV` to determine which ports were open and vulnerable.
Meow had port 23 open and connected via Telnet, so we could guess that Meow's login was root with a blank password.

<br>


The detailed documentation I followed to pwn Meow can be found [here](https://app.hackthebox.com/starting-point).
