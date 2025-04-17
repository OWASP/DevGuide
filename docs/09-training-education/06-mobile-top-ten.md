### 7.6 Mobile Top 10

The OWASP [Mobile Top 10][mobile10] is a list of the most prevalent vulnerabilities found in mobile applications.
In addition to the list of risks it also includes a list of security controls used to counter these vulnerabilities.

This documentation project is an OWASP Lab project, aimed at security builders and defenders.

#### What is the Mobile Top 10?

The Mobile Top 10 identifies and lists the [top ten vulnerabilities][mobile10-2023] found in mobile applications.
These risks of application vulnerabilities have been determined by the project team from various sources
including incident reports, vulnerability databases, and security assessments.
The list has been built using a data-based approach from unbiased sources,
an approach detailed in the [repository][mobile10repo] read-me.

* M1: [Improper Credential Usage][m01]
* M2: [Inadequate Supply Chain Security][m02]
* M3: [Insecure Authentication/Authorization][m03]
* M4: [Insufficient Input/Output Validation][m04]
* M5: [Insecure Communication][m05]
* M6: [Inadequate Privacy Controls][m06]
* M7: [Insufficient Binary Protections][m07]
* M8: [Security Misconfiguration][m08]
* M9: [Insecure Data Storage][m09]
* M10: [Insufficient Cryptography][m10]

The project also provides a comprehensive list of [security controls and techniques][mobile10controls]
that should be applied to mobile applications to provide a minimum level of security:

1. Identify and protect sensitive data on the mobile device
2. Handle password credentials securely on the device
3. Ensure sensitive data is protected in transit
4. Implement user authentication,authorization and session management correctly
5. Keep the backend APIs (services) and the platform (server) secure
6. Secure data integration with third party services and applications
7. Pay specific attention to the collection and storage of consent for the collection and use of the user’s data
8. Implement controls to prevent unauthorized access to paid-for resources (wallet, SMS, phone calls etc)
9. Ensure secure distribution/provisioning of mobile applications
10. Carefully check any runtime interpretation of code for errors

The list of mobile controls has been created and maintained by a collaboration of OWASP
and the [European Network and Information Security Agency][enisa] (ENISA) to build a joint set of controls.

#### Why use it?

It is important to have awareness of the types of attack mobile applications are exposed to,
and the types of vulnerabilities that may be present in any given mobile application.

The Mobile Top 10 provides a starting point for this training and education,
and it should be noted that the risks to mobile applications do not stop at the Top 10;
this list is only the more important ones and in practice there are many more risks.

In addition the Mobile Top 10 provides a list of controls that should be considered for mobile applications;
ideally at the requirements stage of the development cycle (the sooner the better)
but they can be applied at any time during development.

#### Mobile Top 10 versions

The Mobile Top 10 was [first released in 2014][mobile10-2014], [updated in 2016][mobile10-2016]
with the latest version [released in 2024][mobile10-2023].

The list of mobile application [controls][mobile10controls] were originally published in 2011 by [ENISA][enisa]
as the 'Smartphone Secure Development Guideline'.
This was then revised during 2016, released in February 2017, to inform the latest set of mobile application controls.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0906] or [edit on GitHub][edit0906].

[edit0906]: https://github.com/OWASP/www-project-developer-guide/blob/main/draft/09-training-education/06-mobile-top-ten.md
[enisa]: https://www.enisa.europa.eu/
[issue0906]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2009-training-education/06-mobile-top-ten
[m01]: https://owasp.org/www-project-mobile-top-10/2023-risks/m1-improper-credential-usage.html
[m02]: https://owasp.org/www-project-mobile-top-10/2023-risks/m2-inadequate-supply-chain-security.html
[m03]: https://owasp.org/www-project-mobile-top-10/2023-risks/m3-insecure-authentication-authorization.html
[m04]: https://owasp.org/www-project-mobile-top-10/2023-risks/m4-insufficient-input-output-validation.html
[m05]: https://owasp.org/www-project-mobile-top-10/2023-risks/m5-insecure-communication.html
[m06]: https://owasp.org/www-project-mobile-top-10/2023-risks/m6-inadequate-privacy-controls.html
[m07]: https://owasp.org/www-project-mobile-top-10/2023-risks/m7-insufficient-binary-protection.html
[m08]: https://owasp.org/www-project-mobile-top-10/2023-risks/m8-security-misconfiguration.html
[m09]: https://owasp.org/www-project-mobile-top-10/2023-risks/m9-insecure-data-storage.html
[m10]: https://owasp.org/www-project-mobile-top-10/2023-risks/m10-insufficient-cryptography.html
[mobile10]: https://owasp.org/www-project-mobile-top-10/
[mobile10-2014]: https://owasp.org/www-project-mobile-top-10/2014-risks/
[mobile10-2016]: https://owasp.org/www-project-mobile-top-10/2016-risks/
[mobile10-2023]: https://owasp.org/www-project-mobile-top-10/2023-risks/
[mobile10controls]: https://owasp.org/www-project-mobile-top-10/#div-controls
[mobile10repo]: https://github.com/OWASP/www-project-mobile-top-10/blob/master/README.md
