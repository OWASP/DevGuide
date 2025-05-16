![MAS logo](../../assets/images/logos/mas.png "OWASP MAS"){ align=right width=180 }

The OWASP [Mobile Application Security][masproject] (MAS) flagship project provides
industry standards for mobile application security.

The MAS project covers the processes, techniques, and tools used for security testing mobile applications.
It provides a set of test cases that enables testers to deliver consistent and complete results.
The OWASP MAS project provides both the [Mobile Application Security Verification Standard][masvs] (MASVS)
for mobile applications and the [Mobile Application Security Testing Guide][mastg] (MASTG).

#### What is MASVS?

The [OWASP MASVS][mas] is used by mobile software architects and developers to develop secure mobile applications,
as well as security testers to ensure completeness and consistency of test results.
The MAS project has several uses; when it comes to defining requirements then
the MASVS contains a list of security controls for mobile applications.

The security controls are split into several categories:

* [MASVS-STORAGE](https://mas.owasp.org/MASVS/05-MASVS-STORAGE/) / [Cheat Sheets][masvs-storage]
* [MASVS-CRYPTO](https://mas.owasp.org/MASVS/06-MASVS-CRYPTO/) / [Cheat Sheets][masvs-crypto]
* [MASVS-AUTH](https://mas.owasp.org/MASVS/07-MASVS-AUTH/) / [Cheat Sheets][masvs-auth]
* [MASVS-NETWORK](https://mas.owasp.org/MASVS/08-MASVS-NETWORK/) / [Cheat Sheets][masvs-network]
* [MASVS-PLATFORM](https://mas.owasp.org/MASVS/09-MASVS-PLATFORM/) / [Cheat Sheets][masvs-platform]
* [MASVS-CODE](https://mas.owasp.org/MASVS/10-MASVS-CODE/) / [Cheat Sheets][masvs-code]
* [MASVS-RESILIENCE](https://mas.owasp.org/MASVS/11-MASVS-RESILIENCE/) / [Cheat Sheets][masvs-resilience]
* [MASVS-PRIVACY](https://mas.owasp.org/MASVS/12-MASVS-PRIVACY/) / [Cheat Sheets][masvs-privacy]

The last category, MASVS-PRIVACY, is being reworked so is subject to change.

#### Why use MASVS?

The OWASP MASVS is the industry standard for [mobile application security][csmas]
and it is expected that any given set of security requirements will satisfy the MASVS.
When defining security requirements for mobile applications then each security control in the MASVS should be considered.

#### How to use MASVS

MASVS can be [accessed online][masvs] and the links followed for each security control.
In addition MASVS can be downloaded as a PDF which can, for example, be used for evidence or compliance purposes.
Inspect each control within MASVS and regard it as a potential security requirement.

The OWASP Cheat Sheets have been indexed specifically for [each category of the MASVS][csmasvs],
which can be used as a guide to decide if the category should to be included in the test scheme.

#### References

* OWASP [Mobile Application Security][mas] (MAS)
* MAS [project][masproject]
* MAS [Checklist][masc]
* MAS [Verification Standard][masvs] (MASVS)
* OWASP [Mobile Application Security][csmas] cheat sheet

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0506] or [edit on GitHub][edit0506].

[csmas]: https://cheatsheetseries.owasp.org/cheatsheets/Mobile_Application_Security_Cheat_Sheet
[csmasvs]: https://cheatsheetseries.owasp.org/IndexMASVS
[edit0506]: https://github.com/OWASP/DevGuide/blob/main/docs/en/03-requirements/06-mas.md
[issue0506]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2003-requirements/06-mas
[mas]: https://mas.owasp.org/
[masc]: https://mas.owasp.org/checklists/
[masproject]: https://owasp.org/www-project-mobile-app-security/
[mastg]: https://mas.owasp.org/MASTG/
[masvs]: https://mas.owasp.org/MASVS/
[masvs-storage]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-storage
[masvs-crypto]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-crypto
[masvs-auth]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-auth
[masvs-network]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-network
[masvs-platform]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-platform
[masvs-code]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-code
[masvs-resilience]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-resilience
[masvs-privacy]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-privacy
