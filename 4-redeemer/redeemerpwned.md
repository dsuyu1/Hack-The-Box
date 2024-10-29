## Introduction
<img src="https://i.imgur.com/eUAp5Rf.png">
<br>

In Redeemer we look into a different service, **Redis**. Redis is an "in-memory" database. In-memory databases are the ones that rely essentially on the primary memory for data storage. Rather than storing databases on hard drives and SSDs, in-memory databases are stored on RAM. As primary memory is faster than secondary memory, in-memory databases are much faster when it comes to retrieving data.

In-memory databases like Redis are are typically use to cache data of frequented data for quick retrieval. For example, if there are links or prices on the front page of a website that are frequently visited, Redis caches them. Rather than pulling the data primarily from the traditional database (like MySQL or MongoDB), instead, the data is pulled from Redis. Redis handles similar requests over a period of time for much faster retrieval.

Redis stands for Remote Dictionary Server and is an open-source NoSQL key value data store. The data is stored in a dictionary data structure with key-value pairs. Typically, it is used for short-term storage of data that needs fast retrieval.
## Enumeration
Redeemer was interesting in that right from the start we're made to use different flags for `nmap`. Because Redis is located on port `6379`, and regular `nmap` searches on the first 1000 ports, we can use the `-p-` flag to search all ports.

<br>
<img src="https://i.imgur.com/fefTIJi.png">
<i>Ref 1: Redis is open on TCP port 6379</i>
<br><br>

After installing the Redis CLI with `sudo apt install redis-tools` , we can access the Redis server using `redis-cli {host ip}`. Once connected to the Redis server, we can use the `info` command to learn more about the server. We find that there is one database on index 0 with four keys. To select database 0, we use the command `select 0`, and to see all the keys, we use the command `keys *`. Inside, we find the flag. 

<br>
<img src="https://i.imgur.com/yTLDfaB.png">
<i>Ref 2: Under # Keyspace, we can see databasae 0 with 4 keys</i>
<br><br>



