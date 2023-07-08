# VPN

IPsec
- Tunnel Mode - entire IP packet is encrypted
	- AH (Authentication Header, Protocol 51) grants authentication  of packet (struggles with NAT since IP's are stripped and replaced, thus failing authentication)
	- ESP (Encapsulating Security Payload, Protocol 50) grants confidentiality of data through encryption

SSTP (Secure Socket Tunneling Protocol) - uses TLS over port 443

```
```

Split Tunnel - some, but not all traffic uses the VPN

Full Tunnel - all traffic uses the VPN

### VPN Authentication
- PAP (Pasword Authentication Protocol) - password sent in clear text
- MS-CHAPv2 (Challenge Handshake Authentication Protocol) - server challenges the client, client responds with authentication information
- RADIUS (Remote Authentication Dial-In User Service) - centralized authentication system
