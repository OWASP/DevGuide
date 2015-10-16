# Secure Design Principles

## Defense in Depth
Also known as layered defense, defense in depth is a security principle where single points of complete compromise are eliminated or mitigated by the incorporation of a series or multiple layers of security safeguards and risk-mitigation countermeasures.

Have diverse defensive strategies, so that if one layer of defense turns out to be inadequate, another layer of defense will hopefully prevent a full breach.

## Fail Safe
A security principle that aims to maintaining confidentiality, integrity and availability by defaulting to a secure state, rapid recovery of software resiliency upon design or implementation failure. In the context of software security, fail secure is commonly used interchangeably with fail safe, which comes from physical security terminology.

Unless a subject is given explicit access to an object, it should be denied access to that object, aka *Fail Safe Defaults*.

## Least Privilege
A security principle in which a person or process is given only the minimum level of access rights (privileges) that is necessary for that person or process to complete an assigned operation. This right must be given only for a minimum amount of time that is necessary to complete the operation.

Limits the damage in case of exploited vulnerability.

In order to apply this principle, proper granularity of privileges and permissions should be established.

## Separation of Duties
Also known as the [compartmentalization principle][1], or separation of privilege, separation of duties is a security principle which states that the successful completion of a single task is dependent upon two or more conditions that need to be met and just one of the conditions will be insufficient in completing the task by itself.

## Economy of Mechanism
This in layman terms is the [Keep It Simple, Stupid][2] principle because the likelihood of a greater number of vulnerabilities increases with the complexity of the software architectural design and code.

By keeping the software design and implementation details simple, the attack-ability or attack surface of the software is reduced.

## Complete Mediation
A security principle that ensures that authority is not circumvented in subsequent requests of an object by a subject, by checking for authorization (rights and privileges) upon every request for the object.

In other words, the access requests by a subject for an object is completely mediated every time.

“All accesses to objects must be checked to ensure that they are allowed.”

Performance v/s Security issue:
- Results of access check are often cached
- What if permissions have changed since the last check?
- Mechanisms to invalidate or flush caches after a change are often missing

## Open Design
The open design security principle states that the implementation details of the design should be independent of the design itself, which can remain open, unlike in the case of security by obscurity wherein the security of the software is dependent upon the obscuring of the design itself.

When software is architected using the open design concept, the review of the design itself will not result in the compromise of the safeguards in the software.

“The security of a mechanism should not depend on the secrecy of its design or implementation.”

If the details of the mechanism leaks then it is a catastrophic failure for all the users at once.

If the secrets are abstracted from the mechanism, e.g. inside a key, then leakage of a key affects only one user.

## Least Common Mechanism
The security principle of least common mechanisms disallows the sharing of mechanisms that are common to more than one user or process if the users and processes are at different levels of privilege. For example, the use of the same function to retrieve the bonus amount of an exempt employee and a non-exempt employee will not be allowed. In this case the calculation of the bonus is the common mechanism.

## Psychological acceptability
A security principle that aims at maximizing the usage and adoption of the security functionality in the software by ensuring that the security functionality is easy to use and at the same time transparent to the user. Ease of use and transparency are essential requirements for this security principle to be effective.

Security mechanisms should not make the resource more difficult to access than if the security mechanism were not present.

Problem: Users looks for ways to defeat the mechanisms and “prop the doors open”.

## Weakest Link
This security principle states that the resiliency of your software against hacker attempts will depend heavily on the protection of its weakest components, be it the code, service or an interface.

## Leveraging Existing Components
This is a security principle that focuses on ensuring that the attack surface is not increased and no new vulnerabilities are introduced by promoting the reuse of existing software components, code and functionality.


[1]: https://en.wikipedia.org/wiki/Compartmentalization_%28information_security%29
[2]: https://en.wikipedia.org/wiki/KISS_principle
