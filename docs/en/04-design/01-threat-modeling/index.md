![Developer guide logo](../../../assets/images/dg_logo_bbd.png "OWASP Developer Guide"){ align=right width=180 }

Referring to the [Threat Modeling Cheat Sheet][cstm],
threat modeling is a structured approach to identifying and prioritizing potential threats to a system.
The threat modeling process includes determining the value that potential mitigations would have
in reducing or neutralizing these threats.

Assessing potential threats during the design phase of your project can save significant resources
if during a later phase of the project refactoring is required to include risk mitigations.
The outcomes from the threat modeling activities generally include:

* Documenting how data flows through a system to identify where the system might be attacked
* Identifying as many potential threats to the system as possible
* Suggesting security controls that may be put in place to reduce the likelihood or impact of a potential threat

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0601] or [edit on GitHub][edit0601].

[cstm]: https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet
[edit0601]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/01-threat-modeling/index.md
[issue0601]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/01-threat-modeling/index
