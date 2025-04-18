### 9.3 ModSecurity WAF

[ModSecurity][modsec] is an open source Web Application Firewall (WAF) widely deployed on web servers
that has been in continuous development and widespread use since 2002.

In 2024 it became an OWASP Production project, supported by the existing leadership and contributors.

#### What is ModSecurity?

In January 2024 the [ModSecurity][modsec] Web Application Firewall project was [adopted by OWASP][modsec-press],
previously [TrustWave][trustwave] had been the custodian of this project.
ModSecurity itself has a long history as an open source project, the first release was in November 2002,
and is widely used as a web application firewall for [cloud applications][cscloud] and on-premises web servers.

The ModSecurity WAF needs to be configured in operational deployments,
and this can be done using the OWASP [CRS][crs].

#### Why use ModSecurity?

Web Application Firewalls are often the first line of defense against HTTP attacks on web applications and servers.
The ModSecurity WAF is widely used for this purpose along with the [Coraza WAF][coraza], also provided by OWASP.

#### How to use ModSecurity

ModSecurity is a Web Application Firewall, which scans the incoming and outgoing HTTP traffic to a web server.
The ModSecurity WAF is deployed as a proxy server in front of a web application,
or deployed within the web server itself, to provide protection against HTTP attacks.

The rules applied to the HTTP traffic are provided as configuration to ModSecurity,
and these rules allow many different actions to be applied such as blocking traffic, redirecting requests, and many more.
See the documentation for [deploying and running][modsec-docs] ModSecurity,
along with the documentation on configuring ModSecurity with the [CRS][crs].

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue1103] or [edit on GitHub][edit1103].

[coraza]: https://coraza.io/
[crs]: https://coreruleset.org/
[cscloud]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Cloud_Architecture_Cheat_Sheet
[edit1103]: https://github.com/OWASP/DevGuide/blob/main/docs/11-operations/03-modsecurity.md
[issue1103]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2011-operations/03-modsecurity
[modsec]: https://owasp.org/www-project-modsecurity/
[modsec-docs]: https://www.modsecurity.org/
[modsec-press]: https://owasp.org/blog/2024/01/09/ModSecurity.html
[trustwave]: https://www.trustwave.com/
