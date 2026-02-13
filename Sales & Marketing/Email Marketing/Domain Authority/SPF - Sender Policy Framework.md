- Represented as a DNS server 'TXT' record
- DNS record value contains declaration of all servers authorised to send emails from the given server domain name (i.e: `https://scottwebdev.net`)
	- Originally introduced because SMTP does not inherently authenticate the "from" address in email, allowing domain impersonation attempts
- SPF used to demand it's own standalone DNS type
	- Has since been deprecated
- Serves a purpose analogous to that of an 'Email transaction doorman'
	- An SPF record contains a list of allowed guests into a building

### How does it work?

**Scenario:**
- Two independent mail servers:
	- 'Bob's mail server' =>
		- I.P: `192.0.2.0`
		- Return path: `email@returnpath.com`
			- A return path is unique from sender "from" address  - for collecting 'bounced' messages
	- 'Jane's mail server' => 

1. 'Bob's mail server' publishes a message to 'Jane's mail server' with it's known return path _(above)_
2. 'Jane's mail server' receives the message
	1. Identifies 'return path' email address, extracts domain name only and looks up SPF record for corresponding DNS server configuration
	2.  If SPF record identification for a given email address is unsuccessful, reject message (_assumed_)
3. If SPF lookup in previous step is successful, 'Jane's Mail Server' inspects SPF records text value for an I.P address matching the I.P address of the server which originally transmitted the email here.
	1. If negative on sender I.P address lookup in SPF record, authentication failure and messsage submitted to spam 