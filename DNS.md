## DNS Records

A: translates a domain name to an IP

PTR: translates an IP to a domain

CNAME: (canonical name) points one domain name to another domain

SOA: (Start of Authority) administrative details of domain: email of admin, TTL, last update

NS: (Name Server) shows what server holds the actual A record

MX: directs email to mail server

TXT: human-readable notes including SPF (sender policy framework) which indicates mail servers allowed to send mail on behalf of domain


## nslookup

`nslookup <domain>`

A record results, cached or primary sourced

`nslookup -type=NS <domain>` 
