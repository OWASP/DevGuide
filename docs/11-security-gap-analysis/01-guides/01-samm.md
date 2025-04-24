![SAMM logo](../../assets/images/logos/samm.png "OWASP SAMM"){ align=right width=250 }

The [Software Assurance Maturity Model][samm] (SAMM) project provides an effective and measurable way for
an organization to analyze their secure development lifecycle, and identify any gaps or improvements.
SAMM is one of the OWASP's flagship projects, and can be downloaded from the [SAMM project site][samm-project].

#### What is SAMM?

SAMM is regarded as the prime maturity model for software assurance.
SAMM provides an effective and measurable way for all types of organizations to analyze and improve
their software security posture.
SAMM supports the complete secure software development lifecycle and is technology and process agnostic.

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

These give the security activities expected at each maturity level, and provide input to the gap analysis.

#### How to use it

The OWASP Spotlight series provides an overview of using the SAMM:
'Project 9 - [Software Assurance Maturity Model (SAMM)][spotlight09]'.

Security gap analysis can benefit from an assessment which measures the quality of the software assurance maturity process.
The [SAMM Assessment][samma] tools include spreadsheets and online tools such as [SAMMwise][sammwise] and [SAMMY][sammy].

The SAMM model describes these fundamentals of software security, which it calls Business Functions.
Each of these five fundamentals are further split into three Business Practices:

| Business Function       | Business Practices                 |                                        |        |
| ----------------------- | ---------------------------------- | -------------------------------------- | ------ |
| [Governance][sammg]     | [Strategy and Metrics][sammgsm]    | [Policy and Compliance][sammgpc]       | [Education and Guidance][sammgeg] |
| [Design][sammd]         | [Threat Assessment][sammdta]       | [Security Requirements][sammdsr]       | [Secure Architecture][sammdsa]    |
| [Implementation][sammi] | [Secure Build][sammisb]            | [Secure Deployment][sammisd]           | [Defect Management][sammidm]      |
| [Verification][sammv]   | [Architecture Assessment][sammvaa] | [Requirements-driven Testing][sammvrt] | [Security Testing][sammvst]       |
| [Operations][sammo]     | [Incident Management][sammoim]     | [Environment Management][sammoem]      | [Operational Management][sammoom] |

Each Business Practice is further subdivided into two streams which provide different objectives for the same practice.

#### References

* OWASP [Software Assurance Maturity Model][samm] (SAMM)
* [SAMMY][sammy] management tool
* OWASP [SAMM project][samm-project]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue130101] or [edit on GitHub][edit130101].

[edit130101]: https://github.com/OWASP/DevGuide/blob/main/docs/11-security-gap-analysis/01-guides/01-samm.md
[issue130101]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2011-security-gap-analysis/01-guides/01-samm
[samm]: https://owaspsamm.org/about/
[samma]: https://owaspsamm.org/assessment/
[sammd]: https://owaspsamm.org/model/design/
[sammdsa]: https://owaspsamm.org/model/design/secure-architecture/
[sammdsr]: https://owaspsamm.org/model/design/security-requirements/
[sammdta]: https://owaspsamm.org/model/design/threat-assessment/
[sammg]: https://owaspsamm.org/model/governance/
[sammgeg]: https://owaspsamm.org/model/governance/education-and-guidance/
[sammgpc]: https://owaspsamm.org/model/governance/policy-and-compliance/
[sammgsm]: https://owaspsamm.org/model/governance/strategy-and-metrics/
[sammi]: https://owaspsamm.org/model/implementation/
[sammidm]: https://owaspsamm.org/model/implementation/defect-management/
[sammisb]: https://owaspsamm.org/model/implementation/secure-build/
[sammisd]: https://owaspsamm.org/model/implementation/secure-deployment/
[sammo]: https://owaspsamm.org/model/operations/
[sammoem]: https://owaspsamm.org/model/operations/environment-management/
[sammoim]: https://owaspsamm.org/model/operations/incident-management
[sammoom]: https://owaspsamm.org/model/operations/operational-management/
[sammv]: https://owaspsamm.org/model/verification/
[sammvaa]: https://owaspsamm.org/model/verification/architecture-assessment/
[sammvrt]: https://owaspsamm.org/model/verification/requirements-driven-testing/
[sammvst]: https://owaspsamm.org/model/verification/security-testing/
[samm-project]: https://owasp.org/www-project-samm/
[sammwise]: https://github.com/owaspsamm/sammwise
[sammy]: https://sammy.codific.com/
[spotlight09]: https://youtu.be/N0zcZnkH5Wg
