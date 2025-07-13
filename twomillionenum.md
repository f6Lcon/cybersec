## f6Lcon

`ping -c1 10.10.10.111`

-- Check if the host is online

`ping -c1 10.10.10.111 -R`

-- router retrace to se the machine is running on either windows or linux
-- ttl 64 will be linux. node and jump (63)
-- ttl 120 will be windows.

`sudo nmap -p- --open -sS --min-rate 5000 -vvv -n -Pn 10.10.101 -oG portenum`

-p- all ports
-sS no log leave
--open only scan open ports
--min-rate 5000 -vvv not les than 5000 packets and -vvv show imedietly any discovered port without waiting for the scan to finish.
-n no Dns resolution
-Pn no host disco

ports can be either
1.open
2.filterd
3.closedvery

`nmap -p 22,80 -sC -sV 10.10.10 -oN target`

`sudo tshark -i tun0 -Y "tcp.flags.syn == 1 and tcp.flags.ack == 0 and tcp.dstport == 22" 2>/dev/null`

curl

`curl -s -X POST "url" | jq`

FTP sends data in the clear, without any encryption. What acronym is used for a later protocol designed to provide similar functionality to FTP but securely, as an extension of the SSH protocol? SFTP
ftp runs on port 21
