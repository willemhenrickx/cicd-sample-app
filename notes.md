# nmap Port scanning

### 1) 22, 80 ,9929 , 31337 are open

### 2) No, it has only scanned the top 1000 most common used ports. You will be able to scan all ports by using `nmap -p- {{port1,port2,…,portN}} {{address_or_addresses}}`

### 3) By using `nmap -sU scanme.nmap.org`

### 4) Because UDP is rate limited by 1 each second and there are way too many UDP ports available to scan. We can speed this process up by using the -T3, -T4 parameter. We can use the `--top-ports 20` command to scan the 20 top used ports.

### 5) 53, 67,68,69,123,137,139,161,445

### 6) ` sudo nmap -sV -p22 --script vulners --script-args mincvss=1.0 scanme.nmap.org` 

### 7)

# nmap Host/Network scanning

### 1) Only 3 of the 8 hosts we scan are alive
```console
 willem  iLegendaryMEDION  ~  .nmap  $  nmap -sn 157.193.215.170/29

Starting Nmap 7.60 ( https://nmap.org ) at 2021-10-14 12:42 CEST
Nmap scan report for 157.193.215.170
Host is up (0.0078s latency).
Nmap scan report for 157.193.215.171
Host is up (0.0078s latency).
Nmap scan report for 157.193.215.172
Host is up (0.0078s latency).
Nmap done: 8 IP addresses (3 hosts up) scanned in 14.21 seconds
```

### 2) We can, by using the -n and --disable-arp-ping option

````console
 willem  iLegendaryMEDION  mnt  c  Users  wille  $  nmap -sn -n --disable-arp-ping 157.193.215.
170/29

Starting Nmap 7.60 ( https://nmap.org ) at 2021-10-20 17:19 CEST
Nmap scan report for 157.193.215.170
Host is up (0.035s latency).
Nmap scan report for 157.193.215.171
Host is up (0.040s latency).
Nmap scan report for 157.193.215.172
Host is up (0.044s latency).
Nmap done: 8 IP addresses (3 hosts up) scanned in 1.26 seconds
````

Dns gives us more information resolving the domain names

````console
nmap -sn --dns-servers 1.1.1.1 --disable-arp-ping 157.193.215.170/29

Starting Nmap 7.60 ( https://nmap.org ) at 2021-10-20 17:18 CEST
Nmap scan report for home.test.atlantis.ugent.be (157.193.215.170)
Host is up (0.033s latency).
Nmap scan report for www.test.atlantis.ugent.be (157.193.215.171)
Host is up (0.045s latency).
Nmap scan report for mail.test.atlantis.ugent.be (157.193.215.172)
Host is up (0.031s latency).
Nmap done: 8 IP addresses (3 hosts up) scanned in 4.51 seconds
````

### 3)  


