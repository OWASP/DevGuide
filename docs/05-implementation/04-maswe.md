![MAS checklist logo](../assets/images/logos/mas.png "OWASP MASWE"){ align=right width=180 }

### 5.4 MASWE

The OWASP [Mobile Application Security][masproject] (MAS) flagship project provides
industry standards for mobile application security.

The OWASP [MASWE][maswe] project is one of the tools provided by MAS,
and provides a list of weaknesses that have been found in various mobile applications.

#### What is the MASWE?

The MAS [Weakness Enumeration][maswe] lists weaknesses, and therefore potential vulnerabilities,
that have been found in various mobile applications over time.

The MASWE is split out into weakness categories that correspond to the [MASVS][masvs] verification categories:

* [MASVS-STORAGE](https://mas.owasp.org/MASWE/MASVS-STORAGE/MASWE-0001/) sensitive data storage
* [MASVS-CRYPTO](https://mas.owasp.org/MASWE/MASVS-CRYPTO/MASWE-0009/) cryptography best practices
* [MASVS-AUTH](https://mas.owasp.org/MASWE/MASVS-AUTH/MASWE-0028/) authentication and authorization mechanisms
* [MASVS-NETWORK](https://mas.owasp.org/MASWE/MASVS-NETWORK/MASWE-0047/) network communications
* [MASVS-PLATFORM](https://mas.owasp.org/MASWE/MASVS-PLATFORM/MASWE-0053/) interactions with the mobile platform
* [MASVS-CODE](https://mas.owasp.org/MASWE/MASVS-CODE/MASWE-0075/) platform and third-party software
* [MASVS-RESILIENCE](https://mas.owasp.org/MASWE/MASVS-RESILIENCE/MASWE-0089/) integrity and running on a trusted platform
* [MASVS-PRIVACY](https://mas.owasp.org/MASWE/MASVS-PRIVACY/MASWE-0108/) privacy of users, data and resources

#### Why use it?

Although the MASWE is a relatively new project from 2024, it already provides a common language
when discussing and categorizing weaknesses found in mobile applications.
It also provides a list of potential vulnerabilities that should be considered during the design lifecycle
and when creating or revising security requirements for mobile applications.

The MASWE is a valuable list of what can go wrong with mobile applications along with the activities of malicious actors.

#### How to use it

The Common Weakness Enumeration ([CWE][cwe]), published by MITRE, can be used by security architects
so they are aware of what weaknesses and potential vulnerabilities that could be present in an application.
Development teams can use the CWE as a reference to these weaknesses and to help understanding of any mitigations.
These are just two examples of how the CWE is widely used.

In a similar way the MASWE can be used in the development of mobile applications :

* inform development teams of specific weaknesses
* identification of security requirements
* used as a training aid
* provide categorization of weaknesses

This list is just a starting point; there are many uses for the MASWE.

#### References

* Mobile Application Security ([MAS][masproject]) project
* MAS Weakness Enumeration ([MASWE][maswe])
* MITRE Common Weakness Enumeration ([CWE][cwe])
* MAS Verification Standard ([MASVS][masvs])
* MAS [Checklist][masc]
* MAS Testing Guide ([MASTG][mastg])

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0704] or [edit on GitHub][edit0704].

[cwe]: https://cwe.mitre.org/
[edit0704]: https://github.com/OWASP/DevGuide/blob/main/docs/05-implementation/04-maswe.md
[issue0704]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2005-implementation/04-maswe
[masproject]: https://owasp.org/www-project-mobile-app-security/
[masc]: https://mas.owasp.org/checklists/
[mastg]: https://mas.owasp.org/MASTG/
[maswe]: https://mas.owasp.org/MASWE/
[masvs]: https://mas.owasp.org/MASVS/
