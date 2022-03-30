# HackTheBox-Paper-Walkthrough
This the the walkthrough for Paper lab in HackTheBox (https://app.hackthebox.com/machines/Paper)
This is my first public walkthrough for a CTF. I would appriciate any contructive critism and suggestions.


This Lab/CTF focuses on Enumerating skills and LFI skills, it does not focus on Priv-Esc or other things which are unlike other CTFs.



1) Enumerating </br>
    I used nmap to analyse the IP and see the active ports and services running.</br>
      
```
nmap -sC -sV <ip>
```
<pre>
nmap -sC -sV **.**.**.***
Starting Nmap 7.92 ( https://nmap.org ) at 2022-03-31 03:48 IST
Nmap scan report for office.paper (**.**.**.***)
Host is up (0.26s latency).
Not shown: 997 closed tcp ports (conn-refused)
PORT    STATE SERVICE  VERSION
22/tcp  open  ssh      OpenSSH 8.0 (protocol 2.0)
| ssh-hostkey: 
|   2048 10:05:ea:50:56:a6:00:cb:1c:9c:93:df:5f:83:e0:64 (RSA)
|   256 58:8c:82:1c:c6:63:2a:83:87:5c:2f:2b:4f:4d:c3:79 (ECDSA)
|_  256 31:78:af:d1:3b:c4:2e:9d:60:4e:eb:5d:03:ec:a0:22 (ED25519)
80/tcp  open  http     Apache httpd 2.4.37 ((centos) OpenSSL/1.1.1k mod_fcgid/2.3.9)
|_http-server-header: Apache/2.4.37 (centos) OpenSSL/1.1.1k mod_fcgid/2.3.9
|_http-title: Blunder Tiffin Inc. &#8211; The best paper company in the elec...
|_http-generator: WordPress 5.2.3
443/tcp open  ssl/http Apache httpd 2.4.37 ((centos) OpenSSL/1.1.1k mod_fcgid/2.3.9)
|_http-server-header: Apache/2.4.37 (centos) OpenSSL/1.1.1k mod_fcgid/2.3.9
|_ssl-date: TLS randomness does not represent time
| tls-alpn: 
|_  http/1.1
|_http-generator: HTML Tidy for HTML5 for Linux version 5.7.28
| http-methods: 
|_  Potentially risky methods: TRACE
| ssl-cert: Subject: commonName=localhost.localdomain/organizationName=Unspecified/countryName=US
| Subject Alternative Name: DNS:localhost.localdomain
| Not valid before: 2021-07-03T08:52:34
|_Not valid after:  2022-07-08T10:32:34
|_http-title: HTTP Server Test Page powered by CentOS
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 53.51 seconds  
</pre>

    
