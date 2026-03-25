![Top 10 logo](../../assets/images/logos/top10.png "OWASP Top 10"){ align=right width=180 }

The OWASP Top 10 is a standard awareness document for developers and web application security.
It represents a broad consensus about the most critical security risks to web applications.

The OWASP Top Ten is a flagship documentation project and is one of the very first OWASP projects.
It is actively maintained by a dedicated project team.

#### What is the OWASP Top 10?

The OWASP [Top 10 Web Application Security Risks][top10project] project is probably the most well known security concept
within the security community, achieving wide spread acceptance and fame soon after its release in 2003.
Often referred to as just the 'OWASP Top Ten', it is a list that identifies the most important threats
to web applications and seeks to rank them in importance and severity.

* [A01:2025][a01] Broken Access Control
* [A02:2025][a02] Security Misconfiguration
* [A03:2025][a03] Software Supply Chain Failures
* [A04:2025][a04] Cryptographic Failures
* [A05:2025][a05] Injection
* [A06:2025][a06] Insecure Design
* [A07:2025][a07] Authentication Failures
* [A08:2025][a08] Software or Data Integrity Failures
* [A09:2025][a09] Security Logging and Alerting Failures
* [A10:2025][a10] Mishandling of Exceptional Conditions

The list is [based on data][top10data] collected from identified application vulnerabilities and from a variety of sources;
security vendors and consultancies, bug bounties, along with company/organizational contributions.
The data is normalized to allow for level comparison between 'Human assisted Tooling and Tooling assisted Humans'.

#### How to use it

The OWASP Top 10 has various uses that are foundational to application security:

* as a training aid on the most common web application vulnerabilities
* as a starting point when testing web applications
* to raise awareness of vulnerabilities in applications in general
* as a set of demonstration topics

There is not one way to use this documentation project; use it in any way that promotes application security.
The OWASP Spotlight series provides an overview of the Top Ten: 'Project 10 - [Top10][spotlight10]'.

#### OWASP Top 10 versions

The OWASP Top 10 Web Application Security Risks document was originally published in 2003,
making it one of (or even the most) longest lived OWASP project.

The project is periodically revised to keep it up to date with the latest threat landscape.
Listed are the versions up to the latest in 2025:

* Original [2003](https://github.com/OWASP/Top10/blob/master/2003/OWASPWebApplicationSecurityTopTen-Version1.pdf)
* Update [2004](https://github.com/OWASP/Top10/blob/master/2004/OWASP_Top_Ten_2004.pdf)
* Update [2007](https://github.com/OWASP/Top10/blob/master/2007/OWASP%20Top%2010%202007.pdf)
* Release [2010](https://github.com/OWASP/Top10/tree/master/2010)
* Release [2013](https://github.com/OWASP/Top10/tree/master/2013)
* Release [2017](https://github.com/OWASP/Top10/tree/master/2017)
* Release [2021](https://github.com/OWASP/Top10/tree/master/2021)
* Latest version [2025](https://github.com/OWASP/Top10/tree/master/2025)

The 2021 version of the OWASP Top Ten was released to mark 20 years of OWASP.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0905] or [edit on GitHub][edit0905].

[a01]: https://owasp.org/Top10/2025/A01_2025-Broken_Access_Control/
[a02]: https://owasp.org/Top10/2025/A02_2025-Security_Misconfiguration/
[a03]: https://owasp.org/Top10/2025/A03_2025-Software_Supply_Chain_Failures/
[a04]: https://owasp.org/Top10/2025/A04_2025-Cryptographic_Failures/
[a05]: https://owasp.org/Top10/2025/A05_2025-Injection/
[a06]: https://owasp.org/Top10/2025/A06_2025-Insecure_Design/
[a07]: https://owasp.org/Top10/2025/A07_2025-Authentication_Failures/
[a08]: https://owasp.org/Top10/2025/A08_2025-Software_or_Data_Integrity_Failures/
[a09]: https://owasp.org/Top10/2025/A09_2025-Security_Logging_and_Alerting_Failures/
[a10]: https://owasp.org/Top10/2025/A10_2025-Mishandling_of_Exceptional_Conditions/
[edit0905]: https://github.com/OWASP/DevGuide/blob/main/docs/en/07-training-education/05-top-ten.md
[issue0905]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2007-training-education/05-top-ten
[spotlight10]: https://youtu.be/RMkoIrpz8ug
[top10project]: https://owasp.org/www-project-top-ten/
[top10data]: https://owasp.org/www-project-top-ten/#div-data_2020
