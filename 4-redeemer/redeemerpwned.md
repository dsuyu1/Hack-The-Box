## Introduction

In Redeemer we look into a different service, **Redis**. Redis is an "in-memory" database. In-memory databases are the ones that rely essentially on the primary memory for data storage. Rather than storing databases on hard drives and SSDs, in-memory databases are stored on RAM. As primary memory is faster than secondary memory, in-memory databases are much faster when it comes to retrieving data.

In-memory databases like Redis are are typically use to cache data of frequented data for quick retrieval. For example, if there are links or prices on the front page of a website that are frequently visited, Redis caches them. Rather than pulling the data primarily from the traditional database (like MySQL or MongoDB), instead, the data is pulled from Redis. Redis handles similar requests over a period of time for much faster retrieval.

## Enumeration
Redeemer was interesting in that right from the start we're made to use different flags for `nmap`. Because Redis is located on port `6379`, and regular `nmap` searches on the first 1000 ports, we can use the `-p-` flag to search all ports.

<br>
<img src="https://i.imgur.com/fefTIJi.png">
<i>Ref 1: Redis is open on TCP port 6379</i>
<br><br>


