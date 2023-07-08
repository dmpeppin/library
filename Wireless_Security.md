# Wireless Security

## Wireless Cryptographic Protocols
- WEP (Wired Equivalent Privacy) - old, depreciated encryption **no longer secure**
- WPA (Wi-Fi Protected Access) - replacement for WEP without requiring updated hardware **no longer secure**
	- TKIP (Temporal Key Integrity Protocol) - encryption protocol for WPA
- WPA2 (Wi-Fi Protected Access V2) - latest permanent replacement for WPA
	- CCMP (Cipher Block Chaining Message Authenticatin Code Protocol) - encryption protocol for WPA2

## Authentication
- PSK (Pre-shared Key)
- Enterprise (credentials based)
- EAP - uses secure encryption key
- EAP-FAST - Cisco implemntation that has the option to use certificates
- PEAP - EAP negotiation in TLS tunnel, server needs a certificate
- EAP-TLS - EAP negotation in TLS tunnel, server and client need certificates
- RADIUS - SSO 

## Attacks

- Disassociation - forging session termination packets to disconnect clients
- WPS brute force - brute force the WPS pin to find a passphrase
- Rogue AP - can sniff traffic, could potentially attach to a network device
- Evil Twin - duplicate SSID to spoof authentication
- Jamming - causing interference to slow down or disrupt wifi traffic
- IV Attack - flooding with packets to force reuse of a IV number
- Replay Attack - captures data, modifies the traffic then later replays while impersonating one of the parties
