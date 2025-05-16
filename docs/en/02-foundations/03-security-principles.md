This section is a very brief introduction to some concepts used within the software security domain,
as these may not be familiar to many application developers.
The OWASP [Cheat Sheet Series][csproject] provides more in depth explanations for these security principles,
see the further reading at the end of this section.

#### Overview

There are various concepts and terms used in the security domain that are fundamental
to the understanding and discussion of application security.
Security architects and security engineers will be familiar with these terms and development teams
will also need this understanding to implement secure applications.

#### Security by Design

Security should not be an afterthought or add-on. When developing systems, you should begin with identifying relevant
security requirements and treat them as an integral part of the overall process and system design. Begin with
establishing and adopting relevant principles and policies as a foundation for your design, then build security
into your development life cycle. Keep also in mind that the system you are building also will be needing maintenance
and that system operators will need to securely manage and even shutdown and dispose of the system. Therefore, commit
to secure operations by developing secure "operational management"[^1] principles and practices.

#### Security by Default

Secure by default means that the default configuration settings are the most secure settings possible. This is not
necessarily the most user-friendly settings. Evaluate what the settings should be, based on both risk analysis and
usability tests. As a result, the precise meaning is up to you to decide. Nevertheless, configure the system to only
provide the least functionality and to specifically prohibit and/or restrict the use of all other functions, ports,
protocols, and/or services. Also configure the defaults to be as restrictive as possible, according to best practices,
without compromising the "Psychological acceptability" and "Usability and Manageability" of the system.

#### No security guarantee

One of the most important principles of software security is that no application or system is totally
100% guaranteed to be secure from all attacks. This may seem an unusually pessimistic starting point
but it is merely acknowledging the real world; given enough time and enough resources any system can be compromised.
The goal of software security is not '100% secure' but to make it hard enough and the rewards small enough
that malicious actors look elsewhere for systems to exploit.

#### Defense in Depth

Also known as layered defense, [defense in depth][did] is a security principle where defense against attack
is provided by multiple security controls.
The aim is that single points of complete compromise are eliminated or mitigated
by the incorporation of a series or multiple layers of security safeguards and risk-mitigation countermeasures.

If one layer of defense turns out to be inadequate then, if diverse defensive strategies are in place,
another layer of defense may prevent a full breach and if that one is circumvented then
the next layer may block the exploit.

#### Fail Safe

This is a security principle that aims to maintain confidentiality, integrity and availability
when an error condition is detected.
These error conditions may be a result of an attack, or may be due to design or implementation failures,
in any case the system / applications should default to a secure state rather than an unsafe state.

For example unless an entity is given explicit access to an object,
it should be denied access to that object by default.
This is often described as 'Fail Safe Defaults' or 'Secure by Default'.

In the context of software security, the term 'fail secure' is commonly used interchangeably with fail safe,
which comes from physical security terminology.
Failing safe also helps software resiliency in that the system / application can rapidly recover
upon design or implementation flaws.

#### Least Privilege

A security principle in which a person or process is given only the minimum level of access rights (privileges)
that is necessary for that person or process to complete an assigned operation.
This right must be given only for a minimum amount of time that is necessary to complete the operation.

This helps to limits the damage when a system is compromised by minimizing the ability of an attacker
to escalate privileges both laterally or vertically.
In order to apply this [principle of least privilege][elp] proper granularity
of privileges and permissions should be established.

#### Compartmentalize

The principle of least privilege works better if access rights are not an "all or nothing" access model.
Instead, compartmentalize the access to information on a "need-to-know" basis in order to perform certain tasks.
The compartmentalization principle helps in minimizing the impact of a security breach in case of a successful
breach attempt but must be used in moderation in order to prevent the system from becoming unmanageable.
Therefore, follow also the principle of "Economy of Mechanism".

#### Separation of Duties

Also known as [separation of privilege][sop], separation of duties is a security principle which requires that
the successful completion of a single task
is dependent upon two or more conditions that are insufficient, individually by themselves, for completing the task.

There are many applications for this principle,
for example limiting the damage an aggrieved or malicious insider can do, or by limiting privilege escalation.

#### Economy of Mechanism

Also known as 'keep it simple', if there are multiple implementations then the simplest
and most easily understood implementation should be chosen.

The likelihood of vulnerabilities increases with the complexity of the software architectural design and code,
and increases further if it is hard to follow or review the code.
The attack surface of the software is reduced by keeping the software design
and implementation details simple and understandable.

#### Complete Mediation

A security principle that ensures that authority is not circumvented in subsequent requests of an object by a subject,
by checking for authorization (rights and privileges) upon every request for the object.

In other words, the access requests by a subject for an object are completely mediated every time,
so that all accesses to objects must be checked to ensure that they are allowed.

#### Open Design

The open design security principle states that the implementation details of the design
should be independent of the design itself,
allowing the design to remain open while the implementation can be kept secret.
This is in contrast to security by obscurity where the security of the software
is dependent upon the obscuring of the design itself.

When software is architected using the open design concept,
the review of the design itself will not result in the compromise of the safeguards in the software.

#### Least Common Mechanism

The security principle of least common mechanisms disallows the sharing of mechanisms that are common
to more than one user or process if the users or processes are at different levels of privilege.
This is important when defending against privilege escalation.

#### Psychological acceptability

A security principle that aims at maximizing the usage and adoption of the security functionality in the software
by ensuring that the security functionality is easy to use and at the same time transparent to the user.
Ease of use and transparency are essential requirements for this security principle to be effective.

Security controls should not make the resource significantly more difficult to access
than if the security control were not present.
If a security control provides too much friction for the users then they may look for ways
to defeat the control and “prop the doors open”.

#### Usability and Manageability

Is a principle related to psychological acceptability, but goes beyond just the perceived psychological
acceptability to also include the design, implementation and operation of security controls.
The configuration, administration and integration of security components should not be overly complex or
obscure. Therefore, always use open standards for portability and interoperability, use common language
in developing security requirements, design security to allow for regular adoption of new technology,
ensure a secure and logical upgrade process exist, automate security management activities and strive for
operational ease of use.

#### Secure the Weakest Link

This security principle states that the resiliency of your software against hacker attempts will depend heavily
on the protection of its weakest components, be it the code, service or an interface. Therefore, identifying the
weakest component and addressing the most serious risk first, until an acceptable level of risk is attained, is
considered good security practice.

#### Leveraging Existing Components

This is a security principle that focuses on ensuring that the attack surface is not increased
and no new vulnerabilities are introduced by promoting the reuse of existing
software components, code and functionality.

Existing components are more likely to be tried and tested, and hence more secure,
and also should have security patches available.
In addition components developed within the open source community have the further benefit of 'many eyes'
and are therefore likely to be even more secure.

#### References

* OWASP Cheat Sheet series
  * [Authentication Cheat Sheet][csauthn]
  * [Authorization Cheat Sheet][csauthz]
  * [Secure Product Design Cheat Sheet][spdcs]
* OWASP Top 10 Proactive Controls
  * [C5: Secure by Default Configurations](https://top10proactive.owasp.org/the-top-10/c5-secure-by-default/)
* Other
  * [Compartmentalization (information security)](https://en.wikipedia.org/wiki/Compartmentalization_(information_security)),
(Wikipedia)
  * [Least Functionality](https://csf.tools/reference/nist-sp-800-53/r5/cm/cm-7/), (NIST)
  * [Security by Design](https://pubs.opengroup.org/security/o-esa/#_Toc291061712), (Open Group)
  * [Usability and Manageability](https://pubs.opengroup.org/security/o-esa/#_Toc291061714), (Open Group)

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0403] or [edit on GitHub][edit0403].

[^1]: [Operational Management](https://owaspsamm.org/model/operations/operational-management/), (SAMM)

[csauthn]: https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet
[csauthz]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet
[csproject]: https://owasp.org/www-project-cheat-sheets/
[did]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet.html#2-the-principle-of-defense-in-depth
[edit0403]: https://github.com/OWASP/DevGuide/blob/main/docs/en/02-foundations/03-security-principles.md
[elp]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet.html#enforce-least-privileges
[issue0403]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/03-security-principles
[sop]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet.html#1-the-principle-of-least-privilege-and-separation-of-duties
[spdcs]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet
