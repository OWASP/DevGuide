The [Threat Model Library][tml] is a collection of threat models that have been donated to the public domain
and which provide examples of best practice.
This is an OWASP Incubator project with [several models][tmboms] available already and more to come.

#### What is the Threat Model Library?

The Threat Model library is just that;
a collection of models donated to the public domain by various organizations and individuals.
The intention is that these threat models that will stimulate discussion and
can be used as the starting point for other similar systems.

Sharing threat models into the public domain was promoted in a talk by Adam Shostack
at the OWASP 2025 AppSec Barcelona conference: [Publish Your Threat Models!][tmpublish].

The threat models are categorized as:

1. Web applications
2. Infrastructure
3. AI-ML systems

with more categories to be added.

The threat models are in a standard file format, Threat Model Bill of Materials (TMBOM),
and the format of these TM-BOM files is defined by the [Threat Model library schema][tmbom-schema].
The TM-BOM is (as of January 2026) in the process of being defined
by a CycloneDX working group to be part of the existing ECMA-424 standard
published by [ECMA][ecma] international.

#### How to view the models

As of January 2026 [Threat Dragon][tddownload] is the only tool
that provides an easy-to-read rendering of the TM-BOM files along with a PDF report.
More tools are expected to handle TM-BOM file format as the ECMA standard comes into place
and demand for the format increases.

At present Threat Dragon can import the TM-BOM file to display the model and create a report, but it can not export TM-BOMs.
There are plans to provide the TM-BOM export from Threat Dragon
during the course of 2026 which will allow creation and updates to the TM-BOM files.

#### How to create new models

No matter what method or tool is used to create a threat model in TM-BOM format, the activities are roughly the same.
As an example they can be based on Shostack's [Four Question Framework][4QFW] :

1. Describe the system (What are we working on?)
    1. Provide the **Scope** of the diagram
    2. Create a **Diagram** that describes the system using
        1. **Actor** nodes
        2. **Component** nodes
        3. **Data Store** nodes containing **Data Sets**
        4. **Trust Zones**
        5. **Trust Boundaries**
        6. **Data Flows** from one node to another
    3. List the **Assumptions** made when creating the model
2. Identify threats and risks (What can go wrong?)
    1. List the **Threat Personas** - malicious or otherwise
    2. Identify the **Threats** to the system
    3. Identify the **Risks** for the Threats
3. Identify remediations and controls (What are we going to do about it?)
    1. List the existing **Controls** or new ones that need to be put in place
    2. Create the **Mitigation Plans** that contain controls for the identified risks
4. Report what threats are unremediated (Did we do a good job?)
    [Threat Dragon][tdtm] can highlight threats that remain unremediated and also provide reporting;
    more tools will follow as they become TM-BOM aware

The details of creating these TM-BOM files are described in a Threat Model Library [wiki page][tmlwiki].

#### References

* OWASP [Threat Model Library][tml]
* [Threat models][tmboms] in TM-BOM format

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue040106] or [edit on GitHub][edit040106].

[4QFW]: https://github.com/adamshostack/4QuestionFrame
[ecma]: https://ecma-international.org/
[edit040106]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/01-threat-modeling/06-threat-model-library.md
[issue040106]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2004-design/01-threat-modeling/06-threat-model-library
[tddownload]: https://github.com/OWASP/threat-dragon/releases
[tdtm]: https://owasp.org/projects/threat-dragon
[tmboms]: https://github.com/OWASP/www-project-threat-model-library/tree/main/threat-models/
[tmbom-schema]: https://github.com/OWASP/www-project-threat-model-library/releases/latest
[tml]: https://owasp.org/projects/threat-model-library
[tmlwiki]: https://github.com/OWASP/www-project-threat-model-library/wiki/Creating-TM%E2%80%90BOMs
[tmpublish]: https://www.youtube.com/watch?v=jEqa16lGz_E
