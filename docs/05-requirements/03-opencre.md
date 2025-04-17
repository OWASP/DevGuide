![OpenCRE logo](../assets/images/logos/opencre.png "OWASP OpenCRE"){: height="180px" }

### 3.3 OpenCRE

The [Open Common Requirement Enumeration][opencre] (OpenCRE) is a catalog of security requirements:
enumerating security topics and providing links to various standards, cheat sheets and guides.

The OWASP [Integration Standards][intstand] project includes both the OpenCRE and Security
and the Application Security Wayfinder, it is an OWASP documentation project with production status.

#### What is the Integration Standards project?

The [Integration Standards][intstand] project is at the center of the OWASP project community;
it provides guidance on how to navigate and use the many projects within OWASP.
It does this in two ways, first is the [Application Security Wayfinder][intstand] which provides a visual map
of the most important OWASP projects - as of August 2024 there are 345 [OWASP projects][projects]
so this is a really useful visualization.
The second is the Open Common Requirement Enumeration ([OpenCRE][opencre]) which provides a consolidated reference of
standards, cheat sheets, tools and other enumerations (such as [CWE][cwe]).

The Integration Standards project has also produced OWASP [Application Security Fragmentation][sdlc]
write-up on OWASP and the secure Software Development LifeCycle (SDLC).
This provides an overview of tools and techniques used for most SDLCs.

#### What is OpenCRE?

[OpenCRE][opencre] is a catalog, or enumeration, of various standards and reference material, including:

* [CAPEC][capecocre]
* [CWE][cweocre]
* [NIST Special Publications][nist] [800-53][nist53] and [800-63][nist63]
* OWASP [ASVS][asvs]
* OWASP [Top10][top10ocre]
* OWASP [Proactive Controls][proactiveocre]
* OWASP [Cheat Sheets][csocre]
* OWASP [WSTG][wstgocre]
* [ZAP][zapocre]

The aim of this project is to 'Link all the things with OpenCRE' which will:

* make it easier for engineers, security officers, testers and procurement to find relevant information
* make it easier for standards makers to create and maintain references

#### Why use OpenCRE?

OpenCRE: 'Everything organized'

[OpenCRE][opencre] is a powerful tool that can provide developers with links to many resources, and is easy to use.
It provides a one-stop consolidated set of references on various security terms and domains,
and crucially these are automatically kept up to date.
The provides a handy security catalog that can be searched for various standards or security terms.

As well as being useful for day to day security questions,
the OpenCRE can also be used as the reference section in documentation;
linking across to the OpenCRE rather than providing a list of references means the links are kept up to date automatically.

#### How to use OpenCRE

The [OpenCRE][opencre] catalog can be accessed in traditional ways such as using searches or linking across to it.
For example OpenCRE references to the Common Weakness Enumeration can be accessed using the [search facility][cweocre]
or by linking across directly to a [specific Open Common Requirement][cwe1002].

OpenCRE is also useful when providing references in documentation.
OpenCRE can be used for these references instead of listing various references to a security concept or requirement.
This will provide links to standards, cheat sheets, tools and other enumerations -
along with other sources that have been added over time - and all kept up to date.
So no more broken links or referring to out of date versions :)

This is now the age of large language models, and OpenCRE has embraced this technology.
Immediate answers to security questions or searches can be provided by [OpenCRE Chat][opencrechat].

For example, in answer to the question "_what use is the OWASP Developer Guide?_"
OpenCRE Chat provides the agreeable answer:

_"The OWASP Developer Guide provides a comprehensive overview of application security risks and how to mitigate them._
_It covers topics such as input validation, output encoding, secure coding practices, and secure design principles._
_The guide is a valuable resource for developers who want to create secure applications."_

#### References

* OWASP [OpenCRE][opencre]
* [Spotlight on OpenCRE][spotlight28]
* OWASP [Application Security Fragmentation][sdlc]
* OWASP [Integration Standards][intstand] project
* [Understanding the Complete Chain of Application Security Using OpenCRE org][opencretalk]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0503] or [edit on GitHub][edit0503].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[capecocre]: https://opencre.org/search/CAPEC
[csocre]: https://opencre.org/search/OWASP%20Cheat%20Sheets
[cweocre]: https://opencre.org/search/CWE
[cwe]: https://cwe.mitre.org/
[cwe1002]: https://www.opencre.org/node/standard/CWE/sectionid/1002
[edit0503]: https://github.com/OWASP/www-project-developer-guide/blob/main/draft/05-requirements/03-opencre.md
[intstand]: https://owasp.org/www-project-integration-standards/
[issue0503]: https://github.com/OWASP/www-project-developer-guide/issues/new?labels=content&template=request.md&title=Update:%2005-requirements/03-opencre
[nist]: https://csrc.nist.gov/
[nist53]: https://www.nist.gov/privacy-framework/nist-privacy-framework-and-cybersecurity-framework-nist-special-publication-800-53
[nist63]: https://pages.nist.gov/800-63-3/
[opencre]: https://www.opencre.org/
[opencrechat]: https://www.opencre.org/chatbot
[opencretalk]: https://www.youtube.com/watch?v=VPOkT9quve0
[proactiveocre]: https://www.opencre.org/search/Proactive%20Controls
[projects]: https://owasp.org/projects/
[sdlc]: https://owasp.org/www-project-integration-standards/writeups/owasp_in_sdlc/
[spotlight28]: https://www.youtube.com/watch?v=TwNroVARmB0&list=PLUKo5k_oSrfOTl27gUmk2o-NBKvkTGw0T
[top10ocre]: https://www.opencre.org/search/OWASP%20Top%2010
[wstgocre]: https://opencre.org/search/WSTG
[zapocre]: https://opencre.org/search/ZAP
