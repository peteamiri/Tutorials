# Terminology

* `Vulnerability` : Weakness in System (Ex: Buffer Overflow , memory leaks etc.
)
* `Exploit` : Security Attack on the Vulnerability (Ex: Attacker use BOF to
execute his own code )
* `Payload` : Sequence of code that is executed when vulnerability is
triggered
* `Shell codes` : Shell payloads which provides interactive shell to control
compromise system
* `Encoder` : A software which converts a piece of code into another form
* `Auxillary` : Code’s other than exploits and vulnerability
* `Session` : Successful connection after exploitation

## Public Exploits

* [Security Focus](https://www.securityfocus.com/)
* [Exploit Database](https://www.exploit-db.com/)
* [Packet Strom](https://packetstormsecurity.com/)
* [1337 Day](http://1337day.com/)
* [Searchsploit github](https://github.com/offensive-security/exploitdb)
* [Searchsploit] On Kali Linux


Metasploit

## Searchsploit on Kali

Fully upgrade the Linux
`sudo apt update && sudo apt -y full-upgrade`

Get the application: use the following comand
`udo apt update && sudo apt -y install exploitdb`

Update the database
`searchsploit -u`

### Starting Point
