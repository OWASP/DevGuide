The OWASP [DevSecOps Guideline][devsecops] project explains how to best implement a secure pipeline,
using best practices and introducing automation tools to help 'shift-left' security issues.

The DevSecOps Guideline is in active development as an OWASP Production documentation project
and can be accessed from the [web document][dsodoc] or [downloaded as a PDF][dsopdf].

#### What is the DevSecOps Guideline?

The DevOps (combining software Development and release Operations) pipelines use automation to integrate
various established activities within the development and release processes into pipeline steps.
This enables the use of Continuous integration / Continuous Delivery/Deployment (CI/CD) within an organization.
DevSecOps (combining security with DevOps) seeks to add steps into the existing CI/CD pipelines to build security
into the development and release process.

The [DevSecOps Guideline][devsecops] is a collection of advice and theory that explains how to embed security into DevOps.
It covers various foundational topics such as Threat Modeling pipelines, Secrets Management and Linting Code.
It then explains and illustrates various vulnerability scanning steps commonly used in [CI/CD pipelines][cscicd] :

* Static Application Security Testing ([SAST][dsosast])
* Dynamic Application Security Testing ([DAST][dsodast])
* Interactive Application Security Testing ([IAST][dsoiast])
* Software Composition Analysis ([SCA][dsosca])
* [Infrastructure Vulnerability Scanning][dsoivs]
* [Container Vulnerability Scanning][dsocvs]

The DevSecOps Guideline is a concise guide that provides the foundational knowledge to implement DevSecOps.

#### How to use the DevSecOps Guideline

The DevSecOps Guideline is document can be accessed from the [web document][dsodoc] or [downloaded as a PDF][dsopdf].
It is concise enough that all the sections can be read within a short time, and it provides enough knowledge
to understand the concept behind DevSecOps and what activities are involved.

It provides an [excellent overview][dsointro] of DevSecOps which shows how the steps of a typical CI/CD pipeline
fit together and what sort of tools can be applied in each step to secure the pipeline.
Many of the pages in the DevSecOps Guideline contain lists of tools that can be applied to the pipeline step.

The DevSecOps Guideline document is in the process of [being expanded and updated][dsonew] which will build on the
existing 2023 version.

#### References

* OWASP [DevSecOps Guideline][devsecops] project
* OWASP [CI/CD Security Cheat Sheet][cscicd]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue1101] or [edit on GitHub][edit1101].

[cscicd]: https://cheatsheetseries.owasp.org/cheatsheets/CI_CD_Security_Cheat_Sheet
[devsecops]: https://owasp.org/www-project-devsecops-guideline/
[dsocvs]: https://owasp.org/www-project-devsecops-guideline/latest/02f-Container-Vulnerability-Scanning
[dsodoc]: https://owasp.org/www-project-devsecops-guideline/latest/
[dsodast]: https://owasp.org/www-project-devsecops-guideline/latest/02b-Dynamic-Application-Security-Testing
[dsoiast]: https://owasp.org/www-project-devsecops-guideline/latest/02c-Interactive-Application-Security-Testing
[dsointro]: https://owasp.org/www-project-devsecops-guideline/latest/index
[dsoivs]: https://owasp.org/www-project-devsecops-guideline/latest/02e-Infrastructure-Vulnerability-Scanning
[dsonew]: https://github.com/OWASP/DevSecOpsGuideline/tree/master/current-version
[dsopdf]: https://github.com/OWASP/DevSecOpsGuideline/releases
[dsosast]: https://owasp.org/www-project-devsecops-guideline/latest/02a-Static-Application-Security-Testing
[dsosca]: https://owasp.org/www-project-devsecops-guideline/latest/02d-Software-Composition-Analysis
[edit1101]: https://github.com/OWASP/DevGuide/blob/main/docs/en/09-operations/01-devsecops.md
[issue1101]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2009-operations/01-devsecops
