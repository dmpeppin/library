# Cryptography Basics

Cryptography grants the means to grant technological solutions to problems present on the modern day web.
- Privacy of communication
- Authentication
- Integrity

## Privacy (encryption)

Information can be encrypted with a secret cryptographic key such that the information cannot be discern without first decrypting with a secret cryptographic key
- symmetric key (AES) uses the same secret key for encryption and decryption
- assemmetric key (RSA) uses a public key to encrypt that only the holder of the private key can decrypt
- key exchange (D.H.) two parties arrive at a secret key through a secret + shared starting point

Symmetric encryption uses the same key for encryption and decryption

Assymmetric encryption uses
1) for authorized recipient, the public key is used for encryption and the private key is used for decryption
2) for authorized senders, the private key is used for encryption and the the public key is used for decryption

Diffie Hellman allows 2 parties to agree on a secret code. Both parties agree (publicly) on a starting point, and through secret transformations, arrive at a consistent end point that can be used as an encryption key. 

## Authentication

Assemmetric encryption can be used to derive authentication. When a message is encrypted with a public key, only the corresponding private key can perform decryption. Conversly when a message is encrypted and can be decrypted by a public key, only the private key can have done the original encryption


TLS

1) a website requests a certificate from a certificate authority
2) the website proves its identity tot he certificate authority by sending communications from the IP address stated in the CNAME for a domain
3) the certificate authority signs (see below) the information relating to the website (IP address, domain name, public key, other info)  with it's private key
4) the certificate authority gives it's public key to user's web browsers
5) the user visits the website and asks for it certificate
6) the website shares the certificate with the user
7) the user decrypts the certificate with the certificate authority's public key (verifying the CA has generated the certification)
8) the user recieves the public key of the website in the certificate
9) the user proposes an encryption key and encrypts it with the servers public key
10) the website decrypts the encryption key with it's private key
11) the user and website now share a secret encryption key


## Integrity

Hashing can be performed on information to generate a "fingerprint" of the information.  (SHA)
- Only the original information can have generated this fingerprint. 
- It is impossible to prepare information that will generate a specific fingerprint. (hashing is a one-way operation, easy to compute, difficult to reverse)
- SHA is condidered secure, MD5 is condidred insecure, but sufficent for low security applications
- Passwords are generally hashed before storing, since the hash can verify the correct password
- Hashing can be done to verify information is valid and complete

Signatures can be used to verify the source of information
- Only I can encrypt information with my private key
- Only my private key can decrypt information encrypted by my private key
- I can hash my information, encrypt the hash with my private key, and the recipient can decrypt the hash and verify the contents are authentic

## Non-repudiation

Prevents sender of message to deny that they are the sender
