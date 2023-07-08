## Nmap Usage

`nmap <ip server>`

`nmap <ip base/24>` scan subnet


### SYN (Stealth) Scan (-sS)

`-sS`

SYN (stealth) scan is the default, standard scan type, works only with privledge

General structure
- SYN from user nmap
- SYN/ACK from server
- RST from user OS

General Insights from response
- SYN/ACK response: port is open
- RST: port is closed
- no response: port is filtered
- ICMP unreachable error: port is filtered


### TCP ACK Scan (-sA)

`-sA`

Determines of firewall rules are stateful or stateless

General Insights from response
- RST: port is unfultered
- no response: port is filtered
- ICMP unreachable error: port is filtered


### TCP Connect Scan (-sU)

`-sT` TCP full connect scan

### UDP Scan

`-sU`

UDP scan

### FIN, NULL, XMAS Scans

If firewalls try to prevent incoming TCP connectsion (while allowing outboud ones) by blocking TCP SYN flags but allowing other flags
- -sN Null Scan has no TCP flag
- -sF TCP FIN bit
- -sX FIN, PSH, URG flags

General Insights from response
- no response: open or filtered
- RST: port is closed
- ICMP unreachable error: port is filtered

### Scripts

`-sC` enable common scripts

`-sn` do not scan ports, only host scripts would be used

types
- auth: authenticaiton credentials assessment
- brute: brute force authentication
- much, much more...

location of scripts `/usr/share/nmap/scripts`

### Other Arguements

`--packet-trace` shows packet level info

`-p 22,80,443,500-600` select ports

`--scanflags` choose custom TCP flags

`-O` OS fingerprinting, passive approach

`-A` OS fingerprinting, more active approach

`-sV` **enumerate service type**

`-v` verbosity

`-Pn` no pings, skips discovery phase

`-oN output.txt` output to file

### Logic

Filtered can mean firewall is protecting a system, or that a firewall is protecting nothing
- For statefull firewalls, ACK may be filtered while SYN is not
- For firewalls allowing out but filtering in, FIN may be allowed

Full TCP scans may generate entry in server logs, trigger additional scrutiny
