![OWTF logo](../../../assets/images/logos/owtf.png "OWASP OWTF"){ align=right width=80 }

OWASP Offensive Web Testing Framework ([OWTF][owtf]) is a penetration test tool
that provides pen-testers with a framework for organizing and running security test suites.
It also helps align the pen-testing to various standards and security guides,
allowing the testing to be more creative and comprehensive.

The OWTF defender/tool project is an OWASP Flagship Project
and can be downloaded from the project's github repository [release area][owtfdownload].

#### What is OWTF?

The [OWTF][owtf]tool is a penetration test framework used to organize and run suites of security and pen-testing tools.
It is designed to be run on [Kali Linux][kali]; it can also be run on MacOS but with some modification of scripts and paths.

OWTF is very much a penetration tester's tool; there is an expectation that the
user has a reasonable expertise and grasp of penetration testing environments and tools.
The [documentation][owtfdocs] on installing and running OWTF requires is not extensive,
and some in-depth knowledge on the target system is required to configure the tool.

#### Why use it?

[OWTF][owtf] is easily configurable and plugins can be created or new tests added using the configuration files.
It can be quickly installed on [Kali Linux][kali], a distribution of Ubuntu that is widely used by pen-testers,
and allows for a whole suite of tests to be directed against the target.

#### How to use it

The OWTF [documentation][owtfdocs] is relatively old, last updated in 2016,
and  the [install][owtfinstall] instructions may need adapting to run on MacOS or Kali.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue080203] or [edit on GitHub][edit080203].

[edit080203]: https://github.com/OWASP/DevGuide/blob/main/docs/06-verification/02-tools/03-owtf.md
[issue080203]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/02-tools/03-owtf
[kali]: https://www.kali.org/
[owtfinstall]: https://owtf.readthedocs.io/en/develop/installation/methods.html
[owtfdocs]: https://owtf.readthedocs.io/
[owtfdownload]: https://github.com/owtf/owtf/releases
[owtf]: https://owasp.org/www-project-owtf/
