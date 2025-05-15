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
The [latest version][top10] was issued in 2021 and each category is summarized below.

Note that there are various 'OWASP Top Ten' projects, for example the 'OWASP Top 10 for Large Language Model Applications',
so to avoid confusion the context should be noted when referring to these lists.

#### A01:2021 Broken Access Control

Access control involves the use of protection mechanisms that can be categorized as:

* Authentication (proving the identity of an actor)
* Authorization (ensuring that a given actor can access a resource)
* Accountability (tracking of activities that were performed)

Broken Access Control is where the product does not restrict, or incorrectly restricts, access to a resource
from an unauthorized or malicious actor.
When a security control fails or is not applied then attackers can compromise the security of the product
by gaining privileges, reading sensitive information, executing commands, evading detection, etc.

Broken Access Control can take many forms, such as path traversal or elevation of privilege,
so refer to both the [Common Weakness Enumeration CWE-284][cwe284] and [A01 Broken Access Control][a01]
and also follow the various [OWASP Cheat Sheets][a01cs] related to access controls.

#### A02:2021 Cryptographic Failures

Referring to [OWASP Top 10 A02:2021][a02], sensitive data should be protected when at rest and in transit.
Cryptographic failures occur when the cryptographic security control is either broken or not applied,
and the data is exposed to unauthorized actors - malicious or not.

It is important to protect data both at rest, when it is stored in an area  of memory,
and also when it is in transit such as being transmitted across a communication channel or being transformed.
A good example of protecting data transformation is given by [A02 Cryptographic Failures][a02]
where sensitive data is properly encrypted in a database, but the export function automatically
decrypts the data leading to sensitive data exposure.

Crypto failures can take many forms and may be subtle - a security control that looks secure may be easily broken.
Follow the crypto [OWASP Cheat Sheets][a02cs] to get the basic crypto controls in place
and consider putting a crypto audit in place.

#### A03:2021 Injection

A lack of input validation and sanitization can lead to injection exploits,
and this risk has been a constant feature of the OWASP Top Ten since the first version was published in 2003.
These vulnerabilities occur when hostile data is directly used within the application
and can result in malicious data being used to subvert the application; see [A03 Injection][a03] for further explanations.

The security control is straight forward: all input from untrusted sources should be sanitized and validated.
See the [Injection Cheat Sheets][a03cs] for the various types of input and their controls.

#### A04:2021 Insecure Design

It is important that security is built into applications from the beginning and not applied as an afterthought.
The [A04 Insecure Design][a04] category recognizes this and advises that
the use of threat modeling, secure design patterns, and reference architectures
should be incorporated within the application design and architecture activities.

In practice this involves establishing a secure development lifecycle that encourages
the identification of security requirements, the periodic use of threat modeling
and consideration of existing secure libraries and frameworks.
This category was introduced in the 2021 version and for now the supporting cheat sheets only cover [threat modeling][cstm];
as this category becomes more established it is expected that more supporting information will become available.

#### A05:2021 Security Misconfiguration

Systems and large applications can be configurable, and this configuration is often used to secure the system/application.
If this configuration is misapplied then the application may no longer be secure,
and instead be vulnerable to well-known exploits. The [A05 Security Misconfiguration][a05] page contains
a common example of misconfiguration where default accounts and their passwords are still enabled and unchanged.
These passwords and accounts are usually well-known and provide an easy way for malicious actors to compromise applications.

Both the [OWASP Top 10 A05:2021][a05] and the linked [OWASP Cheat Sheets][a05cs] provide strategies to establish
a concerted, repeatable application security configuration process to minimize misconfiguration.

#### A06:2021 Vulnerable and Outdated Components

Perhaps one of the easiest and most effective security activities
is keeping all the third party software dependencies up to date.
If a vulnerable dependency is identified by a malicious actor during the reconnaissance phase of an attack
then there are databases available, such as [Exploit Database][exploit], that will provide a description of any exploit.
These databases can also provide ready made scripts and techniques for attacking a given vulnerability,
making it easy for vulnerable third party software dependencies to be exploited .

Risk [A06 Vulnerable and Outdated Components][a06] underlines the importance of this activity,
and recommends that fixes and upgrades to the underlying platform, frameworks, and dependencies
are based on a risk assessment and done in a 'timely fashion'.
Several tools can used to analyze dependencies and flag vulnerabilities, refer to the [Cheat Sheets][a06cs] for these.

#### A07:2021 Identification and Authentication Failures

Confirmation of the user's identity, authentication, and session management is critical
to protect the system or application against authentication related attacks.
Referring to risk [A07 Identification and Authentication Failures][a07], authorization can fail in several ways
that often involve other OWASP Top Ten risks:

* broken access controls (A01)
* cryptographic failure (A02)
* default passwords (A05)
* out-dated libraries (A06)

Refer to the [Cheat Sheets][a07cs] for the several good practices that are needed for secure authorization.
There are also third party suppliers of Identity and Access Management (IAM) that will provide this as a service,
consider the cost / benefit of using these (often commercial) suppliers.

#### A08:2021 Software and Data Integrity Failures

Software and data integrity failures relate to code and infrastructure that does not protect against integrity violations.
This is a wide ranging category that describes [supply chain attacks][cschain],
compromised auto-update and use of untrusted components for example.
[A07 Software and Data Integrity Failures][a08] was a new category introduced in 2021
so there is little information available from the [Cheat Sheets][a08cs],
but this is sure to change for such an important threat.

#### A09:2021 Security Logging and Monitoring Failures

Logging and monitoring helps detect, escalate, and respond to active breaches; without it breaches will not be detected.
[A09 Security Logging and Monitoring Failures][a09] lists various logging and monitoring techniques that should be familiar,
but also others that may not be so common;
for example monitoring the DevOps supply chain may be just as important as monitoring the application or system.
The [Cheat Sheets][a09cs] provide guidance on sufficient logging and also provide for a common logging vocabulary.
The aim of this common vocabulary is to provide logging that uses a common set of terms, formats and key words;
and this allows for easier monitoring, analysis and alerting.

#### A10:2021 Server-Side Request Forgery

Referring to [A10 Server-Side Request Forgery (SSRF)][a10], these vulnerabilities can occur
whenever a web application is fetching a remote resource without validating the user-supplied URL.
These exploits allow an attacker to coerce the application to send a crafted request to an unexpected destination,
even when protected by a firewall, VPN, or another type of network access control list.
Fetching a URL has become a common scenario for modern web applications and as a result the incidence of SSRF is increasing,
especially for [cloud services][cscloud] and more complex application architectures.

This is a new category introduced in 2021 with a single (for now) [Cheat Sheet][a10cs] that deals with SSRF.

#### OWASP top tens

There are various 'Top 10' projects created by OWASP that, depending on the context,
may also be referred to as 'OWASP Top 10'. Here is a list of the stable 'OWASP Top 10' projects:

* [API Security Top 10][apisec]
* [Data Security Top 10][data10]
* [Low-Code/No-Code Top 10][lcnc10]
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

[a01]: https://owasp.org/Top10/A01_2021-Broken_Access_Control/
[a01cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a012021-broken-access-control
[a02]: https://owasp.org/Top10/A02_2021-Cryptographic_Failures/
[a02cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a022021-cryptographic-failures
[a03]: https://owasp.org/Top10/A03_2021-Injection/
[a03cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a032021-injection
[a04]: https://owasp.org/Top10/A04_2021-Insecure_Design/
[a05]: https://owasp.org/Top10/A05_2021-Security_Misconfiguration/
[a05cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a052021-security-misconfiguration
[a06]: https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/
[a06cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a062021-vulnerable-and-outdated-components
[a07]: https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/
[a07cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a072021-identification-and-authentication-failures
[a08]: https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/
[a08cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a082021-software-and-data-integrity-failures
[a09]: https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/
[a09cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a092021-security-logging-and-monitoring-failures
[a10]: https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/
[a10cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a102021-server-side-request-forgery-ssrf
[apisec]: https://owasp.org/API-Security
[cicd10]: https://owasp.org/www-project-top-10-ci-cd-security-risks/
[cschain]: https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet
[cscloud]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Cloud_Architecture_Cheat_Sheet
[cstm]: https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet
[cwe284]: https://cwe.mitre.org/data/definitions/284.html
[data10]: https://owasp.org/www-project-data-security-top-10/
[edit0405]: https://github.com/OWASP/DevGuide/blob/main/docs/en/02-foundations/05-top-ten.md
[exploit]: https://www.exploit-db.com/
[issue0405]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/05-top-ten
[lcnc10]: https://owasp.org/www-project-top-10-low-code-no-code-security-risks/
[mobile10]: https://owasp.org/www-project-mobile-top-10/
[privacy10]: https://owasp.org/www-project-top-10-privacy-risks/
[proactive10]: https://owasp.org/www-project-proactive-controls/
[samm]: https://owaspsamm.org/about/
[serverless10]: https://owasp.org/www-project-serverless-top-10/
[top10project]: https://owasp.org/www-project-top-ten/
[top10]: https://owasp.org/Top10/
[llm10]: https://owasp.org/www-project-top-10-for-large-language-model-applications/
