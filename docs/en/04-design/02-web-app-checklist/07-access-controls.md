Access Control or [Authorization][csauthz] is the process of granting or denying specific requests
from a user, program, or process.

Refer to proactive control [C1: Implement Access Controls][control1] and its [cheatsheets][csproactive-c7]
for more context from the OWASP Top 10 Proactive Controls project,
and use the list below as suggestions for a checklist that has been tailored for the individual project.

#### 1. Access control (AC)

1. Design access control / authorization thoroughly up-front
2. Force all requests to go through access control checks unless public
3. Deny by default; if a request is not specifically allowed then it is denied
4. Apply least privilege, providing the least access as is necessary
5. Log all authorization events
6. Create unit and integration test to document and verify an application's business rules, data types and access
   authorization criteria and/or processes so that access can be properly provisioned and controlled for restricting
   function-level, data-specific, and field-level access based on consumer permissions and resource attributes
7. Access Control criteria and/or processes not testable through automated tests should be documented so that they
   can be manually tested
8. Use only trusted system objects for making access authorization decisions
9. Use a single site-wide component to check authorization
10. Access control should fail securely
11. Deny all access if the application cannot access its security configuration information
12. Segregate privileged logic from other application code
13. Do not hard code access controls that are role based
14. Enforce application logic flows to comply with business rules
15. Server side implementation and presentation layer representations of access control rules should not differ in such a way
    that they allow for business functionality and rules to be compromised

#### 2. Access control management (ACM)

1. Limit the number of transactions a single user or device can perform in a given period of time,
    low enough to deter automated attacks but above the actual business requirement
2. Implement account auditing and enforce the disabling of unused accounts
3. A new account should have minimal or no access by default
4. For highly sensitive accounts implement Just in Time (JIT), Just Enough Access (JEA) management and avoid the use
    of admin accounts with global access
5. Restrict function-level access to consumers with explicit permissions
6. Restrict direct object references to only authorized users with explicit permissions to specific data items  
    to mitigate insecure direct object reference (IDOR) and broken object level authorization (BOLA)
7. Restrict access to user and data attributes to consumers with explicit permissions to specific fields to mitigate broken
    object property level authorization (BOPLA)
8. Restrict access security-relevant configuration information to only authorized users who have been allowed access through
    multiple layers of security, including continuous consumer identity verification, device security posture assessment, and
    contextual risk analysis
9. If the application must run with elevated privileges, raise privileges as late as possible, and drop as soon as possible

#### References

* OWASP [Cheat Sheet: Authorization][csauthz]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060207] or [edit on GitHub][edit060207].

[csproactive-c7]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c7-enforce-access-controls
[control1]: https://top10proactive.owasp.org/the-top-10/c1-accesscontrol/
[csauthz]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet
[edit060207]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/02-web-app-checklist/07-access-controls.md
[issue060207]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/07-access-controls
[proactive10]: https://top10proactive.owasp.org/
