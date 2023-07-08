- PGP: original concept, upgraded to a propiety system using IDEA encryption
- OpenPGP: standard that defines PGP concepts
- GPG: independent implementation of OpenPGP, using AES, tool used today


`gpg --gen-key`   generates public and private key pair, with contact info, possible password protection

`gpg --list-keys` list keys in local keyring

      /home/user/.gnupg/pubring.kbx
      -----------------------------------
      pub   rsa3072 2019-12-11 [SC] [expires: 2021-12-10]
      C4A3CFC51B1318FFD4D2C291D81710193A5FC56A
      uid           [ultimate] user <user@email>
      sub   rsa3072 2019-12-11 [E] [expires: 2021-12-10]

Example of public key (note pub prefix)

`gpg --export name@email --output file.gpg --armor`
- `--armor` puts key in ASCII format
- `--export` selects key to export based on email tag

`gpg --import file.gpg`

`gpg --armor --output message.enc --encrypt --recipient user@email message.txt`

encrypts message.txt with the public key stored under user@email

`gpg --output decryptedmessage.txt --decrypt message.enc`

decrypts message.enc with the private key

`gpg --output signature.txt --armor --detach-sig message.txt`

`--output signature.txt` creates the signature file

`--detach-sig message.txt` creates a detached based on message.txt

`gpg --verify signature.txt message.txt` 
