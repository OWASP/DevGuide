![Developer guide logo](../assets/images/dg_logo.png "OWASP Developer Guide"){: style="height:180px;float:right" }

## 10. Metrics

Metrics are important in an organization for various reasons, and in software security they can be used to:

* measure the effectiveness of security controls
* determine security posture
* provide justification for security programs
* and others

At present the OWASP [Integration Standards project Application Wayfinder][intstand] project
does not identify any OWASP projects that gather or process metrics; this may change in the future.

### Strategy and Metrics

The software security program is foundational to the strategic planning an organizations security posture.
Metrics keep track of the security activities within the plan and provide the information for gap analysis.

The [Software Assurance Maturity Model][samm] (SAMM) provides descriptions and definitions
for the [Strategy and Metrics][sammgsm] business practices within the [Governance][sammg] business function.
It provides two streams for achieving organizational maturity:

* [Create and Promote][sammgsma]
  which concerns the risks identified with the organization and what level of risk is acceptable
* [Measure and Improve][sammgsmb] which describes monitoring the security strategy through metrics

The categories of metrics suggested by SAMM are :

* Effort metrics: the effort spent on security
* Result metrics: the results of security efforts
* Environment metrics: the environment where security efforts take place

There are other metrics, perhaps specific to an individual organization, that can also be collected and acted on.
The [Security Culture][culturemetrics] project provides various examples of metrics that can be considered.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing then [submit an issue][issue1200].

[culturemetrics]: https://owasp.org/www-project-security-culture/stable/8-Metrics/
[issue1200]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2012-metrics/00-toc
[samm]: https://owaspsamm.org/about/
[sammg]: https://owaspsamm.org/model/governance/
[sammgsm]: https://owaspsamm.org/model/governance/strategy-and-metrics/
[sammgsma]: https://owaspsamm.org/model/governance/strategy-and-metrics/stream-a/
[sammgsmb]: https://owaspsamm.org/model/governance/strategy-and-metrics/stream-b/
[intstand]: https://owasp.org/www-project-integration-standards/
