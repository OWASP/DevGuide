The OWASP [Automated Threats to Web Applications][oatproject] project names and classifies the ways
that web applications are misused by automated software, such as bots and scripts.
It is an OWASP Lab project, and its main output is the [OWASP Automated Threat Handbook][handbook].

#### What are automated threats?

Automated threats are attacks where software, rather than a person, repeatedly uses valid functionality of a web application
in a way that harms the application owner or its users.
They are different from exploiting a vulnerability: every individual request can be legitimate,
for example a single login attempt or a single product search,
and the harm only comes from doing it at scale or for a different purpose.

The project defines 21 threat events, each with an OAT identifier:

* OAT-001 Carding
* OAT-002 Token Cracking
* OAT-003 Cost-Inflation Fraud (previously Ad Fraud)
* OAT-004 Fingerprinting
* OAT-005 Scalping
* OAT-006 Expediting
* OAT-007 Credential Cracking
* OAT-008 Credential Stuffing
* OAT-009 CAPTCHA Defeat
* OAT-010 Card Cracking
* OAT-011 Scraping
* OAT-012 Cashing Out
* OAT-013 Sniping
* OAT-014 Vulnerability Scanning
* OAT-015 Denial of Service
* OAT-016 Skewing
* OAT-017 Spamming
* OAT-018 Footprinting
* OAT-019 Account Creation
* OAT-020 Account Aggregation
* OAT-021 Denial of Inventory

#### Why use it?

None of these threats are implementation bugs, so they don't show up as findings from a vulnerability scan
or map neatly onto the OWASP Top 10. The application is working as designed; it's the way it is used that causes the harm.
They also often have sector-specific names, for example 'sneaker bots' for scalping,
which makes it hard for business owners, developers and security teams to talk about the same problem.

The OAT identifiers provide a common language for this.
During threat modeling they act as a checklist of the automated misuse that a feature could attract,
and in requirements they allow a specific outcome to be stated,
for example that the payment functions must not be susceptible to OAT-001 Carding or OAT-010 Card Cracking,
rather than naming a particular product such as a bot management service.

#### How to use it

When threat modeling a feature, ask which of the threat events apply to it:
login and password reset pages attract Credential Stuffing and Credential Cracking,
sign up pages attract Account Creation, checkout pages attract Carding and Card Cracking,
limited stock or booking systems attract Scalping and Denial of Inventory,
and auctions or other time-limited offers attract Sniping.
The project's [threat identification chart][oatchart] helps decide which threat event matches an observed behavior.

Each threat event in the handbook describes the symptoms and the possible countermeasures,
and these can be used to define the security requirements and the monitoring that the feature needs.
The OWASP [Bot Management and Anti-Automation Cheat Sheet][csbot] gives practical guidance
on implementing those countermeasures.

#### References

* OWASP [Automated Threats to Web Applications][oatproject] project
* OWASP [Automated Threat Handbook][handbook]
* OWASP [Bot Management and Anti-Automation Cheat Sheet][csbot]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue040108] or [edit on GitHub][edit040108].

[csbot]: https://cheatsheetseries.owasp.org/cheatsheets/Bot_Management_and_Anti-Automation_Cheat_Sheet
[edit040108]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/01-threat-modeling/08-automated-threats.md
[handbook]: https://github.com/OWASP/www-project-automated-threats-to-web-applications/tree/master/assets/files/EN
[issue040108]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2004-design/01-threat-modeling/08-automated-threats
[oatchart]: https://owasp.org/www-project-automated-threats-to-web-applications/assets/files/oat-ontology-decision-chart.pdf
[oatproject]: https://owasp.org/projects/automated-threats-to-web-applications
