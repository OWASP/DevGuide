![ESAPI logo](../../assets/images/logos/esapi.png "OWASP ESAPI"){: style="height:180px;float:right" }

### 5.3.1 ESAPI

The OWASP Enterprise Security API (ESAPI) [library][esapi-docs] is a security control library
for web applications written in Java.

The [ESAPI library][esapi-project] is an OWASP Lab project that is under active development
for [Java security controls][esapi-java] with regular releases.

#### What is the ESAPI library?

The OWASP Enterprise Security API (ESAPI) [library][esapi-docs] provides a set of security control interfaces
which define types of parameters that are passed to the security controls.

The ESAPI is an open source web application security control library
that makes it easier for Java programmers to write lower-risk applications.
The ESAPI Java library is designed to help programmers retrofit security into existing Java applications,
and the library also serves as a solid foundation for new development.

#### Why use it?

The use of the ESAPI Java library is not easy to justify, although its use should certainly be considered.
The engineering decisions a development team will need to make when using ESAPI are discussed in the
'[Should I use ESAPI?][esapi-question]' documentation.

For new projects or for modifying an existing project then alternatives should be strongly considered:

* Output encoding: OWASP [Java Encoder][java-encoder] project
* General HTML sanitization: OWASP [Java HTML Sanitizer][java-sanitizer]
* Validation: [JSR-303/JSR-349 Bean Validation][bean]
* Strong cryptography: Google [Tink][google-tink] or [Keyczar][google-keyczar]
* Authentication & authorization: [Apache Shiro][shiro], authentication using [Spring Security][spring]
* [CSRF][cscsrf] protection: OWASP [CSRFGuard][csrfguard] project

Consideration could be given for using ESAPI if multiple security controls provided by this library are used in a project,
it then may be useful to use the monolithic ESAPI library rather than multiple disparate class libraries.

#### How to use it

If the engineering decision is to use the ESAPI library then it can be downloaded as a Java Archive (.jar) package file.
There is a reference implementation for each security control.

#### References

* [ESAPI for Java][esapi-java]
* ESAPI [documentation][esapi-docs]
* ESAPI [project][esapi-project]
* OWASP [Java Encoder][java-encoder] project
* OWASP [Java HTML Sanitizer][java-sanitizer]
* [Spring Security][spring]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue070301] or [edit on GitHub][edit070301].

[bean]: http://beanvalidation.org/
[csrfguard]: https://owasp.org/www-project-csrfguard/
[cscsrf]: https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet
[edit070301]: https://github.com/OWASP/www-project-developer-guide/blob/main/draft/07-implementation/03-secure-libraries/01-esapi.md
[esapi-docs]: https://www.javadoc.io/doc/org.owasp.esapi/esapi/latest/index.html
[esapi-java]: https://mvnrepository.com/artifact/org.owasp.esapi/esapi
[esapi-project]: https://owasp.org/www-project-enterprise-security-api/
[esapi-question]: https://owasp.org/www-project-enterprise-security-api/#div-shouldiuseesapi
[google-keyczar]: https://github.com/google/keyczar
[google-tink]: https://github.com/google/tink
[issue070301]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2007-implementation/03-secure-libraries/01-esapi
[java-encoder]: https://owasp.org/www-project-java-encoder
[java-sanitizer]: https://owasp.org/www-project-java-html-sanitizer
[shiro]: https://shiro.apache.org/
[spring]: https://docs.spring.io/spring-security/reference/features/index.html
