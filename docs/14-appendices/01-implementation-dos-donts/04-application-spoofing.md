### 12.1.4 Application Spoofing

Here is a collection of Do's and Don'ts when it comes to application spoofing, gathered from practical experiences.
Some of these are language specific and others have more general applicability.

What is application spoofing:

* A threat actor including an application in a malicious iFrame
* A threat actor creating dependencies with similar names as legitimate ones (typo squatting)

How can it be addressed:

#### Application spoofing / clickjacking

Set `X-FRAME-OPTIONS` header to `SAMEORIGIN` or `DENY`, depending on what the business requirement is
for rendering the web page.
This will help prevent a malicious actor including your application in an iFrame to capture credentials/exfiltrate data.
As a caveat, this will not work with Meta Tags. X-FRAME-OPTIONS must be applied as HTTP Response Header

Use Content Security Policy:

Common uses of CSP frame-ancestors:

Content-Security-Policy: frame-ancestors 'none';

This prevents any domain from framing the content. This setting is recommended unless a specific need
has been identified for framing.

Content-Security-Policy: frame-ancestors 'self';

This only allows the current site to frame the content.

Content-Security-Policy: frame-ancestors 'self' `*.somesite.com https://myfriend.site.com;`

This allows the current site, as well as any page on `somesite.com` (using any protocol),
and only the page `myfriend.site.com`, using HTTPS only on the default port (443).

Use `SameSite` Cookies

Use `httpOnly` cookies

#### Domain squatting / typo squatting

What is domain squatting (also known as cybersquatting):

* A threat actor creating a malicious domain with the same spelling as a legitimate domain
    but use different UTF characters (domain squatting)
* A threat actor registering, trafficking in, or using an Internet domain name,
    with an intent to profit from the goodwill of a trademark belonging to someone else
* Though domain squatting impacts brand value directly, it has an impact from a security perspective
* It can result in the following kind of scenario: (also known as typosquatting)
    Wherein the domain with U+00ED may be a malicious application trying to harvest credentials
* Typo squatting is achieved with supply chain manipulation.

How can it be addressed:

* Use threat intelligence to monitor lookalikes for your domain
* In the event a dispute needs to be raised, it can be done with [URDP][urdp]
* Verify packages in registries before using them

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue140104] or [edit on GitHub][edit140104].

[edit140104]: https://github.com/OWASP/www-project-developer-guide/blob/main/draft/14-appendices/01-implementation-dos-donts/04-application-spoofing.md
[issue140104]: https://github.com/OWASP/www-project-developer-guide/issues/new?labels=enhancement&template=request.md&title=Update:%20/14-appendices/01-implementation-dos-donts/04-application-spoofing
[urdp]: https://www.icann.org/resources/pages/help/dndr/udrp-en
