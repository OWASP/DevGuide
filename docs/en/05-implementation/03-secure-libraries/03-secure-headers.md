![Secure Headers logo](../../../assets/images/logos/secure_headers.png "OWASP Secure Headers"){ align=right width=150 }

The OWASP Secure Headers Project ([OSHP][oshp]) provides information on HTTP response headers
to increase the security of a web application.

The OSHP documentation project is an OWASP Lab Project and raises awareness  of secure headers and their use.

#### What is OSHP?

The [OSHP project][oshp] provides explanations for the HTTP response headers that an application can use
to increase the security of the application.
Once set the HTTP response headers can restrict modern browsers from running into easily preventable vulnerabilities.

OSHP contains guidance and downloads on:

* Response headers explanations and usage
* Links to individual browser support
* Guidance and best practices
* Technical resources in the form of tools and documents
* Code snippets to help working with HTTP security headers

#### Why use it?

The OSHP is a documentation project that explains the reasoning and usage of HTTP response headers.
It is the go-to document for guidance and best practices;
the information on HTTP response headers is the best advice, in one location, and is kept up to date.

#### How to use it

The OWASP Spotlight series provides an overview of this project and its uses:
'Project 24 - [OWASP Security Headers Project][spotlight24]'.

OSHP provides links to development [libraries][oshp-libs] that provide for secure HTTP response headers
in a range of languages and frameworks: DotNet, Go, HAPI, Java, NodeJS, PHP, Python, Ruby, Rust.
The OSHP also lists [various tools][oshp-tools] useful for inspection, analysis and scanning of HTTP response headers.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue070303] or [edit on GitHub][edit070303].

[edit070303]: https://github.com/OWASP/DevGuide/blob/main/docs/en/05-implementation/03-secure-libraries/03-secure-headers.md
[issue070303]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/03-secure-libraries/03-secure-headers
[oshp]: https://owasp.org/www-project-secure-headers/
[oshp-libs]: https://owasp.org/www-project-secure-headers/#development-libraries
[oshp-tools]: https://owasp.org/www-project-secure-headers/#analysis-tools
[spotlight24]: https://youtu.be/N4F3VWQYU9E
