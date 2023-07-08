## TCP

3-Way Handshake

- SYN
- SYN-ACK
- ACK

---

- FIN
- ACK-FIN
- ACK

SYN Scan

- SYN is sent to many destinations
- SYN-ACK response indicates open port
- RST-ACK response indicates closed port
- no response indicates filtered port



## Ports

System Ports: 0-1023

Registered Ports: 1024-49151

Dynamic/Private Ports: 49152-65536


## OSI Layers

1) Phsysical Data Link (bits) (Coax, Fiber, Wireless)
2) Data Link (frames) (Ethernet, PPP, MAC, ARP)
3) Network (packets) (IP)
4) Transport (segments, connections) (TCP, UDP)
5) Session (data) (APIs)
6) Presentation (data) (SSL, SSH)
7) Application (data) (HTTP)


## ARP

Layer 2 communication to find devices on the local network

1) source broadcasts (ff:ff:ff:ff:ff:ff) who has <IP>
2) destination calls back to source MAC <IP> is at <MAC>

ARP Poisoning - rogue device response to ARP despite not being correct IP

## ping

ICMP - Internet Control Message Protocol


## NAT  

1) Source IP:Port to router: Source 10.0.0.10:49200, Destination 56.0.0.1:80
2) Router adds entry to NAT Translation Table: LAN 10.0.0.10:49200, WAN 30.0.0.1:49200
3) Router modifies packet: Source 30.0.0.1:49200, Destination 56.0.0.1:80
4) Website responds back: Source 56.0.0.1:80, Destination 30.0.0.1:49200
5) Router delivers reponse to source: Source 56.0.0.1:80, Destination 10.0.0.10:49200 
   
Port can be translated if needed  
  
