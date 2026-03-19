![Nettacker logo](../../../assets/images/logos/nettacker.png "OWASP Nettacker"){ align=right width=180 }

OWASP Nettacker is a command line utility for automated network and vulnerability scanning.
It can be used during penetration testing for both internal and external security assessments of networks.

The Nettacker [breaker/tool project][nettacker-project] is an OWASP Lab Project;
the latest version can be downloaded from the project's [github repository][nettacker-releases].

#### What is Nettacker?

[Nettacker][nettacker-project] is an automated scanning and penetration testing tool.
It is used to scan a network to discover nodes and servers on the network including subdomains.
Nettacker can then identify servers, services and port numbers in use.
This information can then be used to plan attacks or for auditing purposes.

Nettacker is a modular python application that that can be extended with other scanning functions.
The many modules available are grouped into domains:

* [Scan][nettacker-scan] modules for reconnaissance
* [Vulnerability][nettacker-vuln] modules that attempt specific exploits
* [Brute force][nettacker-brute] modules

Nettacker runs on Windows, Linux and MacOS.

#### Why use it?

Nettacker can be run from the command line, making it easy to use in scripts,
and also comes with a web browser interface for easy navigation of the results.
This makes it a quick and reliable way to gain information from a network.

Nettacker has multiple uses, it can be used for auditing purposes just as much as for penetration testing.

#### How to use it

The OWASP Spotlight series provides an overview of attack surface management using Nettacker:
'Project 11 - [Nettacker][spotlight11]'.

The documentation for Nettacker is provided in the repository wiki pages;
follow [these instructions][nettacker-install] to install it.

Nettacker is a flexible and modular scanning tool that can be used in many ways and with many options.
The best way to start using it is by following the [introduction video][nettacker-intro] and then taking it from there.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060204] or [edit on GitHub][edit060204].

[edit060204]: https://github.com/OWASP/DevGuide/blob/main/docs/en/06-verification/02-tools/04-nettacker.md
[issue060204]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/02-tools/04-nettacker
[nettacker-brute]: https://github.com/OWASP/Nettacker/wiki/Modules#brute-modules
[nettacker-install]: https://github.com/OWASP/Nettacker/wiki/Installation
[nettacker-intro]: https://github.com/OWASP/Nettacker/wiki#introduction
[nettacker-project]: https://owasp.org/www-project-nettacker/
[nettacker-releases]: https://github.com/OWASP/Nettacker/releases/latest/
[nettacker-scan]: https://github.com/OWASP/Nettacker/wiki/Modules#scan-modules
[nettacker-vuln]: https://github.com/OWASP/Nettacker/wiki/Modules#vuln-modules
[spotlight11]: https://www.youtube.com/watch?v=OGv7OtG127A
