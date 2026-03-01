The OWASP [Java HTML Sanitizer][html-sanitizer-project] and OWASP [Java Encoder][java-encoder-project] projects
are security libraries for Java web applications that provide output encoding and HTML input sanitization.

The OWASP [JSON Sanitizer][json-sanitizer] Java library is used to ensure JSON input / output is standards compliant.

#### What are they?

Java Encoder
contextual output encoding as part of a defense in depth approach to preventing XSS

#### Why use the libraries?

The use of these libraries is widely used to protect against

and remain widely used to this day.

These are both established projects with a regular release history from 2026 back to 2013.

The OWASP [JSON Sanitizer][json-sanitizer] Java library is less well supported
but should be considered for JSON specific output sanitization; it is a direct dependency for literally 1000s of projects.

#### How to use the libraries

[via Maven][java-encoder]

#### References

* OWASP [Cross Site Scripting prevention][csxss] Cheatsheet
* OWASP [Java Encoder][java-encoder-github]
* OWASP [Java HTML Sanitizer][html-sanitizer]
* OWASP [JSON Sanitizer][json-sanitizer]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue050304] or [edit on GitHub][edit050304].

[csxss]: https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet
[edit050304]: https://github.com/OWASP/DevGuide/blob/main/docs/en/05-implementation/03-secure-libraries/04-java-secure-libs.md
[html-sanitizer]: https://github.com/OWASP/java-html-sanitizer/releases/latest/
[html-sanitizer-project]: https://owasp.org/www-project-java-html-sanitizer/
[issue050304]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/03-secure-libraries/04-java-secure-libs
[java-encoder]: http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22org.owasp.encoder%22
[java-encoder-github]: https://github.com/OWASP/owasp-java-encoder/releases/latest/
[java-encoder-project]: https://owasp.org/www-project-java-encoder/
[json-sanitizer]: https://github.com/OWASP/json-sanitizer/releases/latest/
