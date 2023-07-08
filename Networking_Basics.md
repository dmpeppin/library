# Networking Basics


## OSI Layers

1) Phsysical Data Link (bits) (Coax, Fiber, Wireless)
2) Data Link (frames) (Ethernet, PPP, MAC, ARP)
3) Network (packets) (IP)
4) Transport (segments, connections) (TCP, UDP)
5) Session (data) (APIs)
6) Presentation (data) (SSL, SSH)
7) Application (data) (HTTP)


## Layer 2

Layer 2 communication to find devices on the local network

Device: Switch
> When the destination is on the same network (same IP range/subnet) Layer 2 is used to find destination

ARP
1) source broadcasts (ff:ff:ff:ff:ff:ff) who has IP `<destination IP>`? Tell IP `<source IP>`
2) destination responds to source MAC that `<destination IP>` is at MAC address `<destination MAC>`
3) source can now cache IP address to a MAC address
4) while communicating to destination, MAC address can be used and switch can set a direct line of communication from port to port rather than a broadcast to all ports

ARP Poisoning - rogue device response to ARP despite not being correct IP

## Layer 3 IP

Device: Router
> When the destination is on a different network (different IP range or subnet) Layer 3 is used to find the destination's network

ICMP - Internet Control Message Protocol: used to identify network resources available to the IP layer

- ping: simple pass/fail check for resource
- tracert: shows pathway to resource

### NAT  

1) Source IP:Port to router: Source 10.0.0.10:49200, Destination 56.0.0.1:80
2) Router adds entry to NAT Translation Table: LAN 10.0.0.10:49200, WAN 30.0.0.1:49200
3) Router modifies packet: Source 30.0.0.1:49200, Destination 56.0.0.1:80
4) Website responds back: Source 56.0.0.1:80, Destination 30.0.0.1:49200
5) Router delivers reponse to source: Source 56.0.0.1:80, Destination 10.0.0.10:49200 
   
Port can be translated if needed  


### Subnets vs VLANs

VLANs will segment the physical network, ARP can not see across the VLAN

Subnets will force traffic into the Layer 3 router to bridge between subnets (ARP will not be used despite potential to be on the same physical network)

## Layer 4 Transport

### TCP 3 way handshake

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

## DNS

A: translates a domain name to an IP(V4)

AAAA: translates a domain name to an IP(V6)

PTR: translates an IP to a domain

CNAME: (canonical name) points one domain name to another domain

SOA: (Start of Authority) administrative details of domain: email of admin, TTL, last update

NS: (Name Server) shows what server holds the actual A record

MX: directs email to mail server

TXT: human-readable notes including SPF (sender policy framework) which indicates mail servers allowed to send mail on behalf of domain










Next File: Security
ssh
tls
starttls (opportunistic TLS)

ACL, firewalls
