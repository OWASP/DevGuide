[Authentication][csauthn] is the process of verifying that an individual or entity is who they claim to be.
Session management is a process by which a server maintains the state of the users authentication
so that the user may continue to use the system without re-authenticating.

Refer to proactive control [C7: Implement Digital Identity][control7] and its [cheatsheets][csproactive-c6]
for more context from the OWASP Top 10 Proactive Controls project,
and use the list below as suggestions for a checklist that has been tailored for the individual project.

#### 1. Authentication

1. Design access control authentication thoroughly up-front
2. Force all requests to go through access control checks unless public
3. Do not hard code access controls that are role based
4. Log all access control events
5. Use [Multi-Factor Authentication][csmfa] (MFA) for sensitive or high value transactional accounts
6. Authentication failure responses should not indicate which part of the authentication data was incorrect.
   E.g. Through giving different textual response or HTTP response codes
7. Authentication failure responses should not give away the existent of user accounts allowing the response time to differ,
   depending on whether a username exist or not. Use a DB transaction that looks for a fake user profile in case the username
   doesn't exist
8. Add a random tunable delay for authentication failures to defer brute force attacks and protect against timing attacks

#### 2. Passwords

1. Require authentication for all pages and resources, except those specifically intended to be public
2. All authentication controls must be enforced on a trusted system
3. Establish and utilize standard, tested, authentication services whenever possible
4. Use a centralized implementation for all authentication controls
5. Segregate authentication logic from the resource being requested and
    use redirection to and from the centralized authentication control
6. All authentication controls should fail securely
7. Administrative and account management must be at least as secure as the primary authentication mechanism
8. If your application manages a credential store, use cryptographically strong one-way salted hashes
9. Password hashing must be implemented on a trusted system
10. Validate the authentication data only on completion of all data input
11. Authentication failure responses should not indicate which part of the authentication data was incorrect
12. Utilize authentication for connections to external systems that involve sensitive information or functions
13. Authentication credentials for accessing services external to the application should be stored in a secure store
14. Use only HTTP POST requests to transmit authentication credentials
15. Always send non-temporary passwords over an encrypted connection or as encrypted data
16. Enforce password complexity and length requirements established by policy or regulation
17. Enforce account disabling after an established number of invalid login attempts
18. Password reset and changing operations require the same level of controls as account creation and authentication
19. Password reset questions are deprecated, see [Choosing and Using Security Questions Cheat Sheet][csquestions] as to why
20. If using email based resets, only send email to a pre-registered address with a temporary link/password
21. Temporary passwords and links should have a short expiration time
22. Enforce the changing of temporary passwords on the next use
23. Notify users when a password reset occurs
24. Prevent password re-use
25. The last use (successful or unsuccessful) of a user account should be reported to the user
    at their next successful login
26. Change all vendor-supplied default passwords and user IDs or disable the associated accounts
27. Re-authenticate users prior to performing critical operations
28. If using third party code for authentication inspect the code carefully
    to ensure it is not affected by any malicious code
29. Password entry should be masked (e.g., on web forms use the input type "password") on the user's screen unless
    temporarily made viewable by the user
30. Ensure that no credentials are stored in clear text or are easily retrievable in encoded or encrypted forms in the
    browser's storage mechanisms

#### 3. Cryptographic based authentication

1. Use the server or framework's session management controls
2. Session identifier creation must always be done on a trusted system
3. Session management controls should use well vetted algorithms that ensure sufficiently random session identifiers
4. Set the domain and path for cookies containing authenticated session identifiers
    to an appropriately restricted value for the site
5. Logout functionality should fully terminate the associated session or connection
6. Logout functionality should be available from all pages protected by authorization
7. Establish a session inactivity timeout that is as short as possible,
    based on balancing risk and business functional requirements
8. Disallow persistent logins and enforce periodic session terminations, even when the session is active
9. If a session was established before login, close that session and establish a new session after a successful login
10. Generate a new session identifier on any re-authentication
11. Do not allow concurrent logins with the same user ID
12. Do not expose session identifiers in URLs, error messages or logs
13. Implement appropriate access controls to protect server side session data
    from unauthorized access from other users of the server
14. Generate a new session identifier and deactivate the old one periodically
15. Generate a new session identifier if the connection security changes from HTTP to HTTPS,
    as can occur during authentication
16. Set the `secure` attribute for cookies transmitted over an [TLS][tls] connection
17. Set cookies with the `HttpOnly` attribute,
    unless you specifically require client-side scripts within your application to read or set a cookie value

#### 4. Session Management

1. All active sessions must be terminated when a user account is disabled or deleted
2. After a successful change or removal of any authentication factor give the option to terminate all other active sessions
3. Supplement standard session management for sensitive server-side operations, like account management, by requiring and
   validating anti-forgery tokens (CSRF tokens) for each request that may change application state or execute an action

#### References

* OWASP [Cheat Sheet: Authentication][csauthn]
* OWASP [Cheat Sheet: Choosing and Using Security Questions][csquestions]
* OWASP [Cheat Sheet: Forgot Password][csforgot]
* OWASP [Cheat Sheet: Multifactor Authentication][csmfa]
* OWASP [Cheat Sheet: Password Storage][cspass]
* OWASP [Cheat Sheet: Session Management][cssession]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060206] or [edit on GitHub][edit060206].

[csproactive-c6]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c6-implement-digital-identity
[control7]: https://top10proactive.owasp.org/the-top-10/c7-secure-digital-identities/
[csauthn]: https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet
[csmfa]: https://cheatsheetseries.owasp.org/cheatsheets/Multifactor_Authentication_Cheat_Sheet
[cspass]: https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet
[csforgot]: https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet
[cssession]: https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet
[csquestions]: https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet
[edit060206]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/02-web-app-checklist/06-digital-identity.md
[issue060206]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/06-digital-identity
[proactive10]: https://top10proactive.owasp.org
[tls]: https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet
