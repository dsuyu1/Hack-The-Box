## Introduction
<img src="https://i.imgur.com/WaZOKL5.png">
<br>

Server Message Block (SMB) is a communication protocol that provides shared access to files, printers, and serial ports between endpoints on a network. SMB services are mostly seen on Windows machines. 

Port 445 TCP is reserved for the SMB protocol. Usually, SMB runs at the Application or Presentation layers of the OSI model, so it relies on lower-level protocols for transport. The Transport layer protocol that Microsoft SMB Protocol uses most often is NetBIOS over TCP/IP (NBT). During scans, we will most likely see both protocols with open ports running on the target.

## Steps
As always, I started by pinging the target IP address and running a `nmap -sV` scan to identify open ports. Thanks to `nmap`, we can see that port 445 is open. We can think of the SMB share as a folder that can be accessed over the internet. To access it, however, we have to download the SMB client, or use the script `smbclient`. We can install it using the command `sudo apt-get install smbclient`.

After installing, I connected to the share using `smbclient -L {ip}`; the `-L` switch selects the target host (the target IP). After running the command, we can see four separate shares being hosted on the SMB server. We can access them via the command `smbclient \\\\{ip}\\{share name}`. In our case, the shares were called ADMIN$ C$, IPC$, and WorkShares.

SMB shares are usually protected behind a username/password login, however, shares can be misconfigured to not require a password. If we do not input a username, our host computer's name is used as the default. After trial and error, we access the `WorkShares` share without a password! We're in! We can download files using the `get` command, and we can move within the directory using `ls` and `cd` like we would with any other directory. Pwned!
