![SAMM logo](../../assets/images/logos/samm.png "OWASP SAMM"){ align=right width=250 }

The [Software Assurance Maturity Model][samm] (SAMM) project provides an effective and measurable way for
an organization to analyze and improve their secure development lifecycle processes.
SAMM is one of the OWASP's flagship projects, and can be downloaded from the [SAMM project site][samm-project].

#### What is SAMM?

SAMM can be regarded as the prime maturity model for software assurance.
SAMM provides an effective and measurable way for all types of organizations to analyze and improve
their software security posture.
SAMM supports the entire secure software development lifecycle and is technology and process agnostic.

The SAMM model is hierarchical. At the highest level SAMM defines five business functions;
activities that software development must fulfill to some degree:

* [Governance][sammg]
* [Design][sammd]
* [Implementation][sammi]
* [Verification][sammv]
* [Operations][sammo]

Each business function in turn has three security practices,
which are areas of security-related activities that build assurance for the related business function.

Security practices have activities, grouped in logical flows and divided into two streams (A and B).
Streams cover different aspects of a practice and have their own objectives,
aligning and linking the activities in the practice over the different maturity levels.

For each security practice, SAMM defines three maturity levels which generalize to foundational, mature and advanced.
Each level has a successively more sophisticated objective with specific activities, and more strict success metrics.

#### Why use it?

The structure and setup of the SAMM model support:

* assessment of the organization’s current software security posture
* definition of the organization’s targets
* definition of an implementation roadmap to get there
* prescriptive advice on how to implement particular activities

These provide suggestions for improving processes and building security practices into the culture of the organization.

#### How to use it

The OWASP Spotlight series provides an overview of using the SAMM to guide development:
'Project 9 - [Software Assurance Maturity Model (SAMM)][spotlight09]'.

The [SAMM Fundamentals Course][sammfun] provides training on the high level SAMM Business Functions
and provides guidance on each Security Practice.
The SAMM [assessment tools][samma] measure the quality of an organization's software assurance maturity process,
which can be used as feedback into the culture of the organization.

#### References

* OWASP [Software Assurance Maturity Model][samm] (SAMM)
* [SAMMY][sammy] management tool
* OWASP [SAMM project][samm-project]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue1003] or [edit on GitHub][edit1003].

[edit1003]: https://github.com/OWASP/DevGuide/blob/main/docs/08-culture-process/03-samm.md
[issue1003]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2008-culture-process/03-samm
[samm]: https://owaspsamm.org/about/
[samma]: https://owaspsamm.org/assessment/
[sammd]: https://owaspsamm.org/model/design/
[sammfun]: https://owaspsamm.thinkific.com/courses/samm
[sammg]: https://owaspsamm.org/model/governance/
[sammi]: https://owaspsamm.org/model/implementation/
[sammo]: https://owaspsamm.org/model/operations/
[sammv]: https://owaspsamm.org/model/verification/
[samm-project]: https://owasp.org/www-project-samm/
[sammy]: https://sammy.codific.com/
[spotlight09]: https://youtu.be/N0zcZnkH5Wg
