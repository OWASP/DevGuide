### 6.1.1 WSTG

The OWASP [Web Security Testing Guide][wstg] (WSTG) is a comprehensive guide to testing the security of
web applications and web services.

The WSTG [documentation project][wstg] is an OWASP Flagship Project
and can be accessed as a [web based document][wstg-latest].

#### What is WSTG?

The Web Security Testing Guide ([WSTG][wstg]) document is a comprehensive guide to testing the security
of web applications and web services.
The WSTG provides a framework of best practices commonly used by external penetration testers
and organizations conducting in-house testing.

The WSTG document describes a suggested [web application test framework][wstg-framework]
and also provides general information on [how to test][wstg-howto] web applications with good testing practice.

The tests are split out into domains:

1. Configuration and Deployment Management
2. Identity Management
3. Authentication
4. Authorization
5. Session Management
6. Input Validation
7. Error Handling
8. Weak Cryptography
9. Business Logic
10. Client-side
11. API

Each test in each domain has enough information to understand and run the test including:

* Summary
* Test objectives
* How to test
* Suggested remediation
* Recommended tools and references

The tests are identified with a unique reference number,
for example 'WSTG-APIT-01' refers to the first test in the 'API Testing' domain provided in the WSTG document.
These references are widely used and understood by the test and security communities.

The WSTG also provides a suggested Web Security Testing Framework which can be tailored
for a particular organization's processes or can provide a generally accepted reference framework.

#### Why use it?

The WSTG document is widely used and has become the defacto standard on
what is required for comprehensive web application testing.
An organization's security testing process should consider the contents of the WSTG, or have equivalents,
which help the organization conform to general expectation of the security community.
The WSTG reference document can be adopted completely, partially or not at all;
according to an organization's needs and requirements.

#### How to use it

The OWASP Spotlight series provides an overview of how to use the WSTG:
'Project 1 - [Applying OWASP Testing Guide][spotlight01]'.

The WSTG is accessed via the [online web document][wstg-latest].
The section on principles and techniques of testing provides foundational knowledge,
along with advice on testing within typical Secure Development Lifecycle (SDLC) and penetration testing methodologies.

The individual tests described in the various testing domains should be selected or discarded as necessary;
not every test will be relevant to every web application or organizational requirement,
and the tests should be tailored to provide at least the minimum test coverage while not expending too much test effort.

#### References

* OWASP [Web Security Testing Guide][wstg] (WSTG) project
* [WSTG downloads][wstg-latest]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue080101] or [edit on GitHub][edit080101].

[edit080101]: https://github.com/OWASP/DevGuide/blob/main/docs/06-verification/01-guides/01-wstg.md
[issue080101]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/01-guides/01-wstg
[spotlight01]: https://youtu.be/bxQPePVDbQk
[wstg]: https://owasp.org/www-project-web-security-testing-guide/
[wstg-framework]: https://owasp.org/www-project-web-security-testing-guide/latest/3-The_OWASP_Testing_Framework/0-The_Web_Security_Testing_Framework
[wstg-howto]: https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/
[wstg-latest]: https://owasp.org/www-project-web-security-testing-guide/stable/
