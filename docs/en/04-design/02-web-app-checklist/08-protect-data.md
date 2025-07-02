Sensitive data such as passwords, credit card numbers, health records, personal information and business secrets
require extra protection, particularly if that data falls under privacy laws (EU General Data Protection Regulation GDPR),
financial data protection rules such as PCI Data Security Standard (PCI DSS) or other regulations.

Refer to proactive control [C2: Use Cryptography the proper way][control2] and its [cheatsheets][csproactive-c8]
for more context from the OWASP Top 10 Proactive Controls project,
and use the list below as suggestions for a checklist that has been tailored for the individual project.

#### 1. Data protection

1. Classify data according to the level of sensitivity
2. Implement appropriate access controls for sensitive data
3. Encrypt data in transit
4. Ensure secure communication channels are properly configured
5. Avoid storing sensitive data when at all possible
6. Ensure sensitive data at rest is cryptographically protected to avoid unauthorized disclosure and modification
7. Purge sensitive data when that data is no longer required
8. Store application-level secrets in a secrets vault
9. Check that secrets are not stored in code, config files or environment variables
10. Implement least privilege, restricting access to functionality, data and system information
11. Protect all cached or temporary copies of sensitive data from unauthorized access
12. Purge those temporary copies of sensitive data as soon as they are no longer required
13. Do not include sensitive information in the URL or query string, such as an API key or session token
14. Disable client side caching on pages containing sensitive information (e.g. Cache-Control: no-store)

#### 2. Memory management

1. Explicitly initialize all variables and data stores
2. Check that any buffers are as large as specified
3. Check buffer boundaries if calling the function in a loop and protect against overflow
4. Specifically close resources, don't rely on garbage collection
5. Use non-executable stacks when available
6. Properly free allocated memory upon the completion of functions and at all exit points
7. Overwrite any sensitive information stored in allocated memory at all exit points from the function
8. Protect shared variables and resources from inappropriate concurrent access

#### References

* OWASP [Cheat Sheet: Cryptographic Storage][cscs]
* OWASP [Cheat Sheet: Secrets Management][cssm]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060208] or [edit on GitHub][edit060208].

[csproactive-c8]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c8-protect-data-everywhere
[control2]: https://top10proactive.owasp.org/the-top-10/c2-crypto/
[cscs]: https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet
[cssm]: https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet
[edit060208]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/02-web-app-checklist/08-protect-data.md
[issue060208]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/08-protect-data
[proactive10]: https://top10proactive.owasp.org/
