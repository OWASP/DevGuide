### 3.4 SecurityRAT

The [OWASP SecurityRAT][srat] (Requirement Automation Tool) is used to generate and manage security requirements
using information from the [OWASP ASVS][asvs] project.
It also provides an automated approach to requirements management
during development of frontend, server and mobile applications.

At present it is an OWASP Incubator project but it is likely to be upgraded soon to Laboratory status.

#### What is SecurityRAT?

SecurityRAT is a companion tool for the [ASVS][asvs] set of requirements;
it can be used to generate an initial set of requirements from the ASVS
and then keep track of the status and updates for these requirements.
It comes with [documentation and instructions][sratdocs] on how to install and run SecurityRAT.

To generate the initial list of requirements, SecurityRAT needs to be provided with three attributes defined by the ASVS:

* Application Security Verification Standard chapter ID - for example 'V2 - Authentication'
* Application Security Verification Level - the compliance level, for example 'L2'
* Authentication - whether Single sign-on (SSO) authentication is used or not

SecurityRAT then generates an initial list of recommended requirements.
This list can be stored in a SecurityRAT database which allows tracking and update of the set of requirements.
SecurityRAT also provides Atlassian JIRA integration for raising and tracking software issues.

The OWASP Spotlight series provides an overview of what Security Rat can do and how to use it:
'Project 5 - [OWASP SecurityRAT][spotlight05]'.

#### Why use it?

At the time of writing the ASVS has more than 280 suggested requirements for secure software development.
This number of requirements takes time to sort through and determine whether
they are applicable to a given development project or not.

The use of SecurityRAT to create a more manageable subset of the ASVS requirements is a direct benefit to both
security architects and the development team.
In addition SecurityRAT provides for the tracking and update of this set of requirements throughout the development cycle,
adding to the security of the application by helping to ensure security requirements are fulfilled.

#### How to use SecurityRAT

Install both Production and Development SecurityRAT applications by
downloading a release and installing on the Java Development Kit JDK11.
Alternatively download and run the [docker image][sratdocker] from DockerHub.
Configure SecurityRAT by referring to the [deployment documentation][sratdeploy]; this is not that straightforward
so to get started there is an [online demonstration][sratdemo] available.

Logging in to the demonstration site, using the credentials from the [project page][srat],
you are presented with defining a set of requirements or importing an existing set.
Assuming that we want a new set of requirements, give the requirements artifact a name and then
either select specific ASVS sections/chapters from the list:

* V1 - Architecture, Design and Threat Modeling
* V2 - Authentication
* V3 - Session Management
* V4 - Access Control
* V5 - * Validation, Sanitization and Encoding
* V6 - Stored Cryptography
* V7 - Error Handling and Logging
* V8 - Data Protection
* V9 - Communication
* V10 - Malicious Code
* V11 - Business Logic
* V12 - Files and Resources
* V13 - API and Web Service
* V14 - Configuration

or leave blank to include all verification requirements.

Select the level using the ASVS defined security compliance levels:

* Level 1 is for low assurance levels and is completely penetration testable
* Level 2 is for applications that contain sensitive data and is the recommended level for most applications
* Level 3 is for the most critical applications

Finally select whether SSO authentication is being used, and generate a list of requirements.
This requirements artifact is now stored in SecurityRAT ad can be retrieved in subsequent sessions.

SecurityRAT then presents an administration screen which allows tracking and editing of the ASVS verification requirements.
Refer to the [OWASP Spotlight on SecurityRAT][spotlight05] for an explanation of how to integrate with Atlassian JIRA.

#### What is SecurityCAT?

[SecurityCAT][scat] (Compliance Automation Tool) is an extension for SecurityRAT meant for automatic testing of requirements.
There is not an actual implementation of SecurityCAT,
SecurityRAT provides an API that allows for a compliance tool to be created.
and so this may be a future development for SecurityRAT.

#### References

* OWASP [SecurityRAT][srat]
* OWASP [SecurityRAT documentation][sratdocs]
* OWASP [SecurityCAT][scat]
* OWASP [Application Security Verification Standard][asvs] (ASVS)

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0504] or [edit on GitHub][edit0504].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[edit0504]: https://github.com/OWASP/DevGuide/blob/main/draft/05-requirements/04-security-rat.md
[issue0504]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-requirements/04-security-rat
[spotlight05]: https://youtu.be/HiaHXtzJ3DE
[scat]: https://securityrat.github.io/int_securitycat.html#securitycat
[srat]: https://owasp.org/www-project-securityrat/
[sratdemo]: https://securityrat.org/
[sratdeploy]: https://securityrat.github.io/depl_production.html
[sratdocker]: https://hub.docker.com/r/securityrat/securityrat
[sratdocs]: https://securityrat.github.io/
