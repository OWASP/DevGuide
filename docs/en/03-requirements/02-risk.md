This section discusses the Application Risk Profile,
an activity in the OWASP Software Assurance Maturity Model ([SAMM][samm]).
The risk profile activity is part of the Threat Assessment security practice in the Design business function.

#### Overview

Risk management is the identification, assessment, and prioritization of risks to the application or system.
The objective of risk management is to ensure that uncertainty does not deflect development activities
away from the business goals.

Remediation is the strategy chosen in response to a risk to the business system,
and these risks are identified using various techniques such as threat modeling and security requirements analysis.

Risk management can be split into two phases. First create a risk profile for the application
and then provide solutions (remediate) to those risks in a way that is best for the business;
risk management should always be business driven.

#### Application risk profile

The application risk profile is created to understand the likelihood and also the impact of an attack.
Over time various profiles could be created and these should be stored in a risk profile inventory,
and ideally the risk profiles should be revisited as part of the organization's secure development strategy.

Quantifying risks is often difficult and there are many ways of approaching this;
refer to the reading list below for various strategies in creating a risk rating model.
The OWASP page on [Risk Rating Methodology][rrm] describes some steps in identifying risks and quantifying them:

1. Identifying a risk
2. Factors for estimating likelihood
3. Factors for estimating impact
4. Determining severity of the risk
5. Deciding what to fix
6. Customizing the risk rating model

The activities involved in creating a risk profile depend very much on the processes
and maturity level of the organization, which is beyond the level of this
Developer Guide, so refer to the further reading listed below for guidance and examples.

#### Remediation

Risks identified during threat assessment, for example through the risk profile or through threat modeling,
should have solutions or remedies applied.

There are four common ways to handle risk, often given the acronym TAME:

1. Transfer: the risk is considered serious but can be transferred to another party

2. Acceptance: the business is aware of the risk but has decided that no action needs to be taken;
    the level of risk is deemed acceptable

3. Mitigation: the risk is considered serious enough to require implementation of security controls
    to reduce the risk to an acceptable level

4. Eliminate / Avoid: the risk can be avoided or removed completely,
    often by removing the object with which the risk is associated

Examples:

1. Transfer: a common example of transferring risk is the use of third party insurance
    in response to the risk of RansomWare.
    Insurance premiums are paid but losses to the business are covered by the insurance

2. Acceptance: sometimes a risk is low enough in priority, or the outcome bearable, that it is not worth mitigating,
    an example might be where the version of software is revealed but this is acceptable (or even desirable)

3. Mitigation: it is common to implement a security control to mitigate the impact of a risk, for example
    input sanitization or output encoding may be used for information supplied by an untrusted source,
    or the use of encrypted communication channels for transferring high risk information

4. Eliminate: an example may be that an application implements legacy functionality that is no longer used,
    if there is a risk of it being exploited then the risk can be eliminated by removing this legacy functionality

#### References

* [OWASP Risk Rating Methodology][rrm]
* [NIST 800-30 - Guide for Conducting Risk Assessments][nist]
* [Government of Canada - The Harmonized Threat and Risk Assessment Methodology][tra]
* Mozilla's [Risk Assessment Summary][rrs] and [Rapid Risk Assessment (RRA)][rra]
* [Common Vulnerability Scoring System (CVSS)][cvss] used for severity and risk ranking

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0502] or [edit on GitHub][edit0502].

[cvss]: https://www.first.org/cvss/
[issue0502]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2003-requirements/02-risk
[nist]: https://csrc.nist.gov/publications/detail/sp/800-30/rev-1/final
[edit0502]: https://github.com/OWASP/DevGuide/blob/main/docs/en/03-requirements/02-risk.md
[rra]: https://infosec.mozilla.org/guidelines/risk/rapid_risk_assessment.html
[rrm]: https://owasp.org/www-community/OWASP_Risk_Rating_Methodology
[rrs]: https://infosec.mozilla.org/guidelines/assessing_security_risk
[samm]: https://owaspsamm.org/about/
[tra]: https://cyber.gc.ca/en/guidance/harmonized-tra-methodology-tra-1
