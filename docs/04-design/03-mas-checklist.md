![MAS checklist logo](../assets/images/logos/mas.png "OWASP MAS checklist"){ align=right height=180 }

### 4.3 MAS checklist

The OWASP [Mobile Application Security][masproject] (MAS) flagship project provides
industry standards for mobile application security.

The OWASP MAS project provides the [Mobile Application Security Verification Standard][masvs] (MASVS)
for mobile applications and a comprehensive [Mobile Application Security Testing Guide][mastg] (MASTG).

The [Mobile Application Security Checklist][masc] contains links to the MASTG test cases for each MASVS control.

#### What is MAS Checklist?

The MAS Checklist provides a checklist that keeps track of the MASTG test cases for a given MASVS control.
This MAS Checklist is split out into categories that match the MASVS categories:

* [MASVS-STORAGE](https://mas.owasp.org/checklists/MASVS-STORAGE/) sensitive data storage
* [MASVS-CRYPTO](https://mas.owasp.org/checklists/MASVS-CRYPTO/) cryptography best practices
* [MASVS-AUTH](https://mas.owasp.org/checklists/MASVS-AUTH/) authentication and authorization mechanisms
* [MASVS-NETWORK](https://mas.owasp.org/checklists/MASVS-NETWORK/) network communications
* [MASVS-PLATFORM](https://mas.owasp.org/checklists/MASVS-PLATFORM/) interactions with the mobile platform
* [MASVS-CODE](https://mas.owasp.org/checklists/MASVS-CODE/) platform and data entry points along with third-party software
* [MASVS-RESILIENCE](https://mas.owasp.org/checklists/MASVS-RESILIENCE/) integrity and running on a trusted platform
* [MASVS-PRIVACY](https://mas.owasp.org/checklists/MASVS-PRIVACY/) privacy of users, data and resources

In addition to the web links there is a [downloadable spreadsheet][masxls].

#### Why use it?

The OWASP MASVS is the industry standard for [mobile application security][csmas].
If the MASTG is being applied to a mobile application then the MAS Checklist is a handy reference
that can also be used for compliance purposes.

#### How to use it

The [online version][masc] is useful to list the MASVS controls and which MASTG tests apply.
Follow the links to access the individual controls and tests.

The [spreadsheet download][masxls] allows the status of each test to be recorded,
with a separate sheet for each MASVS category.
This record of test results can be used as evidence for compliance purposes.

#### References

* Mobile Application Security ([MAS][masproject]) project
* MAS [Checklist][masc]
* MAS Verification Standard ([MASVS][masvs])
* MAS Testing Guide ([MASTG][mastg])
* OWASP [Mobile Application Security][csmas] cheat sheet

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0603] or [edit on GitHub][edit0603].

[csmas]: https://cheatsheetseries.owasp.org/cheatsheets/Mobile_Application_Security_Cheat_Sheet
[edit0603]: https://github.com/OWASP/DevGuide/blob/main/docs/04-design/03-mas-checklist.md
[issue0603]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/03-mas-checklist
[masproject]: https://owasp.org/www-project-mobile-app-security/
[masxls]: https://github.com/OWASP/owasp-mastg/releases/latest/download/OWASP_MAS_Checklist.xlsx
[masc]: https://mas.owasp.org/checklists/
[mastg]: https://mas.owasp.org/MASTG/
[masvs]: https://mas.owasp.org/MASVS/
