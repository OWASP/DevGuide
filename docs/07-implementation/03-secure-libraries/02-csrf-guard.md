### 5.3.2 CSRFGuard

OWASP [CSRFGuard][csrfguard] is a security control that helps protect Java applications
against [Cross-Site Request Forgery][cscsrf] (CSRF) attacks.

The CSRFGuard Builder/Breaker Tool project is an OWASP Production Project
and is being actively maintained by a pool of international volunteers.

#### What is CSRFGuard?

OWASP [CSRFGuard][csrfguard] is a library that implements a variant of the synchronizer token pattern to mitigate
the risk of Cross-Site Request Forgery (CSRF) attacks for Java applications.

The OWASP CSRFGuard library is integrated through the use of a JavaEE Filter and exposes various automated
and manual ways to integrate per-session or pseudo-per-request tokens into HTML.
When a user interacts with this HTML, CSRF prevention tokens are submitted with the corresponding HTTP request.
CSRFGuard ensures the token is present and is valid for the current HTTP request.

#### Why use it?

The OWASP CSRFGuard library is widely used for Java applications, and will help mitigate against CSRF.

#### How to use it

Pre-compiled versions of the CSRFGuard library can be downloaded from
the [Maven Central repository][csrfguard-maven] or the [OSS Sonatype Nexus][csrfguard-nexus] repository.

Follow the [instructions][csrfguard-build] to build CSRFGuard into the Java application using Maven.

#### References

* OWASP [CSRFGuard][csrfguard]
* OWASP [Cross-Site Request Forgery Prevention Cheat Sheet][cscsrf]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue070302] or [edit on GitHub][edit070302].

[csrfguard]: https://owasp.org/www-project-csrfguard/
[csrfguard-build]: https://github.com/OWASP/www-project-csrfguard/blob/master/readme.md#using-with-maven
[csrfguard-nexus]: https://oss.sonatype.org/#nexus-search;gav~~csrfguard~~~
[csrfguard-maven]: https://central.sonatype.com/search?q=csrfguard&smo=true
[cscsrf]: https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet
[edit070302]: https://github.com/OWASP/DevGuide/blob/main/docs/07-implementation/03-secure-libraries/02-csrf-guard.md
[issue070302]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2007-implementation/03-secure-libraries/02-csrf-guard
