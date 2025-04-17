### 8.1 Security Culture

Most organizations have an application development lifecycle in place with security activities built into it,
this goes a long way to reducing the security issues present in applications and systems.
The OWASP [Security Culture project][culture] is a guide that considers security
at each stage of the application security development lifecycle,
with the aim of creating and nurturing secure development practices throughout the lifecycle.

The Security Culture guide is an [OWASP incubator project][culturerepo]
and the latest stable version is available as a [web document][culturedoc].

#### What is the OWASP Security Culture project

The OWASP [Security Culture project][culture] is a collection of explanations and practical advice
arranged under various topic headings.

* [Why add security][culturewhy] in development teams
* [Setting maturity goals][culturegoal]
* [Security team collaboration][culturegoal]
* [Security champions][culturechamps]
* [Activities][cultureacts]
* [Threat modeling][culturetm]
* [Security testing][culturetest]
* [Security related metrics][culturemetrics]

The OWASP Security Culture project is focused on establishing/persisting
a positive security posture within the application development lifecycle
and references other OWASP projects in a similar way to the OWASP Developer Guide.

#### Encouraging a Security Culture

The philosophy of a security culture is as important as the technical aspects;
the application development teams need to be onboard to adopt a good security posture.
The Security Culture project recognizes this and devotes a [section][culturewhy] to the importance
of building security into the development lifecycle.

As well as onboard development teams there has to be buy-in from the higher management:
without this any security champion program is certain to fail and the security culture of the organization will suffer.
The Security Culture project provides information on [goals, metrics and maturity models][culturegoal]
that are a necessary prerequisite for management approval of security activities.
In addition the Security Culture project highlights the importance of security teams,
management and development teams all working together - all are necessary for a good security culture.

Security Champions are an important way of encouraging security within an organization - an organization can have a
healthy security culture without security champions but it is a lot easier with a security champion program in place.
Selecting and nurturing [security champions][culturechamps] has to be tailored to the individual organization,
no security champion program will be the same as another one and close reference should be made to
the [Security Champions Guide][scguide].

[Threat modeling][culturetm] is an activity that in itself is important within an organization,
and it also has the benefit of helping communication between the security teams and development teams.
[Security testing][culturetest] (such as [SAST][dsosast], [DAST][dsodast] and [IAST][dsoiast])
is another area where close collaboration is required within the organization:
management, security, development and pipeline teams will all be involved.
This has the added benefit, as with threat modeling, of promoting a good security culture / awareness
within the organization - and can be a good indicator of where the security culture is succeeding.

[Metrics][culturemetrics] are important for a healthy security culture to persist and grow with an organization.
Without metrics to show the benefits of the security culture then interest and buy-in from the various
teams involved will wane, leading to a decline in the culture and leading in turn to a poor security posture.
Metrics will provide the justification for investment and nurturing of a good security culture.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue1001] or [edit on GitHub][edit1001].

[issue1001]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2010-culture-process/01-security-culture
[edit1001]: https://github.com/OWASP/DevGuide/blob/main/draft/10-culture-process/01-security-culture.md
[culture]: https://owasp.org/www-project-security-culture/
[cultureacts]: https://owasp.org/www-project-security-culture/stable/5-Activities/
[culturechamps]: https://owasp.org/www-project-security-culture/stable/4-Security_Champions/
[culturedoc]: https://owasp.org/www-project-security-culture/stable/
[culturegoal]: https://owasp.org/www-project-security-culture/stable/3-Goal_Setting_and_Security_Team_Collaboration/
[culturemetrics]: https://owasp.org/www-project-security-culture/stable/8-Metrics/
[culturerepo]: https://github.com/OWASP/www-project-security-culture
[culturetest]: https://owasp.org/www-project-security-culture/stable/7-Security_Testing/
[culturetm]: https://owasp.org/www-project-security-culture/stable/6-Threat_Modelling/
[culturewhy]: https://owasp.org/www-project-security-culture/stable/2-Why_Add_Security_In_Development_Teams/
[dsodast]: https://owasp.org/www-project-devsecops-guideline/latest/02b-Dynamic-Application-Security-Testing
[dsoiast]: https://owasp.org/www-project-devsecops-guideline/latest/02c-Interactive-Application-Security-Testing
[dsosast]: https://owasp.org/www-project-devsecops-guideline/latest/02a-Static-Application-Security-Testing
[scguide]: https://owasp.org/www-project-security-champions-guidebook/
