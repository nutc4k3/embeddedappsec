# Identity Management

User accounts within an embedded device should not be static in nature. Features that allow separation of user accounts for internal web management, internal console access, as well as remote web management and remote console access should be available to prevent automated malicious attacks.

**Considerations:**

* Static passwords utilized for web management and terminal access across product lines should not be used, or be removed as part of the release process.
  * If static default passwords NEED to be used in the interim, ensure that users are forced to change their passwords upon device setup and activation.
  * Ensure that users have the option to change all passwords/pins/passphrases etc. to ALL built in accounts.
* Pre-production account validation scripts should be adjusted in a similar fashion to those that validate WIFI and WPS passwords if applicable.
* Implement remote login and local login account features for users.
* Separation of users for SSH login and Admin login.
* Remote login should implement a temporary account lockout threshold to prevent automated brute force attacks.
* For web management interface:
  * Ensure Session IDs are sent in the request body, not in the URL.
  * Ensure Session IDs are invalidated when users log out.
  * Ensure active Session IDs are invalidated when passwords are changed.
  * If Session IDs are stored in a cookie, ensure that the cookie has the HttpOnly flag set.
  * Ensure Session IDs are random and change across sessions.
* Ensure usernames, passwords and cookies containing Session IDs are not sent over insecure protocols \(e.g. HTTP, FTP and Telnet\).
* Password complexity policies should be enforced to discourage easy to guess passwords such as “Password1”. A complex password should have the following attributes:
  * At least 10 characters or more in length
  * At least one upper-case letter
  * At least one numeric character
  * At least one lower-case letter
  * At least one special character
* Ensure EEPROMs are password protected enforcing complexity requirements.
* Employ key and certificate rotation policies

## Additional References <a id="additional-references"></a>

* [NIST Special Publication 800-63B](https://pages.nist.gov/800-63-3/sp800-63b.html)
* [FTC Charges D-Link Put Consumers’ Privacy at Risk Due to the Inadequate Security of Its Computer Routers and Cameras](https://www.ftc.gov/news-events/press-releases/2017/01/ftc-charges-d-link-put-consumers-privacy-risk-due-inadequate)
* [https://www.owasp.org/index.php/Testing\_Identity\_Management](https://www.owasp.org/index.php/Testing_Identity_Management)
* [https://www.owasp.org/images/6/67/OWASPApplicationSecurityVerificationStandard3.0.pdf](https://www.owasp.org/images/6/67/OWASPApplicationSecurityVerificationStandard3.0.pdf) \(Page 26-31\)
* [SB-327 Information privacy: connected devices](https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=201720180SB327)

