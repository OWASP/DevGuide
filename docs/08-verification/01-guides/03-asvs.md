### 6.1.3 ASVS

The [Application Security Verification Standard][asvs] (ASVS) is a long established OWASP flagship project,
and is widely used as a guide during the verification of web applications.

It can be downloaded from the [OWASP project page][asvs] in various languages and formats:
PDF, Word, CSV, XML and JSON. Having said that, the recommended way to consume the ASVS is to access
the [github markdown][asvsmd] pages directly - this will ensure that the latest version is used.

#### What is ASVS?

The ASVS is an open standard that sets out the coverage and 'level of rigor' expected when it comes to
performing web application security verification.
The standard also provides a basis for testing any technical security controls
that are relied on to protect against vulnerabilities in the application.

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

The ASVS defines three [levels of security verification][asvsL123]:

1. applications that only need low assurance levels; these applications are completely penetration testable
2. applications which contain sensitive data that require protection; the recommended level for most applications
3. the most critical applications that require the highest level of trust

Most applications will aim for Level 2, with only those applications that perform high value transactions,
or contain sensitive medical data, aiming for the highest level of trust at level 3.

#### Why use it?

The ASVS is used by many organizations as a basis for the verification of their web applications.
It is well established, the earlier versions were written in 2008, and it has been continually supported since then.

The ASVS is comprehensive, for example version 4.0.3 has a list of 286 verification requirements,
and these verification requirements have been created and agreed to by a wide security community.
Using the ASVS as a guide provides a firm basis for the verification process.

#### How to use it

The OWASP Spotlight series provides an overview of the ASVS and its uses:
'Project 19 - [OWASP Application Security Verification standard (ASVS)][spotlight19]'.

The ASVS should be used as a guide for the verification process, with the appropriate level of verification chosen from:

* Level 1: First steps, automated, or whole of portfolio view
* Level 2: Most applications
* Level 3: High value, high assurance, or high safety

Use the ASVS as guidance rather than trying to implement every possible control.
Tools such as [SecurityRAT][srat] can help create a more manageable subset of the ASVS requirements.

The ASVS guidance will help developers build security controls that will satisfy the application security requirements.

The OWASP Cheat Sheets have been indexed specifically for [each section of the ASVS][csasvs],
which can be used as documentation to help decide if a requirements category is to be included in verification.

#### References

* OWASP [Application Security Verification Standard][asvs] (ASVS)
* OWASP [ASVS Index][csasvs]
* OWASP [SecurityRAT][srat] project

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue080103] or [edit on GitHub][edit080103].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[asvsL123]: https://github.com/OWASP/ASVS/blob/v4.0.3/4.0/en/0x03-Using-ASVS.md#application-security-verification-levels
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
[edit080103]: https://github.com/OWASP/www-project-developer-guide/issues/new?labels=content&template=request.md&title=Update:%2008-verification/01-guides/05-asvs.md
[issue080103]: https://github.com/OWASP/www-project-developer-guide/issues/new?labels=enhancement&template=request.md&title=Update:%2008-verification/01-guides/03-asvs
[spotlight19]: https://youtu.be/3puIavsZfAk
[srat]: https://owasp.org/www-project-securityrat/
