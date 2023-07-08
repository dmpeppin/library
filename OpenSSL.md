## OpenSSL Symmetric Encryption

Seems best to be as explicit as possible as the default options may change, choosing the correct ciphers is obviously critical

`openssl enc -aes-256-cbc -salt -base64 -pdkbf2 -in inputfile.txt -out outputfile.enc`

`-e` default, set to encryption

`-d` sets to decrypt

`-P` prints keys but does not encrypt

`-p` prints keys and encrypts

`-aes-256-cbc` good encryption algorithm

`-salt` explicitly invokes salt function
- salt should be stored in the header of the key file, thus recoverable

`-base64` bits are encoded into ASCII characters
- every 3 bytes (24bits) are divided into 4 sets of 6bites
- 6bits are encoded into an ASCII character
-every 3bytes (24bits) can be encoded into 4 ASCII characters

`-pdkbf2` solid password hash function

`-iter 100000` number of iterations to use for pdkbf2

- seems pdkbf2 may not be default (is 3DES currently default??)
- default iterations (10000?) may not be enough
- pick enough iterations that it takes a computer 1-5s to iterate


## OpenSSL Asymmetric Encryption




## Other functions to explore for symmetric

`-md sha512` some sort of digest function

openssl "magic" bits

How does openssl store the magic and salt values
- magic value 8bytes?
- salt value 8bytes?

Verify: password + salt (in header) -> key + iv

`openssl enc -aes-256-cbc -salt -base64 -pdkbf2 -in inputfile.txt -P` should demonstrate that salt is randomly selected each run, thus creating new keys everytime it is run

`openssl enc -aes-256-cbc -salt -base64 -pdkbf2 -in inputfile.enc -d -P` should read file for salt, then print key + iv
