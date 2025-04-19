### 8.2.1 Security champions program

A Security Champion program is a commonly used way of helping development teams successfully run a development lifecycle
that is secure, and this is achieved by selecting members of teams to become Security Champions.
The role of Security Champion is described by the OWASP Software Assurance Maturity Model [(SAMM)][sammgegoc]
Organization and Culture activities within the Governance business function of the Education & Guidance practice.

#### Overview

It can be hard to introduce a security mindset across development teams using the application security team alone;
security engineers do not scale well across teams of developers - there is simply not enough of them.
A good way to scale security and distribute security across development teams is by creating a security champion role
and providing a Security Champions program to encourage a community spirit within the organization.
This will help foster a positive security culture within the organization,
see the [Security Culture project][culturechamps] on how this can be done with security champions.

Security champions are usually individuals within each development team that show special interest in application security.
The security champion provides a knowledgeable point of contact between the application security team and development,
and in addition they can ensure that the development lifecycle has security built in.
Often the security champion carries on with their original role within the development team, in addition to their new role,
and so a Security Champions program is important for providing support and training and avoiding burn-out.

#### Security champion role

Security champions are active members of a development team that act as the "voice" of security within their team.
Security champions also provide visibility of their team's security activities to the application security team,
and are seen as the first point of contact between developers and a central security team.

There is no universally defined role for a security champion, but the [Security Culture project][culturechamps]
provides various suggestions:

* Evangelize security: promoting security best practice in their team,
    imparting security knowledge and helping to uplift security awareness in their team
* Contribute to security standards: provide input into organizational security standards and procedures
* Help run activities: promote activities such as Capture the Flag events or secure coding training
* Oversee threat modeling: threat modeling consists of a security review on a product in the design phase
* Oversee secure code reviews: raise issues of risk in the code base that arise from peer group code reviews
* Use security testing tools: provide support to their team for the use of security testing tools

The security champion role requires a passion and interest in application security,
and so arbitrarily assigning this role is unlikely to work in practice.
A better strategy is to provide a security champions program, so that developers who are interested can come forward;
in effect they should self-select.

#### Security champions program

It can be tough being a security champion: usually they are still expected to do their 'day job' but in addition
they are expected to be knowledgeable on security matters and to take extra training.
Relying on good will and cheerful interest will only go so far, and a Security Champions program should be put in place
to identify, nurture, support and train the security champions.

The OWASP [Security Champions Guide][scguide] identifies ten key principles for a successful Security Champions program:

* Be passionate about security - identify the members of the teams that show interest in security
* Start with a clear vision for your program - be practical but ambitious, after if it works then it will work well
* Secure management support - as always, going it alone without management support is never going to work
* Nominate a dedicated captain - the program will take organization and maintaining, so find someone willing to do that
* Trust your champions - they are usually highly motivated when it comes to the security of their own applications
* Create a community - it can be lonely, so provide a support network
* Promote knowledge sharing - if the community is in place, then encourage discussions and meet-ups
* Reward responsibility - they are putting extra work, so appreciate them
* Invest in your champions - the knowledge gained through extra training will pay for itself many times over
* Anticipate personnel changes - the security champion may move on, be alert to this and plan for it

A successful security champions program will increase the security of the applications / systems, allay developer's fears,
increase the effectiveness of the application security team and improve the security posture of the organization as a whole.

#### References

* OWASP [Security Champions Guide][scguide]
* [Security Champions Playbook][scplaybook]
* OWASP [Security Culture][culturedoc] project

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue1021] or [edit on GitHub][edit1021].

[edit1021]: https://github.com/OWASP/DevGuide/blob/main/docs/08-culture-process/02-security-champions/01-security-champions-program.md
[issue1021]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2008-culture-process/02-security-champions/01-security-champions-program
[sammgegoc]: https://owaspsamm.org/model/governance/education-and-guidance/stream-b/
[scguide]: https://owasp.org/www-project-security-champions-guidebook/
[scplaybook]: https://github.com/c0rdis/security-champions-playbook
[culturechamps]: https://owasp.org/www-project-security-culture/stable/4-Security_Champions/
[culturedoc]: https://owasp.org/www-project-security-culture/stable/
