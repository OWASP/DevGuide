Sensitive data such as passwords, credit card numbers, health records, personal information and business secrets
require extra protection, particularly if that data falls under privacy laws (EU General Data Protection Regulation GDPR),
financial data protection rules such as PCI Data Security Standard (PCI DSS) or other regulations.

Refer to proactive control [C2: Use Cryptography to Protect Data][control2] and its [cheatsheets][csproactive-c8]
for more context from the OWASP Top 10 Proactive Controls project,
and use the list below as suggestions for a checklist that has been tailored for the individual project.

#### 1. Cryptographic practices

1. Use peer reviewed and open solution cryptographic modules
2. All cryptographic functions used to protect secrets from the application user must be implemented on a trusted system
3. Cryptographic modules must fail securely
4. Ensure all random elements such as numbers, file names, UUID and strings are generated
    using the cryptographic module approved secure random number generator
5. Build support for changing algorithms when needed
6. Cryptographic modules used by the application are compliant to FIPS 140-2 or an equivalent standard
7. Don't implement your own cryptographic protocols or routines. Use existing security vetted library and frameworks

#### 2. Data protection

1. Classify data according to the level of sensitivity
2. Implement appropriate access controls for sensitive data
3. Avoid storing sensitive data when at all possible
4. Implement least privilege, restricting access to functionality, data and system information
5. Do not include sensitive information in the URL or query string, such as an API key or session token
6. Disable client side caching on pages containing sensitive information (e.g. Cache-Control: no-store)
7. Set a referrer policy to prevent leakage of sensitive data to third-party services via the 'Referer' HTTP request header
    field. This can be done using the Referrer-Policy HTTP response header field or via HTML element attributes

#### 3. Secret Management

1. Establish and utilize a policy and process for how cryptographic keys will be managed
2. Ensure that any secret key is protected from unauthorized access
3. Store keys and application-level secrets in a proper secrets vault
4. Use independent keys when multiple keys are required
5. Build application features to handle a secret key rotation
6. Ensure that secrets are not stored in code, config files or environment variables
7. Scan code repositories to detect accidentally added secrets and credentials
8. Log all authorized access to a secret key for forensic purposes

#### 4. Memory management

1. Explicitly initialize all variables and data stores
2. Check that any buffers are as large as specified
3. Check buffer boundaries if calling the function in a loop and protect against overflow
4. Specifically close resources, don't rely on garbage collection
5. Use non-executable stacks when available
6. Properly free allocated memory upon the completion of functions and at all exit points
7. Overwrite any sensitive information stored in allocated memory at all exit points from the function
8. Protect shared variables and resources from inappropriate concurrent access
9. Avoid the use of known vulnerable functions

#### 5. Protect Data at Rest

1. Ensure sensitive data at rest is cryptographically protected to avoid unauthorized disclosure and modification
2. Purge sensitive data when that data is no longer required
3. Protect all cached or temporary copies of sensitive data from unauthorized access
4. Purge those temporary copies of sensitive data as soon as they are no longer required

#### 6. Protect Data in Transit

1. Encrypt data in transit
2. Ensure secure communication channels are properly configured
3. Utilize TLS connections for all connectivity between a client and external-facing, HTTP-based services
4. Ensure the TLS connections do not fall back to insecure or unencrypted communication
5. Turn off older protocols to avoid protocol downgrade attacks
6. Do not offer HTTP. Disable both HTTP and SSL compression
7. Utilize a single standard TLS implementation with (preferably the latest) secure version of TLS
8. Ensure the TLS connections are configured appropriately to validate certificates received before communicating and
   checking revocation status
9. Use the Strict-Transport-Security Header
10. Use Content-Security-Policy to enforce client-side upgrade from HTTP to HTTPS.
11. Always utilize the “secure” flag for cookies to prevent transmission over HTTP.

#### References

* OWASP [Cheat Sheet: Cryptographic Storage][cscs]
* OWASP [Cheat Sheet: Secrets Management][cssm]
* OWASP [Cheat Sheet: Transport Layer Security][cstls]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060208] or [edit on GitHub][edit060208].

[csproactive-c8]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c8-protect-data-everywhere
[control2]: https://top10proactive.owasp.org/the-top-10/c2-crypto/
[cscs]: https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet
[cssm]: https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet
[cstls]: https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet.html
[edit060208]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/02-web-app-checklist/08-protect-data.md
[issue060208]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/08-protect-data
[proactive10]: https://top10proactive.owasp.org/
