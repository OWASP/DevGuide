### 4.1.6 Threat Modeling toolkit

There is no one technique or tool that fits every threat modeling process.
The process can be tactical or architectural, subjective or automated, attack tree or data flow diagram,
all are perfectly valid for different organizations, teams and situations.

The OWASP [Threat Modeling toolkit][toolkit] presentation at OWASP AppSec California 2018 gives a good
overview of the range of concepts and techniques that can be regarded as threat modeling.

#### Advice on Threat Modeling

In addition to the Threat Modeling toolkit there are OWASP community pages on [Threat Modeling][TM]
and the OWASP [Threat Modeling Project][tmproject],
both of which provide context and overviews of threat modeling - in particular Shostack's [Four Question Framework][4QFW].

#### Threat Modeling step by step

The [Threat Modeling Process][TMP] suggests steps that should be taken when threat modeling:

1. Decompose the Application
2. Determine and Rank Threats
3. Determine Countermeasures and Mitigation

and goes into detail on each concept :

* External Dependencies
* Entry Points
* Exit Points
* Assets
* Trust Levels
* Threat Categorization
* Threat Analysis
* Ranking of Threats
* Remediation for threats / vulnerabilities

The OWASP [Threat Modeling Playbook][tmpb] (OTMP) is an OWASP Incubator project that describes how to
create and nurture a good threat modeling culture within the organization itself.

#### Cheat Sheets for Threat Modeling

The OWASP series of Cheat Sheets is a primary source of advice and techniques on all things security,
with the OWASP [Threat Modeling Cheat Sheet][cstm] and OWASP [Attack Surface Analysis Cheat Sheet][asacs]
providing practical suggestions along with explanations of both the terminology and the concepts involved.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060106] or [edit on GitHub][edit060106].

[4QFW]: https://github.com/adamshostack/4QuestionFrame
[asacs]: https://cheatsheetseries.owasp.org/cheatsheets/Attack_Surface_Analysis_Cheat_Sheet
[cstm]: https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet
[issue060106]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2004-design/01-threat-modeling/06-toolkit
[edit060106]: https://github.com/OWASP/DevGuide/blob/main/docs/04-design/01-threat-modeling/06-toolkit.md
[toolkit]: https://www.youtube.com/watch?v=KGy_KCRUGd4
[tmpb]: https://owasp.org/www-project-threat-modeling-playbook/
[tmproject]: https://owasp.org/www-project-threat-model/
[TM]: https://owasp.org/www-community/Threat_Modeling
[TMP]: https://owasp.org/www-community/Threat_Modeling_Process
