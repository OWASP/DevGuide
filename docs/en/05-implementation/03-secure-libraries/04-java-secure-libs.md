The OWASP [Java Encoder][java-encoder-project] and OWASP [Java HTML Sanitizer][html-sanitizer-project] projects
are security libraries for Java web applications that provide output encoding and HTML input sanitization.

The OWASP [JSON Sanitizer][json-sanitizer] Java library is used to ensure both JSON input and output
are _reasonably_ safe for Java applications.

#### What are they?

Java Encoder package provides the Java application with contextual output encoding of HTML.
It provides individual methods for HTML, URLs, JavaScript and CSS.

Java HTML Sanitizer is used to sanitize untrusted HTML so that it can be safely handled within a Java application.
The JAR file is included in a Java application and then a policy is defined for it.

These are both established projects with a regular release history stretching back to 2013.

The JSON Sanitizer is a Java component that will transform arbitrary JSON
to well-formed JSON as defined by [RFC 4627][rfc4627].
This can be used to accept JSON input from an untrusted source and then safely output JSON to other processes.

JSON Sanitizer is a widely used library provided by OWASP,
and it is a direct dependents for many 1000s of other libraries and in many more applications.
It is a project that was transferred to OWASP in 2021 by github user `mikesamuel`
and so this OWASP library is identified as `com.mikesamuel:json-sanitizer`.

#### Why use the libraries?

The use of both Java Encoder and Java HTML Sanitizer is part of a defense in depth approach
to preventing [cross site scripting][csxss] (XSS) and other attacks.
They are well established OWASP projects with 'Lab' status.

The OWASP [JSON Sanitizer][json-sanitizer] Java library is widely used,
for example it is a direct dependency for literally [1000s of Java components][json-sanitizer-dependents],
and should be considered for JSON specific output normalization and input validation.
It is less well supported than the Java Encoder or Java HTML Sanitizer, version 1.2.2 was released in January 2021,
but it is still stable and (really) useful.

#### How to use the libraries

Include the Java Encoder package into a Java application [via Maven][java-encoder].
The '[How to Use the OWASP Java Encoder][java-encoder-usage]' documentation explains how to use it in various contexts,
such as HTML, URLs, JavaScript and CSS.

Follow the [examples][html-sanitizer-examples] provided by Java HTML Sanitizer
to include the utility and configure it with policy.

The JSON Sanitizer JAR file can be fetched from Maven Central, follow the [Getting Started][json-sanitizer-usage] guide:

```text
import com.google.json.JsonSanitizer;
String wellFormedJson = JsonSanitizer.sanitize(myJsonLikeString);
```

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
[html-sanitizer-examples]: https://github.com/OWASP/java-html-sanitizer/tree/main/owasp-java-html-sanitizer/src/main/java/org/owasp/html/examples
[html-sanitizer-project]: https://owasp.org/www-project-java-html-sanitizer/
[issue050304]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/03-secure-libraries/04-java-secure-libs
[java-encoder]: http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22org.owasp.encoder%22
[java-encoder-github]: https://github.com/OWASP/owasp-java-encoder/releases/latest/
[java-encoder-project]: https://owasp.org/www-project-java-encoder/
[java-encoder-usage]: https://owasp.org/www-project-java-encoder/#div-use
[json-sanitizer]: https://github.com/OWASP/json-sanitizer/releases/latest/
[json-sanitizer-dependents]: https://central.sonatype.com/artifact/com.mikesamuel/json-sanitizer/dependents
[json-sanitizer-usage]: https://github.com/OWASP/json-sanitizer/blob/master/docs/getting_started.md
[rfc4627]: https://www.rfc-editor.org/rfc/rfc4627.txt
