![Developer guide logo](../assets/images/dg_logo.png "OWASP Developer Guide"){: style="height:180px;float:right" }

## Requirements

Security requirements are statements of
security functionality that ensure the different security properties of a software application are being satisfied.
Security requirements are derived from industry standards, applicable laws, and a history of past vulnerabilities.
Security requirements define new features or additions to existing features to solve a specific security problem
or eliminate potential vulnerabilities.

Security requirements also provide a foundation of vetted security functionality for an application.
Instead of creating a custom approach to security for every application,
standard security requirements allow developers to reuse the definition of security controls and best practices;
those same vetted security requirements provide solutions for security issues that have occurred in the past.

The importance of understanding key security requirements is described in the [Security Requirements][sammdsr]
practice that is part of the [Design][sammd] business function section within the OWASP [SAMM model][samm].
Ideally structured software security requirements are available within with a security a requirements framework,
and these are utilized by both developer teams and product teams.
In addition suppliers to the organization must meet security requirements;
build security into supplier agreements in order to ensure compliance with organizational security requirements.

In summary, security requirements exist to prevent the repeat of past security failures.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing then [submit an issue][issue0500].

[issue0500]: https://github.com/OWASP/www-project-developer-guide/issues/new?labels=enhancement&template=request.md&title=Update:%2005-requirements/00-toc
[samm]: https://owaspsamm.org/about/
[sammd]: https://owaspsamm.org/model/design/
[sammdsr]: https://owaspsamm.org/model/design/security-requirements/
