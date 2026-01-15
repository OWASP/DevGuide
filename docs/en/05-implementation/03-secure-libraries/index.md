![Developer guide logo](../../../assets/images/dg_logo_bbd.png "OWASP Developer Guide"){ align=right width=180 }

The use of secure libraries is part of the technology management that helps to fulfill security requirements.
Standard libraries enable the adoption of common design patterns and security solutions,
and provide standardized technologies and frameworks that can be used throughout different applications.

[Technology Management][sammdsatm] for the software applications is described by SAMM as an activity
within the SAMM [Security Architecture][sammdsa] security practice
which in turn is part of the [Design][sammd] business function.

----

## Additional Secure Libraries

### Java Encoder
Java Encoder is an OWASP library that helps prevent cross-site scripting (XSS)
by safely encoding untrusted data before it is included in application output.

It should be used whenever user-controlled input is rendered in HTML,
JavaScript, URLs, or other browser-facing contexts.

See the OWASP Java Encoder project for details [javaencoder].

### Java HTML Sanitizer
Java HTML Sanitizer is an OWASP library designed to clean untrusted HTML content
by allowing only safe elements and attributes.

It is useful when applications need to accept HTML input from users while
reducing the risk of XSS vulnerabilities.

See the OWASP Java HTML Sanitizer project for details [htmlsanitizer].

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0703] or [edit on GitHub][edit0703].

[edit0703]: https://github.com/OWASP/DevGuide/blob/main/docs/en/05-implementation/03-secure-libraries/index.md
[issue0703]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/03-secure-libraries/index
[sammd]: https://owaspsamm.org/model/design/
[sammdsa]: https://owaspsamm.org/model/design/secure-architecture/
[sammdsatm]: https://owaspsamm.org/model/design/secure-architecture/stream-b/
[javaencoder]: https://owasp.org/www-project-java-encoder/
[htmlsanitizer]: https://owasp.org/www-project-java-html-sanitizer/
