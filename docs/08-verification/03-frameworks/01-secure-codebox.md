![SecureCodeBox logo](../../assets/images/logos/securecodebox.png "OWASP SecureCodeBox"){: height="180px" }

#### 6.3.1 secureCodeBox

OWASP [secureCodeBox][codebox] is a kubernetes based modularized toolchain
that provides continuous security scans of an organizations' projects and web applications.

The secureCodeBox [builder/tool project][codebox-project] is an OWASP Lab Project
and is installed using the [Helm ChartMuseum][codebox-repo].

#### What is secureCodeBox?

OWASP secureCodeBox combines existing security tools from the static analysis, dynamic analysis and network analysis domains.
It uses these tools to provide a comprehensive overview of threats and vulnerabilities
affecting an organization's network and applications.

OWASP secureCodeBox orchestrates a range of security-testing tools in various domains:

* Container analysis:
  * Trivy container vulnerability scanner
  * Trivy SBOM container dependency scanner

* Content Management System analysis:
  * CMSeeK detecting the Joomla CMS and its core vulnerabilities
  * Typo3Scan detecting the Typo3 CMS and its installed extensions
  * WPScan Wordpress vulnerability scanner

* Kubernetes analysis:
  * Kube Hunter vulnerability scanner
  * Kubeaudit configuration Scanner

* Network analysis:
  * Amass subdomain enumeration scanner
  * doggo DNS client
  * Ncrack network authentication bruteforcing
  * Nmap network discovery and security auditing
  * Whatweb website identification

* Repository analysis:
  * Git Repo Scanner discover Git repositories
  * Gitleaks find potential secrets in repositories
  * Semgrep static code analysis

* SSH/TLS configuration and policy scanning with SSH-audit and SSLyze

* Web Application analysis:
  * ffuf web server and web application elements and content discovery
  * Nikto web server vulnerability scanner
  * Nuclei template based vulnerability scanner.
  * Screenshooter takes screenshots of websites
  * ZAP Advanced web application & OpenAPI vulnerability scanner

Other tools may be added over time.

#### Why use it?

OWASP secureCodeBox provides the power of leading open source security testing tools with a multi-scanner platform.
This provides the ability to run routine scans continuously and automatically
on an organization's network infrastructure and applications.

OWASP secureCodeBox is fully scalable and can be separately configured for multiple teams, systems or clusters.

#### How to use it

OWASP secureCodeBox runs on [Kubernetes][kube] and uses [Helm][helm] to install using the [Helm ChartMuseum][codebox-repo].
There is an excellent '[Starting your First Scans][codebox-start]' guide to getting started with secureCodeBox,
with the rest of the [documentation][codebox-docs] providing clear information on configuring and running secureCodeBox.

#### References

* OWASP [secureCodeBox][codebox]
* [Kubernetes][kube] container orchestration
* [Helm][helm] package manager for Kubernetes

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue080301] or [edit on GitHub][edit080301].

[codebox]: https://www.securecodebox.io/
[codebox-project]: https://owasp.org/www-project-securecodebox/
[codebox-repo]: https://charts.securecodebox.io
[codebox-start]: https://www.securecodebox.io/docs/getting-started/first-scans
[codebox-docs]: https://www.securecodebox.io/docs/getting-started/installation
[edit080301]: https://github.com/OWASP/DevGuide/blob/main/draft/08-verification/03-frameworks/01-secure-codebox.md
[helm]: https://helm.sh/
[issue080301]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2008-verification/03-frameworks/01-secure-codebox
[kube]: https://kubernetes.io/
