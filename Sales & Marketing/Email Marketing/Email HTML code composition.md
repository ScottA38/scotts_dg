<sup><i>Reference prompt to <a href="https://claude.ai/">Claude.ai</a></i><br/><q>I’m about to send a test email

Are you able to provide me with a raw HTML sample email based upon the layout and styling of scottwebdev.net that has placeholder links that I can supplant with UTM links from Google Analytics?</q></sup>

### Summary notes
- HTML in emails has a different norms to Web Pages, _i.e_:
	- No seperate CSS stylesheets
		- CSS must be inlined
	- No JavaScript is allowed to run within emails
		- (really? Google analytics scripts run in emails, right?)
	- All HTML elements must be arranged inside of an HTML structure