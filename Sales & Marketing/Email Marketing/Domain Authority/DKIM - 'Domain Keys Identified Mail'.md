- DKIM stands for 'Domain Keys Identified Mail'
- Anti-phishing measure
- DKIM typically represented by 3 server DNS records
- Prevents illicit impersonation of a legitimate website domain
- Introduces 'Digital Signature schemes'
	- Enforces **public key cryptography** on emails

> Suppose Chuck wants to trick Alice, who works for example.com, into sending him confidential company information. He could send her an email that seems to be coming from "bob@example.com" to fool her into thinking he also works for example.com.
> 
> DKIM, along with [Sender Policy Framework (SPF)](https://www.cloudflare.com/learning/dns/dns-records/dns-spf-record/) and [Domain-based Message Authentication Reporting and Conformance (DMARC)](https://www.cloudflare.com/learning/dns/dns-records/dns-dmarc-record/), makes it much more difficult for attackers to impersonate domains in this way

<sup><i>source: </i><a href="https://www.cloudflare.com/en-gb/learning/dns/dns-records/dns-dkim-record/">Cloudflare</a></sup>

### How does it work? 

- DKIM system comprised of 2 components:
	- Server **DKIM DNS** record
	- Actual **DKIM header** per-email

1. Email Service provider generates public and private crypto key
	1. Hands **generated public key** to DNS domain name holder to store against domain as 'DKIM' record
2. From then on, every time an email is sent from that domain:
	1. Email Service Provider embeds a 'DKIM' header in the message header
		1. DKIM section in header contains a string or identifier _signed with_ the ESP's secret key 
3. Recipient mail server will look up sender's DNS server from 'from' address
	1. Looks for 'DKIM' record and uses public key to decrypt the 'DKIM' message header it has recieved
		1. What is left after attempted decryption process determines whether or not the email has been tampered with in transit or is suspicious with regards to domain impersonation