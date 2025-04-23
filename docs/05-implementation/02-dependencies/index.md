![Developer guide logo](../../assets/images/dg_logo_bbd.png "OWASP Developer Guide"){ align=right width=180 }

### 5.2 Dependencies

Management of software dependencies is described by the SAMM [Software Dependencies][sammisbsd] activity,
which in turn is part of the SAMM [Secure Build][sammisb] security practice
within the [Implementation][sammi] business function.

It is important to record all dependencies used throughout the application in a production environment.
This can be achieved by Software Composition Analysis (SCA) to identify the third party dependencies.

A Software Bill of Materials (SBOM) provides a record of the dependencies within the system / application,
and provides information on each dependency so that it can be tracked :

* Where it is used or referenced
* Version used
* License
* Source information and repository
* Support and maintenance status of the dependency

Having an SBOM provides the ability to quickly find out which applications are affected by a specific
[Common Vulnerability and Exposure][cve] (CVE), or what CVEs are present in a particular application.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing then [submit an issue][issue0720].

[cve]: https://cve.mitre.org/
[issue0720]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2005-implementation/02-dependencies/00-toc
[sammi]: https://owaspsamm.org/model/implementation/
[sammisb]: https://owaspsamm.org/model/implementation/secure-build/
[sammisbsd]: https://owaspsamm.org/model/implementation/secure-build/stream-b/
