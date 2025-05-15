![SKF logo](../../assets/images/logos/skf.png "OWASP SKF"){ align=right width=180 }

The [Security Knowledge Framework][skf] (SKF) is a system that uses draws on the material in various
open source projects to support development teams and security architects in building secure applications.

Having been an OWASP flagship project for many years the SKF is now no longer within the OWASP organization;
and it will continue to be referenced in the OWASP Wayfinder and other OWASP projects
because it is a flagship project for any organization.

#### What is the Security Knowledge Framework?

The [SKF][skf] is a web application that provides context and training
to help security architects identity security requirements.
As their website puts it: "Training and guidance for doing AppSec right!"

Note that SKF is in a process of migrating to a [new repository][skfrepo] so the download links may change.

The SKF provides guidance for application security in several areas:

* Requirements [organizer][skfreqs]
* Learning [courses][skfdemo]:
  * Developing Secure Software (LFD121)
  * Understanding the OWASP Top 10 Security Threats (SKF100)
  * Secure Software Development: Implementation (LFD105x)
* Practice [labs][skflabs]
* Documentation on [installing and using][skfdocs] the SKF

The SKF builds on the OWASP [Application Security Verification Standard][asvs] (ASVS)
to help developers in both pre-development and post-development phases and create applications that are secure by design.

#### Why use the SKF for requirements?

The SKF organizes security requirements into various categories that provides a good starting point for application security.

* API and Web Service
* Access Control
* Architecture Design and Threat Modeling
* Authentication
* Business Logic
* Communication
* Configuration
* Data Protection
* Error Handling and Logging
* Files and Resources
* Malicious Code
* Session Management
* Stored Cryptography
* Validation Sanitization and Encoding

#### How to use the SKF for requirements

There is [a demo version][skfdemo] of SKF that is useful for exploring the multiple perspectives of the SKF.

Follow the documentation on [installing and using][skfdocs] the SKF.

Visit the [requirements tool website][skfreqs] and select the relevant requirements from the various categories.
Export the selection to the format of your choice (Markdown, spreadsheet CSV or plain text)
and use this as a starting point for the application security requirements.

The OWASP Spotlight series provides an overview of the SKF: 'Project 7 - [Security Knowledge Framework (SKF)][spotlight07]'.

#### References

* [Security Knowledge Framework][skf] (SKF)
* [SKF courses and labs][skfdemo]
* [SKF requirements][skfreqs]
* OWASP [Application Security Verification Standard][asvs] (ASVS)

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0507] or [edit on GitHub][edit0507].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[edit0507]: https://github.com/OWASP/DevGuide/blob/main/docs/03-requirements/07-skf.md
[issue0507]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2003-requirements/07-skf
[skf]: https://www.securityknowledgeframework.org/
[skfdemo]: https://secureby.design/
[skfdocs]: https://skf.readme.io/docs/introduction
[skflabs]: https://secureby.design/labs
[skfrepo]: https://github.com/Security-Knowledge-Framework
[skfreqs]: https://github.com/Security-Knowledge-Framework/SKF-requirements-tool
[spotlight07]: https://youtu.be/TFX_ZBy6lNY
