The fundamental principles of application security rely on the security concepts referenced in this developer guide.
This section aims to provide an introduction to fundamental principles that any development team must be familiar with.

#### Software Assurance Maturity Model

![SAMM logo](../../assets/images/logos/samm.png "OWASP SAMM"){ align=right width=250 }

The Software Assurance Maturity Model ([SAMM][samm]) provides context for the scope of software security
and the foundations of good security practice:

* [Governance][sammg]
* [Design][sammd]
* [Implementation][sammi]
* [Verification][sammv]
* [Operations][sammo]

The SAMM model describes these foundations of software security as Business Functions,
which are further divided into Business Practices.
The OWASP Software Assurance Maturity Model ([SAMM][samm]) is used throughout this Developer Guide;
most of the sections in the Developer Guide reference at least one of the Business Functions or Practices from SAMM.

#### CIA triad

Security is simply about controlling who can interact with your information,
what they can do with it, and when they can interact with it.
These characteristics of security can be described using the CIA triad.

CIA stands for Confidentiality, Integrity and Availability,
and it is usually depicted as a triangle representing the strong bonds between its three tenets.
This triad is considered the pillars of application security,
often Confidentiality, Integrity or Availability are used as a properties of data or processes within a given system.
The CIA triad can be extended with the AAA triad: Authorization, Authentication and Auditing.

#### Confidentiality

Confidentiality is the protection of data against unauthorized disclosure;
it is about ensuring that only those with the correct authorization can access the data
and applies to both data at rest and to data in transit.
Confidentiality is also related to the broader concept of data privacy.

#### Integrity

Integrity is about protecting data against unauthorized modification, or assuring data trustworthiness.
The concept contains the notion of data integrity (data has not been changed accidentally or deliberately)
and the notion of source integrity (data came from or was changed by a legitimate source).

#### Availability

Availability is about ensuring the presence of information or resources.
This concept relies not just on the availability of the data itself, for example by using replication of data,
but also on the protection of the services that provide access to the data, for example by using load balancing.

#### AAA triad

The CIA triad is often extended with Authentication, Authorization and Auditing as these are closely linked to CIA concepts.
CIA has a strong dependency on Authentication and Authorization;
the confidentiality and integrity of sensitive data can not be assured without them.
Auditing is added as it can provide the mechanism to ensure proof of any interaction with the system.

#### Authentication

[Authentication][csauthn] is about confirming the identity of the entity that wants to interact with a secure system.
For example the entity could be an automated client or a human actor;
in either case authentication is required for a secure application.

#### Authorization

[Authorization][csauthz] is about specifying access rights to secure resources (data, services, files, applications, etc).
These rights describe the privileges or access levels related to the resources that are being secured.
Authorization is usually preceded by successful authentication.

#### Auditing

Auditing is about keeping track of implementation-level events, as well as domain-level events taking place in a system.
This helps to provide non-repudiation, which means that changes or actions on the protected system are undeniable.
Auditing can provide not only technical information about the running system,
but also proof that particular actions have been performed.
The typical questions that are answered by auditing are "Who did What, When and potentially How?"

#### Vulnerabilities

NIST defines a [vulnerability][nistvuln] as 'Weakness in an information system, system security procedures,
internal controls, or implementation that could be exploited or triggered by a threat source.'

There are many weaknesses or bugs in every large application, but the term vulnerability is generally reserved
for those weaknesses or bugs where there is a risk that a threat actor could exploit it using a threat vector.

Well known security vulnerabilities are :

* [Clickjacking][csclick]
* [Credential Stuffing][cscreds]
* [Cross-site leaks][csxsleaks]
* [Denial of Service][csdos] (DoS) attacks
* DOM based [XSS attacks][csdom] including [DOM Clobbering][csdomclub]
* [IDOR][csidor] (Insecure Direct Object Reference)
* [Injection][csinjection] including [OS Command injection][csosinjection] and [XXE][csxxe]
* LDAP specific [injection attacks][csldap]
* [Prototype pollution][csproto]
* [SSRF][csssrf] attacks
* [SQL injection][cssql] and the use of [Query Parameterization][csquery]
* [Unvalidated redirects and forwards][csredirect]
* [XSS attacks][csxss] and [XSS Filter Evasion][csxssevade]

#### HTTP and HTML

Although not a security fundamental as such, web applications rely on HTTP communications and HTML.
Both application developers and security engineers should have a good understanding of HTTP
and the HTML language along with their various security controls.

Most application development teams will be familiar with HTTP communications and the HTML standard,
but if necessary refer to the training from the [W3 Consortium][w3consortium] or the [W3 Schools][w3schools].
The OWASP [Cheat Sheet Series][cheatsheets] provide web application developers with the information
needed to produce secure software :

* The [HTML5 Security][cshtml5] cheat sheet describes a wide range of controls,
  aligned with the current [HTML Living Standard][htmlliving]
* Refer to the [Securing Cascading Style Sheets][cscss] cheat sheet for CSS
* The HTTP headers need to be secure, see the [HTTP Security Response Headers][csheaders] cheat sheet
* Strongly consider [HTTP Strict Transport Security][csstrict]
* If the application has a file upload feature, follow the [File Upload][csfile] cheat sheet
* Ensure content security policy is in place with the [Content Security Policy][cscsp] cheat sheet
* Using JWTs for a Java application? Refer to the [JSON Web Token][csjwt] cheat sheet
* Storing or sending objects? Check out the [Deserialization][csserial] cheat sheet

#### References

* [WHATWG][whatwg] [HTML Living Standard][htmlliving]
* OWASP [Cheat Sheet Series][cheatsheets]
* OWASP [Software Assurance Maturity Model][samm] (SAMM)

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0401] or [edit on GitHub][edit0401].

[cheatsheets]: https://cheatsheetseries.owasp.org/
[csclick]: https://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet
[cscreds]: https://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet
[cscsp]: https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet
[cscss]: https://cheatsheetseries.owasp.org/cheatsheets/Securing_Cascading_Style_Sheets_Cheat_Sheet
[csdom]: https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet
[csdomclub]: https://cheatsheetseries.owasp.org/cheatsheets/DOM_Clobbering_Prevention_Cheat_Sheet
[csdos]: https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet
[csidor]: https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet
[csinjection]: https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet
[csosinjection]: https://cheatsheetseries.owasp.org/cheatsheets/OS_Command_Injection_Defense_Cheat_Sheet
[csldap]: https://cheatsheetseries.owasp.org/cheatsheets/LDAP_Injection_Prevention_Cheat_Sheet
[csproto]: https://cheatsheetseries.owasp.org/cheatsheets/Prototype_Pollution_Prevention_Cheat_Sheet
[csauthn]: https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet
[csauthz]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet
[csfile]: https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet
[csheaders]: https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Headers_Cheat_Sheet
[cshtml5]: https://cheatsheetseries.owasp.org/cheatsheets/HTML5_Security_Cheat_Sheet
[csjwt]: https://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_for_Java_Cheat_Sheet
[csredirect]: https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet
[csserial]: https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet
[cssql]: https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet
[csquery]: https://cheatsheetseries.owasp.org/cheatsheets/Query_Parameterization_Cheat_Sheet
[csssrf]:  https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet
[csstrict]: https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet
[csxss]: https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet
[csxsleaks]: https://cheatsheetseries.owasp.org/cheatsheets/XS_Leaks_Cheat_Sheet
[csxssevade]: https://cheatsheetseries.owasp.org/cheatsheets/XSS_Filter_Evasion_Cheat_Sheet
[csxxe]: https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet
[edit0401]: https://github.com/OWASP/DevGuide/blob/main/docs/en/02-foundations/01-security-fundamentals.md
[htmlliving]: https://html.spec.whatwg.org/multipage/
[issue0401]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/01-security-fundamentals
[nistvuln]: https://csrc.nist.gov/glossary/term/vulnerability
[samm]: https://owaspsamm.org/about/
[sammd]: https://owaspsamm.org/model/design/
[sammg]: https://owaspsamm.org/model/governance/
[sammi]: https://owaspsamm.org/model/implementation/
[sammo]: https://owaspsamm.org/model/operations/
[sammv]: https://owaspsamm.org/model/verification/
[w3consortium]: https://www.w3.org/
[w3schools]: https://www.w3schools.com/html/
[whatwg]: https://whatwg.org/
