 - Email authentication directive specifically sequenced after [[SPF - Sender Policy Framework]] and [[DMARC - Domain-based Message Authentication Reporting and Conformance]] steps.
- Final measure to prevent [[Domain name spoofing]] 
- Represents a protocol for how a message handled after results are visible from message being processed by [[SPF - Sender Policy Framework]]  and [[DMARC - Domain-based Message Authentication Reporting and Conformance]]

> The DMARC policy determines if failure results in the email being marked as spam, getting blocked, or being delivered to its intended recipient. (Email servers may still mark emails as spam if there is no DMARC record, but DMARC provides clearer instructions on when to do so.)

<sup><i>source: </i><a href="https://www.cloudflare.com/en-gb/learning/dns/dns-records/dns-dmarc-record/">Cloudflare</a></sup>

- DMARC instructions are not human-readable
	- i.e: ```v=DMARC1; p=quarantine; adkim=s; aspf=s;```
		- `v=DMARC1;` _instructs server_: "Hey, this value should be interpreted as a DMARC statement"
		- `p=quarantine;` _instructs server_ "Server should quarantine emails which have failed both DKIM and SPF
			- `p=reject;` is a much stricter policy, _saying_ "If an email fails the DKIM and SPF tests, do not deliver it."
		- \[optional\] `akdim=s;` _instructs server_ "treat DKIM checks as strict"
			- `r` => _'relaxed'_ (or lenient)
		- \[optional\] `aspf=s;` _instructs server_ to make SPF checks strict