![Developer guide logo](../assets/images/dg_logo.png "OWASP Developer Guide"){ align=right width=180 }

Operations are those activities necessary to ensure that confidentiality, integrity, and availability
are maintained throughout the operational lifetime of an application and its associated data.
The aim of Operations is to provide greater assurance that the organization is resilient
in the face of operational disruptions, and responsive to changes in the operational landscape.
This is described by the [Operations][sammo] business function in the OWASP [SAMM model][samm].

Operations generally cover the security practices:

* [Incident Management][sammoim] of security breaches and incidents
* [Environment Management][sammoem] such as configuration hardening, patching and updating
* [Operational Management][sammoom] which includes data protection and system / legacy management

OWASP projects provide the CRS that is used for both Coraza and ModSecurity web application firewalls,
which are widely used for data and system management.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing then [submit an issue][issue1100].

[issue1100]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2009-operations/00-toc
[samm]: https://owaspsamm.org/about/
[sammo]: https://owaspsamm.org/model/operations/
[sammoem]: https://owaspsamm.org/model/operations/environment-management/
[sammoim]: https://owaspsamm.org/model/operations/incident-management
[sammoom]: https://owaspsamm.org/model/operations/operational-management/
