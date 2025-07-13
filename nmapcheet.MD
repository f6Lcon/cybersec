**Port specific options**
-p nmap -p 23 123.1.1 --port scaning a specific port [23 in this case]
-p nmap -p 23-100 123.1.1 --poer scanning specific port range
-p nmap -pU:110, T:23-25,443 123.1.1 U-UDP, T-TCP, diffrent port types scan
-p- nmap -p- 1223.1.1 port scan for all ports
-p nmap -smtp, https 123.1.1 portscan for all specified protocals
-F nmap -F 1223.1.1 Fast port scan for speed up
-p "*" nmap -p "*" frp 123.1.1 port scan using name
-r nmap -r 123.1.1 sequential port scan

**Host /123.1.1 Discvery**
-sL nmap 123.1.1 -sL List123.1.1 without scanning
-sn nmap 123.1.1 -sn Disable port scanning
-Pn nmap 123.1.1 -Pn port scan only and no gost discovery
-PS nmap 123.1.1 -PS22-225,80 TCP SYN discovery on specified port
-PA nmap 123.1.1 -PA22-25,80 TCP ACK discovery on specified port
-PU nmap 123.1.1 -PU53 UDP discovery on specified port
-PR nmap1 23.1.1/8 -PR ARP discovery within local networks
-n nmap 123.1.1 -n no DNS resolution


**Version Detection**
-sV nmap 123.1.1 -sV Try to find the version of the seervice running on port
-sV --version-intensity nmap 123.1.1 -sV --version-intensity 6 Intensity level [0-9]
-sV --version-all nmap 123.1.1 -sV --version-all set intensity version to 9
-sV --version-light nmap 123.1.1 -sV --version-light enanle light mode
-A nmap 123.1.1 -A Enable OS detection, version detection , scriptscanning and tracerout
-O nmap 123.1.1 -O Remote OS detection

**Firewall Proffing**
nmap -f [123.1.1] scan fragment packets
nmap -mtu [MTU] [123.1.1] specify mMTU
nma- -sI [zombie] [123.1.1] scan idle zombie
nmap -source-port [PORT] [123.1.1] manual source port - specify
nmap -data-length [size] [123.1.1] randomly apend data
nmap -randomizze-hosts [172.1.1] bad checksum

**Nmap Timing Options**
nmap -T0 123.1.1 Slowest Scan
nmap -T5 123.1.1 Very aggresive scan

**Scanning Types**
-sS nmap 123.1.1 -sS TCP SYN Port scan
-sT nmap 123.1.1 -sT TCP Connect port scan
-sA nmap 123.1.1 -sA TCP SCK port scan
-sU nmap -123.1.1 -sU  UDP port scan
-Sf nmap 0Sf 123.1.1 TCP FIN scan
-sX nmap -sX 123.1.1 XMAS scan
-Sp nmap -sP 123.1.1 ping scan
-SL nmap -SL 123.1.1 list scan


**NMAP output fomarts**
Default /Normal output nmap -oN scan.txt 123.1.1
XML nmap -OX scan.xml 123.1.1
Grepable fomart snmap -oG grep.txt 123.1.1
All fomarts
nmap -oA 123.1.1

**Miscellaneous commands**
nmap -6 scan IPV^ targets
nmap -proxies proxy 1 URL, proxy 2 URL run in targets with proxies
nmap -open shou open ports only



 What is the command we need to run in order to display the 'ftp' client help menu? 
