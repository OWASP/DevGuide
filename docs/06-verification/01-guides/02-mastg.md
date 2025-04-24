![MAS logo](../../assets/images/logos/mas.png "OWASP MAS"){ align=right width=180 }

The [MAS Verification Standard][masvs] (MASVS) explains the processes, techniques
and tools used for security testing a mobile application.

The OWASP [MAS][mas] project provides the [Mobile Application Security Testing Guide][mastg] (MASTG)
which describes technical processes that can be used for verification of the mobile application controls .

#### What is MASTG?

The OWASP [Mobile Application Security Testing Guide][mastg] is a comprehensive manual
for mobile application security testing and reverse engineering.
It describes the technical processes used for verifying the controls listed in the OWASP MASVS.

The MASTG provides several resources for testing the controls:

* Sections detailing the concepts and theory behind testing of both Android and iOS platforms
* Lists of [tests][mastgtests] for each section of the [MASVS][masvs]
* Descriptions of [techniques][mastgtechs] for Android or iOS used during testing
* Lists of generic [tools][mastgtools] and also ones specific for Android or iOS
* Reference [applications][mastgapps] that can be used as training material

#### Why use MASTG?

The OWASP MASVS is the industry standard for [mobile application security][csmas],
and provides a list of security controls that are expected in a mobile application.
If the application does not implement these controls correctly then it could be vulnerable;
the MASTG tests that the application has the controls listed in the MASVS.

#### How to use MASTG

The OWASP Spotlight series provides an overview of using the MASTG:
'Project 13 - [OWASP Mobile Security Testing Guide (MSTG)][spotlight13]'.

The MASTG project contains a large number of resources that can be used during verification
and testing of mobile applications; pick and choose the resources that are applicable to specific application.

* Refer to the MASTG section on the concepts and theory to ensure good understanding of the testing process
* Select the [MASTG tests][mastgtests] that are applicable to the application and its platform OS
* Use the section on [MASTG techniques][mastgtechs] to run the selected tests correctly
* Become familiar with the range of [MASTG tools][mastgtools] available and select the ones that you need
* Use the [MAS Checklists][masc] to provide evidence of compliance

#### References

* OWASP [Mobile Application Security][masproject] (MAS) project
* OWASP [MAS Testing Guide][mastg] (MASTG)
* OWASP [MAS Checklists][masc]
* OWASP [MAS Verification Standard][masvs] (MASVS)
* OWASP [Mobile Application Security][csmas] cheat sheet

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue080102] or [edit on GitHub][edit080102].

[csmas]: https://cheatsheetseries.owasp.org/cheatsheets/Mobile_Application_Security_Cheat_Sheet
[edit080102]: https://github.com/OWASP/DevGuide/blob/main/docs/06-verification/01-guides/02-mastg.md
[issue080102]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2006-verification/01-guides/02-mastg
[mas]: https://mas.owasp.org/
[masproject]: https://owasp.org/www-project-mobile-app-security/
[masc]: https://mas.owasp.org/checklists/
[mastg]: https://mas.owasp.org/MASTG/
[mastgapps]: https://mas.owasp.org/MASTG/apps/
[mastgtests]: https://mas.owasp.org/MASTG/tests/
[mastgtechs]: https://mas.owasp.org/MASTG/techniques/
[mastgtools]: https://mas.owasp.org/MASTG/tools/
[masvs]: https://mas.owasp.org/MASVS/
[spotlight13]: https://youtu.be/b07OQd5KSrs
