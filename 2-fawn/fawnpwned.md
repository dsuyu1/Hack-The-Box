## Introduction
<img src="https://i.imgur.com/yiCeAf4.png">
<br>


Fawn is the second lab in the Hack The Box "Starting Point" penetration testing series. In this lab, we pwn Fawn using port 21, the FTP protocol. The File Transfer Protocol (FTP) is a native protocol to
all host operating systems and used for a long time for simple file transfer tasks. FTP can be easily
misconfigured. FTP can be used to transfer log files from one network device to another or a log collection server.
FTP is built on a client-server model architecture using separate control and data connections between the client
and the server. 

Importantly, clients can connect to the FTP server anonymously if the server is configured to allow it. For secure
transmission that protects the username and password and encrypts the content, FTP is often secured with SSL/TLS
or replaced with SSH FTP (SFTP).

## Steps
Using `nmap -sV {ip address}`, we find that port 21 is open. Using the `ftp` command, we can access the FTP server.
First, we should make sure FTP is installed on our own host, and we can do that by running the command `sudo apt install ftp -y`. 
We use the `ftp {ip address}` command to connect to the target. Because the server was misconfigured, or configured to allow anonymous connections,
we can enter the username `anonymous` and the password can be anything as it is disregarded. 

And we're in! We use the `ls` command to find the flag, and the `get` command to download it to our host. Importantly, the file downloads to the same directory
where we issed the `ftp {ip address}` command.
