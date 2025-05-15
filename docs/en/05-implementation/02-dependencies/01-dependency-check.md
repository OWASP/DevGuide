![DepCheck logo](../../../assets/images/logos/depcheck.png "OWASP Dependency-Check"){ width=250 }

OWASP [Dependency-Check][depcheck] is a tool that provides Software Composition Analysis (SCA) from the command line.
It identifies the third party libraries in a web application project
and checks if these libraries are vulnerable using the [NVD database][nist-db].

Dependency-Check is an OWASP Flagship project and can be downloaded from the [github releases][depcheck-download] area.
Dependency-Check was started in September 2012 and since then has been continuously supported with regular releases.

#### What is Dependency-Check?

Dependency-Check is a Software Composition Analysis (SCA) tool that attempts to detect
publicly disclosed vulnerabilities contained within a project’s dependencies.
It does this by determining if there is a [Common Platform Enumeration][cpe] (CPE) identifier for a given dependency.

The core engine contains a series of analyzers that inspect the project dependencies
and identify the CPE for the given dependency.
If a CPE is identified then it is cross referenced to the [NIST CVE database][nist-db]
and any associated [Common Vulnerability and Exposure][cve] (CVE) entries are listed in the report.

Dependency-Check's core analysis engine can be used as:

* an Ant Task
* a Command Line Tool
* Gradle Plugin
* Jenkins Plugin
* Maven Plugin
* SBT Plugin

#### Why use it?

Checking for vulnerable components, '[A06 Vulnerable and Outdated Components][a06]', is in the OWASP Top Ten
and is one of the most straight-forward and effective security activities to implement.
The Dependency-Check tool provides checks for vulnerable components that can be run from the command line.

This is useful for development teams; the ability to check for vulnerable application components from the command line
gives immediate feedback to the developer without having to wait for a pipeline to run.

Dependency-Check also provides plugins to check for vulnerable components for [CI/CD pipelines][cscicd].

#### How to use it

The OWASP Spotlight series provides an example of the risks involved in using out of date and vulnerable libraries,
and how to use Dependency-Check: 'Project 2 - [OWASP Dependency Check][spotlight02]'.

Refer to the Dependency-Check [documentation][depcheck-docs] to get started running from the command line:

* ensure Java is installed, for example from [Eclipse Adoptium][adoptium]
* download and unzip the latest Dependency-Check [release][depcheck-download]
* navigate to the Dependency-Check 'bin' directory and run, using threat Dragon as an example:
  `./dependency-check.sh --project "Threat Dragon" --scan ~/github/threat-dragon`
* open the html output file and act on the findings

The command line is useful for immediate debugging development.
Depending on what automation environment is in place a plugin can also be installed
into a pipeline which can then generate the SCA reports.

#### References

* OWASP [Dependency-Check][depcheck] project
* OWASP [Dependency-Check][depcheck-docs] documentation
* OWASP [CI/CD Security Cheat Sheet][cscicd]
* OWASP [Top 10][a06]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue070201] or [edit on GitHub][edit070201].

[a06]: https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/
[adoptium]: https://adoptium.net/
[cpe]: https://nvd.nist.gov/products/cpe
[cscicd]: https://cheatsheetseries.owasp.org/cheatsheets/CI_CD_Security_Cheat_Sheet
[cve]: https://cve.mitre.org/
[depcheck]: https://owasp.org/www-project-dependency-check/
[depcheck-docs]: https://jeremylong.github.io/DependencyCheck/
[depcheck-download]: https://github.com/jeremylong/DependencyCheck/releases
[edit070201]: https://github.com/OWASP/DevGuide/blob/main/docs/05-implementation/02-dependencies/01-dependency-check.md
[issue070201]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/02-dependencies/01-dependency-check
[nist-db]: https://nvd.nist.gov/
[spotlight02]: https://youtu.be/YAXf3TaAYeA
