## Introduction
<br>
<img src="https://i.imgur.com/WaZOKL5.png">
<br><br>

Server Message Block (SMB) is a communication protocol that provides shared access to files, printers, and serial ports between endpoints on a network. SMB services are mostly seen on Windows machines. 

Port 445 TCP is reserved for the SMB protocol. Usually, SMB runs at the Application or Presentation layers of the OSI model, so it relies on lower-level protocols for transport. The Transport layer protocol that Microsoft SMB Protocol uses most often is NetBIOS over TCP/IP (NBT). During scans, we will most likely see both protocols with open ports running on the target.

## Enumeration
As always, I started by pinging the target IP address and running a `nmap -sV` scan to identify open ports. Thanks to `nmap`, we can see that port 445 is open. We can think of the SMB share as a folder that can be accessed over the internet. In order to access it, however, we have to download the SMB client, or use the script `smbclient`.
