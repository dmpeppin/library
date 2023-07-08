## Defense in Depth

From largest to smallest scale

1. Perimeter
2. Network
3. Host
4. Application
5. Data


## Stateless vs Statefull

- Stateless: rules based on source/destination IP/port, some IP Protocols, Level 3, Level 4
- Statefull: tracks connection status (SYN, ACK) 


## Application (Proxy) Firewalls

- Inspects packet contents including authentication, encryption
- can protect from SQLi and XSS 

WAF

## UFW Firewall

`sudo ufw reset` reset ufw to default configuration

`sudo ufw status` check status of ufw

`sudo ufw status verbose`

`sudo ufw enable` enable ufw with current rules

`sudo ufw disable` disable ufw

`sudo ufw reload` reload current rules without stopping firewall

`sudo ufw default deny incoming` default applies to all traffic, incoming can also be outgoing

`sudo ufw allow 22` allows traffic to and from port 22

`sudo ufw delete <rule name, ie deny 22>` delete a previously written rule




## Firewalld

`sudo systemctl <command> firewalld` 

- *See systemd.md for commands to operate firewalld service

`sudo firewalld-cmd <args>` 

`--list-all` show all settings

`--zone=<zone>` show settings for a specific zone

`--get-services` show running services

`--add-rich-rule='<new rule>'` add new rule

`rule family="ipv4"` rules for IPV4 protocol

`source address="<IP>"` source IP rule applies to

`reject` reject all trafic from source address

`--add-icmp-block=echo-reply --add-icmp-block=echo-request` blocks ping requests
