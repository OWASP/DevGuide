### 7.5 OWASP Top Ten project

The OWASP Top 10 is a standard awareness document for developers and web application security.
It represents a broad consensus about the most critical security risks to web applications.

The OWASP Top Ten is a flagship documentation project and is one of the very first OWASP projects.

#### What is the OWASP Top 10?

The OWASP [Top 10 Web Application Security Risks][top10project] project is probably the most well known security concept
within the security community, achieving wide spread acceptance and fame soon after its release in 2003.
Often referred to as just the 'OWASP Top Ten', it is a list that identifies the most important threats
to web applications and seeks to rank them in importance and severity.

The OWASP Top 10 is periodically revised to keep it up to date with the latest threat landscape.
The latest version was released in 2021 to mark twenty years of OWASP:

* [A01:2021-Broken Access Control][a01]
* [A02:2021-Cryptographic Failures][a02]
* [A03:2021-Injection][a03]
* [A04:2021-Insecure Design][a04]
* [A05:2021-Security Misconfiguration][a05]
* [A06:2021-Vulnerable and Outdated Components][a06]
* [A07:2021-Identification and Authentication Failures][a07]
* [A08:2021-Software and Data Integrity Failures][a08]
* [A09:2021-Security Logging and Monitoring Failures][a09]
* [A10:2021-Server-Side Request Forgery][a10]

The project itself is actively maintained by a project team.
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
making it one of (or even the most) longest lived OWASP project,
and since then has been in active and continuous development.
Listed below are the versions up to the latest in 2021, which was released to mark 20 years of OWASP.

* Original [2003](https://github.com/OWASP/Top10/blob/master/archives/OWASPWebApplicationSecurityTopTen-Version1.pdf)
* Update [2004](https://github.com/OWASP/Top10/blob/master/archives/OWASP_Top_Ten_2004.pdf)
* Update [2007](https://owasp.org/www-pdf-archive//OWASP_Top_10_2007.pdf)
* Release [2010](https://github.com/OWASP/OWASP-Top-10/tree/master/2010)
* Release [2013](https://github.com/OWASP/Top10/tree/master/2013)
* Release [2017](https://github.com/OWASP/Top10/tree/master/2017)
* Latest version [2021](https://github.com/OWASP/Top10/tree/master/2021)

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0905] or [edit on GitHub][edit0905].

[a01]: https://owasp.org/Top10/A01_2021-Broken_Access_Control/
[a02]: https://owasp.org/Top10/A02_2021-Cryptographic_Failures/
[a03]: https://owasp.org/Top10/A03_2021-Injection/
[a04]: https://owasp.org/Top10/A04_2021-Insecure_Design/
[a05]: https://owasp.org/Top10/A05_2021-Security_Misconfiguration/
[a06]: https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/
[a07]: https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/
[a08]: https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/
[a09]: https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/
[a10]: https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/
[edit0905]: https://github.com/OWASP/DevGuide/blob/main/draft/09-training-education/05-top-ten.md
[issue0905]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2009-training-education/05-top-ten
[spotlight10]: https://youtu.be/RMkoIrpz8ug
[top10project]: https://owasp.org/www-project-top-ten/
[top10data]: https://owasp.org/www-project-top-ten/#div-data_2020
