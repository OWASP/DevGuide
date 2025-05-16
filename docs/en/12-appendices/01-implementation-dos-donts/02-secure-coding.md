Here is a collection of Do's and Don'ts when it comes to secure coding, gathered from practical experiences.
Some of these are language specific and others have more general applicability.

* Authentication
  * User
    * Require authentication for all pages and resources, except those specifically intended to be public
    * Perform all authentication on server side. Send credentials only on encrypted channel (HTTPS)
    * Use a centralized implementation for all authentication controls, including libraries that call external
        authentication services. Use security vetted libraries for federation (Okta / PING / etc).
        If using third party code for authentication, inspect the code carefully to ensure it is not affected
        by any malicious code
    * Segregate authentication logic from the resource being requested and use redirection to and from
        the centralized authentication control
    * Validate the authentication data only on completion of all data input,
        especially for sequential authentication implementations
    * Authentication failure responses should not indicate which part of the authentication data was incorrect.
        For example, instead of "Invalid username" or "Invalid password",
        just use "Invalid username and/or password" for both.
        Error responses must be truly identical in both display and source code
    * Utilize authentication for connections to external systems that involve sensitive information or functions
    * Authentication credentials for accessing services external to the application should be encrypted
        and  stored in a protected location on a trusted system (e.g., Secrets Manager).
        The source code is NOT a secure location.
    * Do not store passwords in code or in configuration files. Use Secrets Manager to store passwords
    * Use only HTTP POST requests to transmit authentication credentials
    * Implement monitoring to identify attacks against multiple user accounts, utilizing the same password.
        This attack pattern is used to bypass standard lockouts, when user IDs can be harvested or guessed
    * Re-authenticate users prior to performing critical operations
    * Use Multi-Factor Authentication for highly sensitive or high value transactional accounts
    * If using third party code for authentication, inspect the code carefully
        to ensure it is not affected by any malicious code
    * Restrict the user if a pre-defined number of failed logon attempts exceed.
        Restrict access to a limited number of attempts to prevent brute force attacks
    * Partition the portal into restricted and public access areas
    * Restrict authentication cookies to HTTPS connections
    * If the application has any design to persist passwords in the database, hash and salt the password
        before storing in database. Compare hashes to validate password
    * Authenticate the user before authorizing access to hidden directories
    * Ensure registration, credential recovery, and API pathways are hardened against account enumeration attacks
        by using the same messages for all outcomes.
  * Server
    * When using SSL/TLS, ensure that the server identity is established by following a trust chain
        to a known root certificate
    * When using SSL/TLS, validate the host information of the server certificate.
    * If weak client authentication is unavoidable, perform it only over a secure channel
    * Do not rely upon IP numbers or DNS names in establishing identity.
    * Ensure all internal and external connections (user and entity) go through an appropriate
        and adequate form of authentication. Be assured that this control cannot be bypassed.
    * For the account that runs the web server:
      * Grant permissions to only those folders that the application needs to access
      * Grant only those privileges that the account needs
    * Disable HTTP TRACE.
        It can help in bypassing WAF because of it inherent nature of TRACE response includes all headers on its route.
        Please see - [Three Minutes with the HTTP TRACE Method][trace] - for further details
    * Disable WEBDav feature unless it is required for business reasons.
        If it is, perform a risk assessment for enabling the feature on your environment.
    * Ensure that authentication credentials are sent on an encrypted channel
    * Ensure development/debug backdoors are not present in production code.
  * Password policy
    * Provide a mechanism for self-reset and do not allow for third-party reset.
    * If the application has any design to persist passwords in the database, hash and salt the password
        before storing in database. Compare hashes to validate password.
    * Rate limit bad password guesses to a fixed number(5) in a given time period (5-minute period)
    * Provide a mechanism for users to check the quality of passwords when they set or change it.
    * Only send non-temporary passwords over an encrypted connection or as encrypted data,
        such as in an encrypted email. Temporary passwords associated with email resets may be an exception
    * Enforce password complexity requirements established by policy or regulation.
        Authentication credentials should be sufficient to withstand attacks that are typical
        of the threats in the deployed environment.
        (e.g., requiring the use of alphabetic as well as numeric and/or special characters)
    * Enforce password length requirements established by policy or regulation. Eight characters is commonly used,
        but 16 is better or consider the use of multi-word pass phrases
    * Password entry should be obscured on the user's screen. (e.g., on web forms use the input type "password")
    * Enforce account disabling after an established number of invalid login attempts (e.g., five attempts is common).
        The account must be disabled for a period of time sufficient to discourage brute force guessing of credentials,
        but not so long as to allow for a denial-of-service attack to be performed
    * Password reset and changing operations require the same level of controls as account creation and authentication.
    * Password reset questions should support sufficiently random answers.
        (e.g., "favorite book" is a bad question because “The Bible” is a very common answer)
    * If using email based resets, only send email to a pre-registered address with a temporary link/password
    * Temporary passwords and links should have a short expiration time
    * Enforce the changing of temporary passwords on the next use
    * Notify users when a password reset occurs
    * Prevent password re-use
    * For high risk application (for example banking applications or any application the compromise of credentials
        of which may lead to identity theft), passwords should be at least one day old before they can be changed,
        to prevent attacks on password  re-use
    * Enforce password changes based on requirements established in policy or regulation. Critical systems
        may require more frequent changes. The time between resets must be administratively controlled
    * Disable "remember me" functionality for password fields
    * Avoid sending authentication information through E-mail, particularly for existing users.
* Authorization
  * Access control
    * Build authorization on rules based access control.
        Persist the rules as a matrix (for example as a list of strings which is passed as a parameter to a method
        that is run when the user first access the page, based on which access is granted).
        Most frameworks today, support this kind of matrix.
    * Check if the user is authenticated before checking the access matrix.
        If the user is not authenticated, direct the user to the login page.
        Alternatively, use a single site-wide component to check access authorization.
        This includes libraries that call external authorization services
    * Ensure that the application has clearly defined the user types and the privileges for the users.
    * Ensure there is a least privilege stance in operation. Add users to groups and assign privileges to groups
    * Scan the code for development/debug backdoors before deploying the code to production.
    * Re-Authenticate the user before authorizing the user to perform business critical activities
    * Re-Authenticate the user before authorizing the user to admin section of the application
    * Do not include authorization in the query string. Direct the user to the page via a hyperlink on a page.
        Authenticate the user before granting access. For example if `admin.php` is the admin page for `www.example.com`
        do not create a query string like `www.example.com/admin.php`.
        Instead include a hyperlink to `admin.php` on a page and control authorization to the page
    * Prevent forced browsing with role based access control matrix
    * Ensure Lookup IDs are not accessible even when guessed and lookup IDs cannot be tampered with
    * Enforce authorization controls on every request, including those made by server side scripts,
        "includes" and requests from rich client-side technologies like AJAX and Flash
    * Server side implementation and presentation layer representations of access control rules must match
    * Implement access controls for POST, PUT and DELETE especially when building an API
    * Use the "referer" header as a supplemental check only, it should never be the sole authorization check,
        as it is can be spoofed
    * Ensure it is not possible to access sensitive URLs without proper authorization.
        Resources like images, videos should not be accessed directly by simply specifying the correct path
    * Test all URLs on administrator pages to ensure that authorization requirements are met.
        If verbs are sent cross domain, pin the OPTIONS request for non-GET verbs to the IP address of
        subsequent requests. This will be a first step toward mitigating DNS Rebinding and TOCTOU attacks.
  * Session management
    * Creation of session: Use the server or framework’s session management controls.
        The application should only recognize these session identifiers as valid
    * Creation of session: Session identifier creation must always be done on a trusted system (e.g., The server)
    * Creation of session: If a session was established before login,
        close that session and establish a new session after a successful login
    * Creation of session: Generate a new session identifier on any re-authentication
    * Random number generation: Session management controls should use well vetted algorithms
        that ensure sufficiently random session identifiers.
        Rely on CSPRNG rather than PRNG for random number generation
    * Domain and path: Set the domain and path for cookies containing authenticated session identifiers
        to an appropriately restricted value for the site
    * Logout: Logout functionality should fully terminate the associated session or connection
    * Session timeout: Establish a session inactivity timeout that is as short as possible,
        based on balancing risk and business functional requirements.
        In most cases it should be no more than several hours
    * Session ID: Do not expose session identifiers in URLs, error messages or logs.
        Session identifiers should only be located in the HTTP cookie header. For example,
        do not pass session identifiers as GET parameters
    * Session ID: Supplement standard session management for sensitive server-side operations, like account management,
        by utilizing per-session strong random tokens or parameters.
        This method can be used to prevent Cross Site Request Forgery attacks
  * JWT
    * Reject tokens set with ‘none’ algorithm when a private key was used to issue them (`alg: ""none""`).
        This is because an attacker may modify the token and hashing algorithm to indicate, through the ‘none’ keyword,
        that the integrity of the token has already been verified,
        fooling the server into accepting it as a valid token
    * Use appropriate key length (e.g. 256 bit) to protect against brute force attacks.
        This is because attackers may change the algorithm from ‘RS256’ to ‘HS256’ and use the public key to generate
        a HMAC signature for the token, as server trusts the data inside the header of a JWT
        and doesn’t validate the algorithm it used to issue a token.
        The server will now treat this token as one generated with ‘HS256’ algorithm
        and use its public key to decode and verify it
    * Adjust the JWT token validation time depending on required security level (e.g. from few minutes up to an hour).
        For extra security, consider using reference tokens if there’s a need to be able to revoke/invalidate them
    * Use HTTPS/SSL to ensure JWTs are encrypted during client-server communication,
        reducing the risk of the man-in-the-middle attack. This is because sensitive information may be revealed,
        as all the information inside the JWT payload is stored in plain text
    * Only use up-to-date and secure libraries and choose the right algorithm for requirements
    * Verify all tokens before processing the payload data. Do not use unsigned tokens.
        For the tokens generated and consumed by the portal, sign and verify tokens
    * Always check that the `aud` field of the JWT matches the expected value,
        usually the domain or the URL of your APIs. If possible, check the "sub" (client ID) - make sure that
        this is a known client. This may not be feasible however in a public API situation
        (e.g., we trust all clients authorized by Google).
    * Validate the issuer's URL (`iss`) of the token. It must match your authorization server.
    * If an authorization server provides X509 certificates as part of its JWT,
        validate the public key using a regular PKIX mechanism
    * Make sure that the keys are frequently refreshed/rotated by the authorization server.
    * Make sure that the algorithms you use are sanctioned by JWA ([RFC7518][rfc7518])
    * There is no built in mechanism to revoke a token manually, before it expires.
        One way to ensure that the token is force expired build a service that can be called on log out.
        In the mentioned service, block the token.
    * Restrict accepted algorithms to the ONE you want to use
    * Restrict URLs of any JWKS/X509 certificates
    * Use the strongest signing process you can afford the CPU time for
    * Use asymmetric keys if the tokens are used across more than one server
  * SAML
* Input data validation
  * Identify input fields that form a SQL query. Check that these fields
      are suitably validated for type, format, length, and range.
  * To prevent SQL injection use bind variables in stored procedures and SQL statements.
      Also referred as prepared statements / parameterization of SQL statements.
      DO NOT concatenate strings that are an input to the database.
      The key is to ensure that raw input from end users is not accepted without sanitization.
      When converting data into a data structure (deserializing), perform explicit validation for all fields,
      ensuring that the entire object is semantically valid.
      Many technologies now come with data access layers that support input data validation.
      These layers are usually in the form of a library or a package. Ensure to add
      these libraries  / dependencies / packages to the project file such that they are not missed out.
  * Use a security vetted library for input data validation. Try not to use hard coded allow-list of characters.
      Validate all data from a centralized function / routine.
      In order to add a variable to a HTML context safely, use HTML entity encoding
      for that variable as you add it to a web template.
    * Validate HTTP headers. Dependencies that perform HTTP headers validation are available in technologies.
    * Validate post backs from javascript.
    * Validate data from http headers, input fields, hidden fields, drop down lists & other web components
    * Validate data retrieved from database. This will help mitigate persistent XSS.
    * Validate all redirects. Unvalidated redirects may lead to data / credential exfiltration.
        Evaluate any URL encodings before trying to use the URL.
    * Validate data received from redirects. The received data may be from untrusted source.
    * If any potentially hazardous characters must be allowed as input,
        be sure that you implement additional controls like output encoding,
        secure task specific APIs and accounting for  the utilization of that data throughout the application.
        Examples of common hazardous characters include `< > " ' % ( ) & + \ \' \"`
    * If your standard validation routine cannot address the following inputs, then they should be checked discretely
      * Check for null bytes `%00`
      * Check for new line characters `%0d, %0a, \r, \n`
      * Check for “dot-dot-slash" `../` or `..\` path alterations characters.
          In cases where UTF-8 extended character set encoding is supported, address alternate representation like:
          `%c0%ae%c0%ae/`
          (Utilize canonicalization to address double encoding or other forms of obfuscation attacks)
    * Client-side storage (`localStorage`, `SessionStorage`, `IndexedDB`, WebSQL):
        If you use client-side storage for persistence of any variables,
        validate the date before consuming it in the application
    * Reject all input data that has failed validation.
    * If used, don’t involve user parameters in calculating the destination. This can usually be done.
        If destination parameters can’t be avoided, ensure that the supplied value is valid,
        and authorized for the user.
        It is recommended that any such destination parameters be a mapping value,
        rather than the actual URL or portion of the URL,
        and that server side code translate this mapping to the target URL.
        Applications can use ESAPI to override the `sendRedirect()` method
        to make sure all redirect destinations are safe.
* Output data encoding
  * If your code echos user input or URL parameters back to a Web page, validate input data as well as output data.
      It will help you prevent persistent as well as reflective cross-site scripting.
      Pay particular attention to areas of the application that permit users
      to modify configuration or personalization settings.
      Also pay attention to persistent free-form user input,
      such as message boards, forums, discussions, and Web postings.
      Encode javascript to prevent injection by escaping non-alphanumeric characters.
      Use quotation marks like " or ' to surround your variables.
      Quoting makes it difficult to change the context a variable operates in, which helps prevent XSS
  * Conduct all encoding on a trusted system (e.g., The server)
      Utilize a standard, tested routine for each type of outbound encoding
      Contextually output encode all data returned to the client
      that originated outside the application's trust boundary.
      HTML entity encoding is one example, but does not work in all cases
      Encode all characters unless they are known to be safe for the intended interpreter
      Contextually sanitize all output of untrusted data to queries for SQL, XML, and LDAP
      Sanitize all output of untrusted data to operating system commands
  * Output encoding is not always perfect. It will not always prevent XSS. Some contexts are not secure. These include:
      Callback functions
      Where URLs are handled in code such as this CSS `{ background-url : “javascript:alert(test)”; }`
      All JavaScript event handlers (`onclick()`, `onerror()`, `onmouseover()`).
      Unsafe JavaScript functions like `eval()`, `setInterval()`, `setTimeout()`
      Don't place variables into these contexts as even with output encoding, it will not prevent an XSS attack fully
  * Do not rely on client-side validation. Perform validation on server side to prevent second order attacks.
* Canonicalisation
  * Convert all input data to an accepted/decided format like UTF-8.  This will help prevent spoofing of character
* Test all URLs with different parameter values.
    Spider and check the site/product/application/portal for redirects.
* Connection with backend
    Assign required permissions and privileges for accounts / roles
    used by the application to connect to the database.
    In the event of any compromise of the account / role,
    the malicious actor would be able to do whatever the account /role has permissions for.
* Insecure direct object references
* Unvalidated redirects
    Test all URLs with different parameter values to validate any redirects
    If used, do not allow the URL as user input for the destination.
    Where possible, have the user provide short name, ID or token which is mapped server-side to a full target URL.
    This provides the protection against the URL tampering attack.
    Be careful that this doesn't introduce an enumeration vulnerability where
    a user could cycle through IDs to find all possible redirect targets
    If user input can’t be avoided, ensure that the supplied value is valid, appropriate for the application,
    and is authorized for the user.
    Sanitize input by creating a list of trusted URLs (lists of hosts or a regex).
    This should be based on an allow-list approach, rather than a block list.
    Force all redirects to first go through a page notifying users that they are going off of your site,
    with the destination clearly displayed, and have them click a link to confirm.
* JSON
    For JSON, verify that the Content-Type header is application/json and not text/html to prevent XSS
    Do not use duplicate keys. Usage of duplicate keys may be processed differently by parsers.
    For example last-key precedence versus first-key precedence.
* Generate fatal parse errors on duplicate keys.
    Do not perform character truncation. Instead, replace invalid Unicode with placeholder characters
    (e.g., unpaired surrogates should be displayed as the Unicode replacement character `U+FFFD`).
    Truncating may break sanitization routines for multi-parser applications."
* Produce errors when handling integers or floating-point numbers that cannot be represented faithfully
* Do not use `eval()` with JSON. This opens up for JSON injection attacks. Use JSON.parse() instead
    Data from an untrusted source is not sanitized by the server and written directly to a JSON stream.
    This is referred to as server-side JSON injection.
    Data from an untrusted source is not sanitized and parsed directly using the JavaScript `eval` function.
    This is referred to as client-side JSON injection.
    To prevent server-side JSON injections, sanitize all data before serializing it to JSON
    Escape characters like ":", "\", "@", "'”", "%", "?", "--", ">", "<", "&"

#### JSON Vulnerability Protection

A JSON vulnerability allows third party website to turn your JSON resource URL into JSONP request under some conditions.
To counter this your server can prefix all JSON requests with following string `")]}',\n"`.
AngularJS will automatically strip the prefix before processing it as JSON.

For example if your server needs to return: `['one','two']`
which is vulnerable to attack, your server can return: `)]}', ['one','two']`

Refer to [JSON vulnerability protection](https://docs.angularjs.org/api/ng/service/$http#json-vulnerability-protection)
Always have the outside primitive be an object for JSON strings

Exploitable: `[{""object"": ""inside an array""}]`

Not exploitable: `{""object"": ""not inside an array""}`

Also not exploitable: `{""result"": [{""object"": ""inside an array""}]}"`

* Avoid manual build of JSON, use an existing framework
* Ensure calling function does not convert JSON into a javascript
    and JSON returns its response as a non-array json object
* Wrap JSON in () to force the interpreter to think of it as JSON and not a code block
* When using node.js, on the server use a proper JSON serializer to encode user-supplied data properly
    to prevent the execution of user-supplied input on the browser.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue140102] or [edit on GitHub][edit140102].

[edit140102]: https://github.com/OWASP/DevGuide/blob/main/docs/en/12-appendices/01-implementation-dos-donts/02-secure-coding.md
[issue140102]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%20/12-appendices/01-implementation-dos-donts/02-secure-coding
[rfc7518]: https://www.rfc-editor.org/rfc/rfc7518
[trace]: https://www.blackhillsinfosec.com/three-minutes-with-the-http-trace-method/
