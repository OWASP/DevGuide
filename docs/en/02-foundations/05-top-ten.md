![Top 10 logo](../../assets/images/logos/top10.png "OWASP Top 10"){ align=right width=180 }

The OWASP Top Ten is a very well known list of web application security risks,
and is included by the OWASP Software Assurance Maturity Model [(SAMM)][samm]
in the Education & Guidance practice within the Governance business function.

#### Overview

The OWASP [Top 10 Web Application Security Risks][top10project] project is probably the most well known security concept
within the security community, achieving wide spread acceptance and fame soon after its release in 2003.
Often referred to as just the 'OWASP Top Ten', it is a list that identifies the most important threats
to web applications and seeks to rank them in importance and severity.

The list has changed over time, with some threat types becoming more of a problem to web applications
and other threats becoming less of a risk as technologies change.
The [latest version][top10] was issued in 2025 and each category is summarized below.
Compared to the 2021 version, Server-Side Request Forgery is now part of Broken Access Control,
Vulnerable and Outdated Components has grown into Software Supply Chain Failures,
and Mishandling of Exceptional Conditions is a new category.

Note that there are various 'OWASP Top Ten' projects, for example the 'OWASP Top 10 for Large Language Model Applications',
so to avoid confusion the context should be noted when referring to these lists.

#### A01:2025 Broken Access Control

Access control involves the use of protection mechanisms that can be categorized as:

* Authentication (proving the identity of an actor)
* Authorization (ensuring that a given actor can access a resource)
* Accountability (tracking of activities that were performed)

Broken Access Control is where the product does not restrict, or incorrectly restricts, access to a resource
from an unauthorized or malicious actor.
When a security control fails or is not applied then attackers can compromise the security of the product
by gaining privileges, reading sensitive information, executing commands, evading detection, etc.

Broken Access Control can take many forms, such as path traversal or elevation of privilege,
and in the 2025 version it also includes Server-Side Request Forgery (SSRF),
where the application can be coerced into sending requests to destinations the attacker could not reach directly.
Refer to [A01 Broken Access Control][a01] and follow the [Authorization][csauthz]
and [SSRF Prevention][csssrf] cheat sheets.

#### A02:2025 Security Misconfiguration

Systems and large applications can be configurable, and this configuration is often used to secure the system/application.
If this configuration is misapplied then the application may no longer be secure,
and instead be vulnerable to well-known exploits. The [A02 Security Misconfiguration][a02] page contains
a common example of misconfiguration where default accounts and their passwords are still enabled and unchanged.
These passwords and accounts are usually well-known and provide an easy way for malicious actors to compromise applications.

Security misconfiguration has moved up to second place in the 2025 version,
reflecting how much of an application's security now depends on configurable frameworks, platforms and cloud services.
Establish a repeatable hardening process, and where infrastructure is defined as code
follow the [Infrastructure as Code Security][csiac] cheat sheet.

#### A03:2025 Software Supply Chain Failures

Software supply chain failures are breakdowns or compromises in the process of building, distributing, or updating software.
This category expands the 2021 'Vulnerable and Outdated Components' to cover the whole supply chain:
third party dependencies, build tools and pipelines, and the way updates are delivered.

Keeping all the third party software dependencies up to date is still one of the easiest
and most effective security activities.
If a vulnerable dependency is identified by a malicious actor during the reconnaissance phase of an attack
then there are databases available, such as [Exploit Database][exploit], that will provide a description of any exploit,
making it easy for vulnerable third party software dependencies to be exploited.
Refer to [A03 Software Supply Chain Failures][a03] and the [Software Supply Chain Security][cschain]
and [Vulnerable Dependency Management][csdeps] cheat sheets.

#### A04:2025 Cryptographic Failures

Referring to [OWASP Top 10 A04:2025][a04], sensitive data should be protected when at rest and in transit.
Cryptographic failures occur when the cryptographic security control is either broken or not applied,
and the data is exposed to unauthorized actors - malicious or not.

It is important to protect data both at rest, when it is stored in an area of memory,
and also when it is in transit such as being transmitted across a communication channel or being transformed.
Crypto failures can take many forms and may be subtle - a security control that looks secure may be easily broken.
Follow the [Cryptographic Storage][cscrypto] and [Transport Layer Security][cstls] cheat sheets
to get the basic crypto controls in place and consider putting a crypto audit in place.

#### A05:2025 Injection

A lack of input validation and sanitization can lead to injection exploits,
and this risk has been a constant feature of the OWASP Top Ten since the first version was published in 2003.
These vulnerabilities occur when untrusted input is sent to an interpreter,
such as a browser, a database or the command line,
and the interpreter executes parts of that input as commands; see [A05 Injection][a05] for further explanations.

The security control is straight forward: all input from untrusted sources should be sanitized and validated,
and queries and commands should keep data separate from code, for example by using parameterized queries.
See the [Injection Prevention][csinject] cheat sheet for the various types of input and their controls.

#### A06:2025 Insecure Design

It is important that security is built into applications from the beginning and not applied as an afterthought.
The [A06 Insecure Design][a06] category recognizes this and advises that
the use of threat modeling, secure design patterns, and reference architectures
should be incorporated within the application design and architecture activities.

In practice this involves establishing a secure development lifecycle that encourages
the identification of security requirements, the periodic use of threat modeling
and consideration of existing secure libraries and frameworks.
See the [Threat Modeling][cstm] and [Secure Product Design][csdesign] cheat sheets.

#### A07:2025 Authentication Failures

Confirmation of the user's identity, authentication, and session management is critical
to protect the system or application against authentication related attacks.
Referring to risk [A07 Authentication Failures][a07], authentication can fail in several ways,
for example by permitting automated attacks such as credential stuffing and password spraying,
by allowing weak or well-known passwords, or by missing or ineffective multi-factor authentication.
This category was called 'Identification and Authentication Failures' in the 2021 version.

Refer to the [Authentication][csauthn] and [Password Storage][cspass] cheat sheets for the good practices that are needed.
There are also third party suppliers of Identity and Access Management (IAM) that will provide this as a service,
consider the cost / benefit of using these (often commercial) suppliers.

#### A08:2025 Software or Data Integrity Failures

Software and data integrity failures relate to code and infrastructure that does not protect against
invalid or untrusted code or data being treated as trusted and valid.
Examples include relying on plugins or libraries from untrusted sources, auto-update without integrity checks,
CI/CD pipelines that pull artifacts without verifying them, and insecure deserialization of untrusted data.
Refer to [A08 Software or Data Integrity Failures][a08] and the [CI/CD Security][cscicd]
and [Deserialization][csdeser] cheat sheets.

#### A09:2025 Security Logging and Alerting Failures

Logging and monitoring helps detect, escalate, and respond to active breaches; without it breaches will not be detected.
The 2025 version renames this category from 'Security Logging and Monitoring Failures'
to stress that logs only help if they raise alerts that someone acts on.
[A09 Security Logging and Alerting Failures][a09] lists various logging, monitoring and alerting techniques.
The [Logging][cslogging] and [Logging Vocabulary][cslogvocab] cheat sheets provide guidance on sufficient logging
and a common set of terms, formats and key words that allows for easier monitoring, analysis and alerting.

#### A10:2025 Mishandling of Exceptional Conditions

This is a new category in the 2025 version.
Mishandling exceptional conditions happens when an application fails to prevent, detect, or respond to unusual situations,
which leads to crashes, unexpected behavior, and sometimes vulnerabilities;
for example error messages that reveal sensitive information, or a failure part way through a transaction
that leaves the application in an inconsistent or insecure state ('failing open').
Refer to [A10 Mishandling of Exceptional Conditions][a10] and the [Error Handling][cserror] cheat sheet.

#### OWASP top tens

There are various 'Top 10' projects created by OWASP that, depending on the context,
may also be referred to as 'OWASP Top 10'. Here is a list of the stable 'OWASP Top 10' projects:

* [API Security Top 10][apisec]
* [Citizen Development Top 10][cd10]
* [Data Security Top 10][data10]
* [Mobile Top 10][mobile10]
* [Serverless Top 10][serverless10]
* [Top 10 CI/CD Security Risks][cicd10]
* [Top 10 for Large Language Model Applications][llm10]
* [Top 10 Privacy Risks][privacy10]
* [Top 10 Proactive Controls][proactive10]
* [Top 10 Web Application Security Risks][top10]

Other OWASP Top 10s are 'incubator' projects, which are work in progress, so this list will change over time.

----

The OWASP Developer Guide is a community effort; if you see something that needs changing
then [submit an issue][issue0405] or [edit on GitHub][edit0405].

[a01]: https://top10.owasp.org/2025/A01_2025-Broken_Access_Control/
[a02]: https://top10.owasp.org/2025/A02_2025-Security_Misconfiguration/
[a03]: https://top10.owasp.org/2025/A03_2025-Software_Supply_Chain_Failures/
[a04]: https://top10.owasp.org/2025/A04_2025-Cryptographic_Failures/
[a05]: https://top10.owasp.org/2025/A05_2025-Injection/
[a06]: https://top10.owasp.org/2025/A06_2025-Insecure_Design/
[a07]: https://top10.owasp.org/2025/A07_2025-Authentication_Failures/
[a08]: https://top10.owasp.org/2025/A08_2025-Software_or_Data_Integrity_Failures/
[a09]: https://top10.owasp.org/2025/A09_2025-Security_Logging_and_Alerting_Failures/
[a10]: https://top10.owasp.org/2025/A10_2025-Mishandling_of_Exceptional_Conditions/
[csauthz]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet
[csssrf]: https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet
[csiac]: https://cheatsheetseries.owasp.org/cheatsheets/Infrastructure_as_Code_Security_Cheat_Sheet
[csdeps]: https://cheatsheetseries.owasp.org/cheatsheets/Vulnerable_Dependency_Management_Cheat_Sheet
[cscrypto]: https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet
[cstls]: https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet
[csinject]: https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet
[csdesign]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet
[csauthn]: https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet
[cspass]: https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet
[cscicd]: https://cheatsheetseries.owasp.org/cheatsheets/CI_CD_Security_Cheat_Sheet
[csdeser]: https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet
[cslogging]: https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet
[cslogvocab]: https://cheatsheetseries.owasp.org/cheatsheets/Logging_Vocabulary_Cheat_Sheet
[cserror]: https://cheatsheetseries.owasp.org/cheatsheets/Error_Handling_Cheat_Sheet
[apisec]: https://api-security.owasp.org/
[cd10]: https://owasp.org/projects/citizen-development-top-10
[cicd10]: https://owasp.org/projects/top-10-cicd-security-risks
[cschain]: https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet
[cstm]: https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet
[data10]: https://owasp.org/projects/data-security-top-10
[edit0405]: https://github.com/OWASP/DevGuide/blob/main/docs/en/02-foundations/05-top-ten.md
[exploit]: https://www.exploit-db.com/
[issue0405]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/05-top-ten
[mobile10]: https://owasp.org/projects/mobile-top-10
[privacy10]: https://owasp.org/projects/top-10-privacy-risks
[proactive10]: https://top10proactive.owasp.org/
[samm]: https://owaspsamm.org/about/
[serverless10]: https://owasp.org/projects/serverless-top-10
[top10project]: https://owasp.org/projects/top-ten
[top10]: https://top10.owasp.org/
[llm10]: https://owasp.org/projects/top-10-for-large-language-model-applications
