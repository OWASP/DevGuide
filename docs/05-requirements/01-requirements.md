### 3.1 Requirements in practice

This section deals with Security Requirements, which is a security practice in the Design business function
section of the OWASP Software Assurance Maturity Model ([SAMM][samm]).
This security requirements practice has two activities, Software Requirements and Supplier Security,
with regulatory and statutory requirements being an important subset of both these activities.

#### Overview

Security requirements are part of every secure development process
and form the foundation for the application's security posture.
Requirements will certainly help with the prevention of many types of vulnerabilities.

Requirements come from various sources, three common ones being:

1. Software-related requirements which specify objectives and expectations
    to protect the service and data at the core of the application
2. Requirements relative to supplier organizations that are part of the development context of the application
3. Regulatory and Statutory requirements

Ideally security requirements are built in at the beginning of development,
but there is no wrong time to consider these security requirements and add new ones as necessary.

#### Software requirements

Defining security requirements can be daunting at times,
for example they may reference cryptographic techniques that can be misapplied,
but it is perfectly acceptable to state these requirements in everyday language.
For example a security requirement could be written as “Identify the user of the application at all times”
and this is certainly sufficient to require that authentication is included in the design.

The SAMM [Security Requirements practice][sammdsr] lists maturity levels of software security requirements
that specify objectives and expectations.
Choose the level that is appropriate for the organization and the development team,
with the understanding that any of these levels are perfectly acceptable.

The software security requirements maturity levels are:

1. High-level application security objectives are mapped to functional requirements
2. Structured security requirements are available and utilized by developer teams
3. Build a requirements framework for product teams to utilize

OWASP provides projects that can help in identifying security requirements
that will protect the service and data at the core of the application.
The [Application Security Verification Standard][asvs] provides a list of requirements for secure development,
and this can be used as a starting point for the security requirements.
The [Mobile Application Security][mas] provides a similar set of standard security requirements for mobile applications.

Consider using [Abuse Cases][csabuse] to identify possible attacks and the controls required to mitigate them.
This can then feed into the software security requirements.

#### Supplier security

External suppliers involved in the development process need to be assessed for their security practices and compliance.
Depending on their level of involvement these suppliers can have a significant impact on the security of the application
so a set of security requirements will have to be negotiated with them.

[SAMM][sammdsr] lists maturity levels for the security requirements
that will clarify the strengths and weaknesses of your suppliers.
Note that supplier security is distinct from security of third-party software and libraries,
and the use of third-party and open source software is discussed
in its own section on dependency checking and tracking.

The supplier security requirements maturity levels are:

1. Evaluate the supplier based on organizational security requirements
2. Build security into supplier agreements in order to ensure compliance with organizational requirements
3. Ensure proper security coverage for external suppliers by providing clear objectives

#### Regulatory and statutory requirements

Regulatory requirements can include security requirements which then must be taken into account.
Different industries are regulated are regulated to a lesser or greater extent,
and the only general advice is to be aware and follow the regulations.

Various jurisdictions will have different statutory requirements that may result in security requirements.
Any applicable statutory security requirement should be added to the application security requirements.
Similarly to regulatory requirements,
the only general advice is to be familiar with and follow the appropriate statutory requirements.

#### Periodic review

The security requirements should be identified and recorded at the beginning of any new development
and also when new features are added to an existing application.
These security requirements should be periodically revisited and revised as necessary;
for example security standards are updated and new regulations come into force,
both of which may have a direct impact on the application.

#### References

* OWASP projects:
  * [Software Assurance Maturity Model (SAMM)][samm]
  * [Top Ten Proactive Controls][proactive10]
  * [Application Security Verification Standard (ASVS)][asvs]
  * [Mobile Application Security][mas]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0501] or [edit on GitHub][edit0501].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[csabuse]: https://cheatsheetseries.owasp.org/cheatsheets/Abuse_Case_Cheat_Sheet
[issue0501]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2005-requirements/01-requirements
[mas]: https://mas.owasp.org/
[edit0501]: https://github.com/OWASP/DevGuide/blob/main/docs/05-requirements/01-requirements.md
[proactive10]: https://owasp.org/www-project-proactive-controls/
[samm]: https://owaspsamm.org/about/
[sammdsr]: https://owaspsamm.org/model/design/security-requirements/
