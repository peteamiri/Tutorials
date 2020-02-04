# Domain Name System

Is a higherarchal distributed database. that is mainly translates the `computer host names` into IP (this is called resolutions). Or translate an IP to a dommain name.

* `Forward Lookup` is the process of translating the hostname to IP.
*  `Reverse lookup` is a process of translating the IP to hostname. This is used in troubleshooting.
* `Fully Qulified Domain Name (FQDN)` : is a hostname + domain name + a dot that disgnates as the root server. This is similar to file structre, with / root directory. The hstname is resovlved from right to left.
  - Root Domain
  - TLD
  - Second lavel domains (google in google.com)
  - Sub domains / hostnames
    - Sub domains is a logical grouping of serveres
    - Hostnames ar actual server names

# Layers of Servers
* Root Server; they are manages by ICANN (13 Servers)
* `Top Layer Domain (TLD)` Servers various orgnization
  - There are two types of TLD's
    - GTLD (Global TLD) example: example.com
    - CCTLD (Contry Code TLD) example : example.co.uk
* Authoritative Servers

`default DNS Server` in most cases is `ISP DNS Server`

# Proces of converting Domain Name into the IP addoress

This is a recursive process;

1. put domain name on your browser
1. Browser calls send the information to `resolver`. `Resolver` is build into the computer operatingg system.
1. Looks into /etc/hosts file to see if info is there
1. Looks into the `resolver cache`
   1. if so, returns the IP address
   2. Otherwise, Conversts the Domains name to Fully qualifies Names (Add a dot at the end), example.com becomes example.com. and calls the DNS server (ISP)
1. The DNS Server will look int its own ressolver `DNS cache`
2. if IP is not resoolved it will start by asking the `root server` this servers IP are in the DNS Server.
   3. The DNS Server will call the second layer domain on behalf of your PC
1. then the `authoritave server` to get the IP
2. when done sends the information to the resolver in your PC.

Apex name : is example.com

#### For more information see
* [Short Video](https://www.youtube.com/watch?v=4a3MGDAoljI)
* [IANA](https://www.iana.org/domains)
* [Wiki](https://en.wikipedia.org/wiki/Domain_Name_System)
* [wiki](https://en.wikipedia.org/wiki/DNS_root_zone)
* [Redhat](https://www.redhat.com/sysadmin/dns-domain-name-servers)

-----
Commands asociated with this are

* ifconfig/ipconfig
  - /displaydns
  - /flushdns
  - /registerdns
* dig +trace
* Whois
* nslookup
-----

`Registry`: A domain name registry is an organization like `NeuStar` or `VeriSign` that manages top-level domain names. They create domain name extensions, set the rules for that domain name, and work with registrars to sell domain names to the public. For example, VeriSign manages the registration of .com domain names and their domain name system (DNS).

`Registrar`: The registrar is an accredited organization, like GoDaddy, that sells domain names to the public. Some have the ability to sell top-level domain names (TLDs) like .com, .net and .org, or country-code top-level domain names (ccTLDs) such as .tv, .us, .ca and .eu.

`Registrant`: A registrant is the person or company who registers a domain name. Registrants can manage their domain name’s settings through their registrar. When changes are made to the domain name, their registrar will communicate the changes to the registry to be updated in the registry’s database. When you register a domain name, you become a registrant!

----

# Caching name server

`Caching name servers (DNS caches)` store DNS query results for a period of time determined in the configuration (time-to-live) of each domain-name record. DNS caches improve the efficiency of the DNS by reducing DNS traffic across the Internet, and by reducing load on authoritative name-servers, particularly root name-servers. Because they can answer questions more quickly, they also increase the performance of end-user applications that use the DNS. Recursive name servers resolve any query they receive, even if they are not authoritative for the question being asked, by consulting the server or servers that are authoritative for the question. Caching name servers are often also recursive name servers—they perform every step necessary to answer any DNS query they receive. To do this the name server queries each authoritative name-server in turn, starting from the DNS root zone. It continues until it reaches the authoritative server for the zone that contains the queried domain name. That server provides the answer to the question, or definitively says it can't be answered, and the caching resolver then returns this response to the client that asked the question. The authority, resolving and caching functions can all be present in a DNS server implementation, but this is not required: a DNS server can implement any one of these functions alone, without implementing the others. Internet service providers typically provide caching resolvers for their customers. In addition, many home-networking routers implement caching resolvers to improve efficiency in the local network. Some systems utilize nscd - the name service caching daemonfs

## Hacking

* DNS Tunneling
* DNS Spoofing (DNS Cache Poisening)
* DNS HiJacking
* NXDomain Attack (This is like DDos but at the DNS level)
* Phantom Domain Attack
* 
