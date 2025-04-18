### 7.1.4 Security Shepherd

OWASP Security Shepherd is a web and [mobile application security][csmas] training platform
that helps to foster and improve security awareness for development teams.

The Security Shepherd [tool project][sec-shep] is an OWASP Flagship Project
and can be downloaded from the project's [github repository][sec-shep-repo].

#### What is Security Shepherd?

Security Shepherd is a teaching tool that provides lessons and an environment
to learn how to attack both web and mobile applications.
This enables users to learn or to improve upon existing their manual penetration testing skills.

Security Shepherd is run on a web server such as Apache Tomcat and this can be installed manually.
There is also a pre-built virtual machine available or a docker image can be composed to run as a container.

#### Why use it?

Security Shepherd can train inexperienced pen-testers to security expert level by sharpening their testing skill-set.
Pen-testing is often included as a required stage in a organization's secure software development lifecycle (SDLC).

#### How to use it

Security Shepherd can be run as a Docker container, as a Virtual Machine or manually on top of a web server.

The Security Shepherd wiki has step by step installation instructions:

* either [compose the Docker image][sec-shep-docker] and run the container
* or download the [virtual machine][sec-shep-vm] and run on a hypervisor such as [Virtual Box][vbox]
* or [install on a Tomcat][sec-shep-tomcat] web server
* or [install on windows][sec-shep-windows] using a Tomcat web server

Once installed and logged in, the lessons and vulnerable applications are available to use.
Security Shepherd has modes which it can be used for different training goals:

* CTF (Capture the Flag) Mode
* Open Floor Mode
* Tournament Mode

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue090104] or [edit on GitHub][edit090104].

[csmas]: https://cheatsheetseries.owasp.org/cheatsheets/Mobile_Application_Security_Cheat_Sheet
[edit090104]: https://github.com/OWASP/DevGuide/blob/main/docs/09-training-education/01-vulnerable-apps/04-security-shepherd.md
[issue090104]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2009-training-education/01-vulnerable-apps/04-security-shepherd
[sec-shep]: https://owasp.org/www-project-security-shepherd/
[sec-shep-docker]: https://github.com/OWASP/SecurityShepherd/wiki/Docker-Environment-Setup
[sec-shep-repo]: https://github.com/OWASP/SecurityShepherd
[sec-shep-tomcat]: https://github.com/OWASP/SecurityShepherd/wiki/Manual-Shepherd-Setup
[sec-shep-vm]: https://github.com/OWASP/SecurityShepherd/wiki/Using-the-Shepherd-VM
[sec-shep-windows]: https://github.com/OWASP/SecurityShepherd/wiki/Manual-Shepherd-Set-Up-(Windows)
[vbox]: https://www.virtualbox.org/wiki/Downloads
