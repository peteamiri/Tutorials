# DNS Record Types 

DNS records or zone files store information about domains. They consist of a series of text files written in the DNS syntax and are stored on DNS servers.

## A Record
A (address) records are one of the most basic and commonly used DNS record types. They translate domain names and store them as IP addresses. A records can only hold IPv4 addresses.

An example of an A record is:

```
Domain name:	Record type:	Value:	TTL
example-website.com @	A	192.0.0.1	14400
```

In the example above, the record is made up of the following elements:

* ***Domain name***: Contains the domain name of the website. The "@" symbol indicates that the record contains the root domain name.
* ***Record type***: Indicates the usage of an A record type.
* ***Value***: Contains the IP address associated with the domain name.
* ***TTL***: Lists the record's TTL (Time to Live) in seconds. The default value is 14400, which means the record expires after 14400 seconds (240 minutes).

## AAAA Record

AAAA records work the same as A records in that they store IP addresses connected to domain names. The only difference is that AAAA records hold IPv6 addresses.

## AFSDB Record
AFSDB records connect a domain name to an AFS (Andrew File System) number. This record type is commonly used to contact AFS cells outside the client's local domain.

An AFSDB record example is:

```
Address:	TTL:	Internet type:	Record type:	Service subtype:	AFS cell server:
example-website.com	14400	IN	ASFDB	1	database01.example.com
```

The example above contains the following elements:

* ***Address***: Location of the AFSDB record.
* ***TTL***: Time until the record expires.
* ***Internet type***: Indicates that the record is on the Internet.
* ***Record type***: Indicates that this is an AFSDB record.
* ***Service subtype***: Can either be 1 for an AFS volume location server or 2 for a DCE authenticated server.
* ***AFS cell server***: The canonical database hostname.

## ATMA Record

An ATMA record maps a domain name to an ATM (Asynchronous Transfer Mode) address, expressed in either E.164 (decimal) or NSAP (hexadecimal) format. ATMA record entries use the following elements:

```
Host name:	Domain name:	Format:	Value:
Examplehost	example-website.com	E164	47.0091810000000060705A8F01.0060705A8F01.00
```

In the example above:

* ***Host name***: A single-part name for the ATM host, written without periods (".").
* ***Domain name***: The domain name you want to map to an ATM address.
* ***Format***: Can be E164 or NSAP.
* ***Value***: The ATM address mapped to the hostname.

## CAA Record
CAA records allow domain owners to determine which certificate authorities can issue certificates to that domain and all its subdomains. If there is no CAA record, anyone can issue certificates to the domain.

```
Domain name:	Record type:	Flag:	Tag:	CA:
example-webisite.com	CAA	0	issue	"caa-domain.com"
```

The CAA record example above contains the following elements:

* ***Domain name***: The name of the domain that is being certified.
* ***Record type***: Indicates that this is a CAA record.
* ***Flag***: Can be either 1 (critical) or 0 (non-critical). A critical flag means the certificate authority cannot use the CAA record if it doesn't understand the property. A non-critical flag means it can use the CAA record regardless of whether it understands the property.
* ***Tag***: The three tag options are issue (authorized to issue a single certificate), issuewild (authorized to issue a wildcard certificate), and iodef (specifies a URL for reporting policy violations).
* ***CA***: The certification authority that can issue certificates for the domain in question.

## CERT Record

CERT records provide a space for storing certificates and related certificate revocation lists (CRL). The certificates can verify the authenticity of sending and receiving parties, while CRLs identify unauthorized parties.

CERT records contain the following data fields:

Record type: Identifies the record as CERT.
TTL: Time until record expires.
Host: The domain name that is being certified.
Type: Defines the type of certificate/CRL used.
Key tag: A numeric value with the range of 0-65535, used to identify the CERT record.
Algorithm: Identifies the algorithm used to produce the certificate/CRL.
Points to: Base 64 encoded string.

## CNAME Record
A CNAME (canonical name) record is used instead of an A record if a domain is an alias for another domain. Because of this, all CNAME records point to a domain instead of an IP address.

For example, in a domain called alias-domain.com which works as an alias for real-domain.com, a CNAME record for would look like this:
```
Domain name:	Record type:	Value:	TTL
alias-domain.com @	CNAME	real-domain.com	14400
```

This record contains:

Domain name: Contains the alias domain name. The "@" symbol shows that this is a root domain name.
Record type: Shows that this is a CNAME record.
Value: Contains the real domain name that the alias domain is pointing to.
TTL: Time left until the record expires.
CNAE records usually contain subdomains that point to a domain's A or AAAA record. This prevents having to create an extra A or AAAA record for each subdomain.

It is not recommended to have CNAME records pointing to other CNAME records, as this creates unnecessary steps to the DNS lookup process.

## DHCID Record

DHCID records store DHCP (Dynamic Host Configuration Protocol) information. DHCP servers and clients generally create them through dynamic updates.

## DNAME Record

DNAME records are used to create an alias for every subdomain of a domain. They are similar to CNAME records, with the main difference being that CNAME can only store a single alias domain without any subdomains.

A hierarchy of several CNAME records under a single DNAME record
DNSKEY Record
DNSKEY records hold public data keys used to verify DNSSEC signatures. An example of a DNSKEY record might look like:

```
Host:	TTL:	Record class:	Record type:	Flags:	Protocol:	Algorithm:	Public key:
wxample-website.com	14400	IN	DNSKEY	257	3	13	ZhCa3rGLofZcndFN2aVd==
```

In the example above:

Host: Contains the domain name of the key holder. Domain names ending with a period do not append the origin to the label.
TTL: Time left until the record expires.
Record class: Can be IN (default), CH (used for querying DNS server versions), or HS (uses DNS functionality to provide access to databases).
Record type: Indicates that this is a DNSKEY record.
Flags: Contains "zone keys" for DNSSEC keys or "secure entry points" for simple keys.
Protocol: Must contain the value of 3. All other values are invalid.
Algorithm: Identifies the algorithm used to generate the public data key.
Public key: Contains the public data key.

## DS Record
DS (delegation signer) records are used to secure delegations in DNSSEC. These records reference DNSKEY records in their sub-delegated zones.

DS records contain the following elements:

Key tag: A numeric value that references a DNSKEY record.
Algorithm: Identifies the algorithm used to generate the referenced DNSKEY record.
Digest type: Specifies the cryptographic hash algorithm used to create the Digest value.
Digest: A cryptographic hash value for the referenced DNSKEY record.
HINFO Record
HINFO (host information) records store details about the hardware and operating system the host is using. Due to security concerns, only certain application protocols use this information which is rarely stored on public servers.

A typical HINFO record contains:

Host: The domain name of the host.
TTL: Time until record expiration.
Record class: Can be IN (default), CH (used for querying DNS server versions), or HS (uses DNS functionality to provide access to databases).
Record type: Identifies the record as HINFO.
CPU: A short description of the host's CPU.
Operating system: The name of the operating system the host is using.

## ISDN Record
An ISDN record maps the domain name to an ISDN (Integrated Services Digital Network) telephone number, using the ITU-T E.163/E.164 international telephone numbering standards.

This record type can contain an optional hexadecimal number as an ISDN sub-address.

MB, MG, MINFO, MR Records
MB, MG, MINFO, and MR records work as an alternative to the more commonly used MX records:

MB: Maps a mailbox to a host with an existing A record.
MG: Each MG record specifies a single mail group member. Each member must have a valid MB record.
MINFO: Points to an existing MB record as a mailbox of an administrator.
MR: Specifies a renamed mailbox. Forwards mail to a new mailbox in an existing MB record.
The relationship between mailbox record types
MX Record
MX (mail exchange) records store instructions for directing emails to mail servers following the SMTP protocol. An MX record might look like:

```
Domain name:	Record type:	Priority:	Value:	TTL:
example-website.com @	MX	10	mail.example-website.com	14400
```

In this example:

Domain name: Specifies the domain name.
Record type: Indicates an MX record.
Priority: Specifies preference when delivering mail, with lower values having higher priority. If there is a failure to deliver, the mail will be redirected to a lower-priority email server.
Value: Specifies an email server for the domain name.
TTL: Time left to record expiration.
Note: An MX record can only point to a name of an email server. This means that each referenced email server must also have a valid A record specifying its IP address.

## NAPTR Record

An NS (nameserver) record indicates which server contains the DNS records for a given domain. Domains usually have several NS records pointing to primary and backup nameservers for that domain.

A nameserver is a type of DNS server that contains all DNS records for a single domain.

Note: Learn more about how to set DNS nameserver on Ubuntu 20.04.

```
Domain name:	Record type:	Value:	TTL:
example-website.com @	NS	nameserver.example-server.com	14400
```

The example above contains the following elements:

Domain name: Contains the domain name.
Record type: Shows that this is an NS record.
Value: Specifies the nameserver for the provided domain.
TTL: Time until record expires.
NSAP Record
NSAP records map domain names to NSAP addresses, expressed in hexadecimal digits. NSAP addresses are similar to IP addresses and are used to identify equipment connected to an ATM network.

## NSEC Record
An NSEC (next secure) record links to the next record in the DNSSEC sorting order and lists the record types that exist for that record's name. These records are commonly used as a part of DNSSEC validation to verify if a record name exists or not.

NSEC records contain the following elements:

Next domain name: The name of the next record in the DNSSEC sorting order.
Record types: A list of all the record types that exist for the specified record name.

## NSEC3 Record

NSEC3 (next secure version 3) records work the same as NSEC records, except NSEC3 uses cryptographically hashed record names to prevent record names in a zone from being enumerated. These records contain the following elements:

Hash algorithm: Specifies the algorithm for generating the cryptographically hashed record name.
Flags: Allows turning delegations on or off.
Iterations: Indicates how many times the hash algorithm was applied.
Salt: Salt value for the hash calculation.
Next Hashed Owner Name: The name of the next record in the hashed name sorting order.
Record types: Lists the record types that exist for the hashed record name.

## NSEC3PARAM Record

An NSEC3PARAM (NSEC3 parameters) record contains a list of parameters associated with an NSEC3 record. It determines which NSEC3 records to include as a response when DNSSEC requests a nonexistent record name or type.

NSEC3PARAM records include the Hash algorithm, Flags, Iterations, and Salt elements of an appropriate NSEC3 record.

Comparing the elements of NSEC, NSEC3, and NSEC3PARAM record types

## PTR Record

PTR (pointer) records serve as an inverse of A or AAAA records. They map IP addresses to domain names and help perform reverse DNS lookups.

PTR records store IP addresses in reverse:

IPv4 addresses are saved with the segments in reverse order.
IPv6 addresses are saved in the reverse order of hexadecimal digits.
Note: Learn more about reverse DNS lookups and how they work.

## RP Record

RP (responsible person) records store mailboxes of persons responsible for a given domain name. Additional information, such as the responsible person's phone number or address, can be provided in a TXT record that the RP record maps to.

An example of an RP record:

```
Domain name:	TTL:	Record class:	Record type:	Mailbox:	TXT domain name:
example-website.com	14400	IN	RP	admin.example-website.com	moreinfo.examplewebsite.com
```

In this example:

* ***Domain name***: Provides a domain name.
* ***TTL***: The number of seconds left until the record expires.
* ***Record class***: Either IN (default), CH (used for querying DNS server versions), or HS (uses DNS functionality to provide access to databases).
* ***Record type***: Identifies this record as RP.
* ***Mailbox***: Stores the mail address of the person responsible for the domain name.
* ***TXT domain name***: Maps to a TXT record with additional information.

## RRSIG Record

An RRSIG record holds a DNSSEC signature for a set of one or more DNS records with the same name and type. These signatures can be verified with the public keys stored in DNSKEY records.

RRSIG records have the following elements:

Type covered: DNS record type the stored signature covers.

* ***Algorithm***: The cryptographic algorithm used to create the signature.
* ***Labels***: The number of labels associated with the original RRSIG record name used to validate wildcards.
* ***Original TTL***: The TTL value of the DNS record set.
* ***Signature expiration***: Time when the signature expires.
* ***Signature inception***: Time when the signature was created.
* ***Key tag***: A short numeric value for identifying the DNSKEY record that can validate the signature.
* ***Signer's name***: The DNSKEY record that can validate the signature.
* ***Signature***: Contains the DNSSEC cryptographic signature.

## RT Record

RT (route through) records are used to specify intermediate hosts that provide routing to the domain name stored in the record. Multiple intermediates can route to the same domain, with the lower preference value deciding who tries first.

Each intermediate host must also have a valid A record present.

## SOA Record

The SOA (start of authority) record holds important information about a domain or zone. These records are required by IETF standards and are an important element of zone transfers.

SOA records detail the following zone properties:

* ***Name***: Name of the primary DNS server for the zone. Each primary server should also have a matching NS record.
* ***Record type***: Indicates that this is an SOA record.
* ***MNAME***: Specifies the primary nameserver for the zone.
* ***RNAME***: The email address of the person responsible for the zone.
* ***Serial***: The zone's serial number.
* ***Refresh***: The number of seconds between checking for record updates.
* ***Retry***: The number of seconds before asking an unresponsive primary nameserver for another update.
* ***Expire***: How long to retry updating an unresponsive nameserver before stopping.
* ***TTL***: Time until record expires.

## SRV Record

SRV (service) records store host and port information for internet services, such as email or VoIP. Some internet protocols need valid SRV records to function.

SRV records hold the following information:

* ***Service***: Symbolic name for a service.
* ***Protocol***: Specifies if the service is using TCP or UDP protocols.
* ***Name***: Stores a domain name.
* ***TTL***: Time left until record expires.
* ***Class***: Can contain IN (default), CH (used for querying DNS server versions), or HS (uses DNS functionality to provide access to databases).
* ***Type***: Specifies record type as SRV.
* ***Priority***: Determines which server is looked at first, with lower values giving higher priority.
* ***Weight***: Determines which server is looked at first if more than one has the same priority value. Higher values give more priority.
* ***Port***: The TCP or UDP port the service is running on.
* ***Target***: The canonical hostname for the machine providing the service.

## TLSA Record

TLSA (Transport Layer Security Authentication) records store keys used in a domain's TLS servers. The names of TLSA records are made up of a port number, protocol name, and TLS server host name.

These records detail certificate usage, selector, and matching type as numeric values with a range of 0-255 and certificate association data as a hexadecimal value.

## TXT Record

TXT (text) records are used to store descriptive text. They are often used in combination with other record types to provide additional information that doesn't fit the format of other records.

```
Domain name:	Record type:	Value:	TTL:
example-website.com @	TXT	Example text.	14400
```

The example above shows a typical TXT record. It contains the following elements:

* ***Domain name***: Specifies a domain name.
* ***Record type***: Shows that this is a TXT record.
* ***Value***: Stores a user-defined text string.
* ***TTL***: Time until record expires.

Note: Text strings in TXT records have a maximum length of 255 characters.

## X25 Record

X25 records map domain names to a PSDN (Public Switched Data Network) address number following the X.121 international numbering plan.

