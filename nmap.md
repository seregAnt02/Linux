##### сканирование следующими командами:
  * nmap -sS <example.com> – TCP-SYN сканирование узла
  * nmap -sT <example.com> – полное TCP сканирование узла
  * nmap -sU <example.com> – UDP сканирование узла
##### ┌──(kali㉿kali)-[~]
└─$ nmap -sT -Pn -n -F -sV --open 172.18.0.2
Starting Nmap 7.94 ( https://nmap.org ) at 2023-10-14 09:26 EDT
Nmap scan report for 172.18.0.2
Host is up (0.00018s latency).
Not shown: 98 closed tcp ports (conn-refused)
PORT     STATE SERVICE        VERSION
22/tcp   open  ssh            OpenSSH 7.4p1 Debian 10+deb9u7 (protocol 2.0)
8443/tcp open  ssl/https-alt?
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 34.50 seconds
