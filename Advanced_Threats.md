# Advanced Attacks

- DDoS
- Privilege Escalation
- Spoofing
- SYN Flood
- Man in the Middle (MITM)
- ARP Attacks
	- ARP Poisoning
	- ARP MITM
	- ARP DoS
- DNS Attacks
	- DNS Poisoning
	- Pharming (local DNS poisoning)
	- DDoS
- Amplification
	- ping amplification - send ping with phoney return IP
- Password Attacks
	- Brute Force
	- Dictionary
	- Pass the Hash - when hashing occurs client side, the hash is intercepted and reused
	- Birthday (Hash Collision)
	- Rainbow Table - when the hash is obtained, the hash is compared to a rainbow table
- Replay Attack - communication is recorded and run again (mitigated with time stamps)
- Plaintext - reverse the encryption with:
	- Known Plaintext - full plaintext + ciphertext
	- Chosen Plaintext - partial plaintext + ciphertext 
	- Ciphertext Only - ciphertext only
- Typo squatting (URL hijacking)
- Clickjacking - trick the user into clicking something other than what was intended
- Session hijacking - obtaining session information through cookie or session info stolen 
- Memory Buffer Attacks
	- memory leak - memory is not closed or managed properly by code
	- integer overflow
	- buffer overflow
- Pointer Dereference - failed reference causing crash or corruption
- SQL Injects - send database operation code
- Command Injects - send OS commands or file locations
- Cross-site Scripting (XSS) - send html or java code that the web browser can execute
- Cross-site Request Forgery - manipulate the URL to execute commands