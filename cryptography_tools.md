## steghide

`steghide embed -cf image.jpg -ef message.txt`

`-cf` cover file to embed into

`-ef` embeded file

`steghide extract -sf image.jpg`

`-sf` stegofile, file that contains the embed

## john the ripper


## hashcat

`hashcat -m 0 -a 0 -o solved.txt hash.txt rockyou.txt --force`

`-m 0` defines hash type

`a 0` defines attack type, in this case dictionary

`-o solved.txt` where the cracked hash output goes

`hash.txt` the text containing the hash

`--force` overrides any potential small errors

`rockyou.txt` wordlist to use

