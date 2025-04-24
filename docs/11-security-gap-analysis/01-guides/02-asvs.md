The [Application Security Verification Standard][asvs] (ASVS) is a long established OWASP flagship project,
and is widely used to identify gaps in security as well as the verification of web applications.

It can be downloaded from the [OWASP project page][asvs] in various languages and formats:
PDF, Word, CSV, XML and JSON. Having said that, the recommended way to consume the ASVS is to access
the [github markdown][asvsmd] pages directly - this will ensure that the latest version is used.

#### What is ASVS?

The ASVS is an open standard that sets out the coverage and 'level of rigor' expected when it comes to
performing web application security verification.
For this reason it can be used to identify gaps in the security of web applications.

The ASVS is split into various sections:

* V1 [Architecture, Design and Threat Modeling][asvsV1]
* V2 [Authentication][asvsV2]
* V3 [Session Management][asvsV3]
* V4 [Access Control][asvsV4]
* V5 [Validation, Sanitization and Encoding][asvsV5]
* V6 [Stored Cryptography][asvsV6]
* V7 [Error Handling and Logging][asvsV7]
* V8 [Data Protection][asvsV8]
* V9 [Communication][asvsV9]
* V10 [Malicious Code][asvsV10]
* V11 [Business Logic][asvsV11]
* V12 [Files and Resources][asvsV12]
* V13 [API and Web Service][asvsV13]
* V14 [Configuration][asvsV14]

#### How to use it

The ASVS is a list of verification requirements that can be used to identify gaps in the security of web applications.
If the ASVS suggests using a control then that control should be considered for the application security,
it may be not applicable but at least the control should have been considered at some point in the development process.

The OWASP Spotlight series provides an overview of the ASVS and its uses:
'Project 19 - [OWASP Application Security Verification standard (ASVS)][spotlight19]'.

The OWASP Cheat Sheets have been indexed specifically for [each section of the ASVS][csasvs],
which can be used as documentation on controls for a given requirements category.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue130102] or [edit on GitHub][edit130102].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[asvsmd]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x00-Header.md
[asvsV1]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x10-V1-Architecture.md#v1-architecture-design-and-threat-modeling
[asvsV2]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x11-V2-Authentication.md#v2-authentication
[asvsV3]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x12-V3-Session-management.md#v3-session-management
[asvsV4]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x12-V4-Access-Control.md#v4-access-control
[asvsV5]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x13-V5-Validation-Sanitization-Encoding.md#v5-validation-sanitization-and-encoding
[asvsV6]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x14-V6-Cryptography.md#v6-stored-cryptography
[asvsV7]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x15-V7-Error-Logging.md#v7-error-handling-and-logging
[asvsV8]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x16-V8-Data-Protection.md#v8-data-protection
[asvsV9]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x17-V9-Communications.md#control-objective
[asvsV10]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x18-V10-Malicious.md#v10-malicious-code
[asvsV11]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x19-V11-BusLogic.md#v11-business-logic
[asvsV12]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x20-V12-Files-Resources.md#v12-files-and-resources
[asvsV13]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x21-V13-API.md#v13-api-and-web-service
[asvsV14]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x22-V14-Config.md#v14-configuration
[csasvs]: https://cheatsheetseries.owasp.org/IndexASVS.html
[edit130102]: https://github.com/OWASP/DevGuide/blob/main/docs/11-security-gap-analysis/01-guides/02-asvs.md
[issue130102]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2011-security-gap-analysis/01-guides/02-asvs
[spotlight19]: https://youtu.be/3puIavsZfAk
