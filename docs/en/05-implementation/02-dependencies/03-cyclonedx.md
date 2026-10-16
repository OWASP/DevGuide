![CycloneDX logo](../../../assets/images/logos/cyclonedx.png "OWASP CycloneDX"){ align=right width=180 }

OWASP [CycloneDX][cyclonedx] is a Bill of Materials (BOM) standard
that provides supply chain capabilities for cyber risk reduction.
This [project][cyclonedx-project] is one of the OWASP flagship projects
and is also an [ECMA][ecma] international standard ECMA-424.

#### What is CycloneDX?

CycloneDX is a widely used for various types of [Bills of Materials][cyclonedx-spec].
Think of a Bill of Materials (BOM) as a list of the components in a deliverable;
a real world example might be receiving a new mobile phone and the package contains:

* the mobile phone itself
* a charger cable
* various disclaimers and warranties

This itemized list can be called a Bill of Materials, and it means the consumer knows exactly what is provided.

In a similar way, CycloneDX provides software security risk reduction for an organization's [supply chain][cschain]
by specifying what is in the (often third party) components that make up the deliverable product.
The specification supports:

* [Software Bill of Materials][sbom] (SBOM)
* [Cryptography Bill of Materials][cbom] (CBOM)
* [Software-as-a-Service Bill of Materials][saasbom] (SaaSBOM)
* [Hardware Bill of Materials][hbom] (HBOM)
* [Machine-learning Bill of Materials][mlbom] (ML-BOM)
* [Manufacturing Bill of Materials][mbom] (MBOM)
* [Operations Bill of Materials][obom] (OBOM)
* [Bill of Vulnerabilities][bov] (BOV)
* [Vulnerability Disclosure Reports][cyclonedx-vdr] (VDR)
* [Vulnerability Exploitability eXchange][cyclonedx-vex] (VEX)
* Common [Release Notes][cyclonedx-notes] format
* Syntax for [Bill of Materials linkage][cyclonedx-bomlink] (BOM-Link)

The CycloneDX project provides standards in XML, JSON, and Protocol Buffers.
There is a large collection of official and community supported tools that consume and create CycloneDX BOMs
or interoperate with the CycloneDX standard.

#### Why use it?

BOMs are useful. From answering questions such as "What cryptography are we shipping in that product?"
to listing vulnerabilities in a deliverable in a consumable way along with a listing of software packages / libraries.

CycloneDX is a very well established standard for SBOMs and various other types of BOM.
There is a huge ecosystem built around CycloneDX and it is used globally by many companies.
In addition SBOMs are mandatory for many industries and various governments - at some point every organization
will have to provide SBOMs for their customers and CycloneDX is an accepted standard for this.

CycloneDX also provides standards for other types of BOMs that may be required in the supply chain
along with standards for release notes and [responsible disclosure][csdisclose].
It is useful to use CycloneDX throughout the supply chain as it promotes interoperability between the various tools.

If there is a security related list that is being generated, then chances are there is a CycloneDX BOM for that.

#### How to use it

The OWASP Spotlight series provides an overview of CycloneDX along with the a demonstration of using SBOMs:
'Project 21 - [OWASP CycloneDX][spotlight21]'.

CycloneDX is an easy to understand standard that can be extended to suit all parts of a supply chain,
and there are [many tools][cyclonedx-tools] (more than 220 as of February 2024) that interoperate with CycloneDX.

The easiest way to use CycloneDX is to select tools from this list for any of the supported BOM types,
with both proprietary/commercial and open source tools included in the list.
A common example is for a customer to request that an SBOM is provided for a web application,
and [various tools][cyclonedx-tools] can be chosen that are able to export the SBOM in various formats.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue050203] or [edit on GitHub][edit050203].

[cbom]: https://cyclonedx.org/capabilities/cbom/
[cschain]: https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet
[csdisclose]: https://cheatsheetseries.owasp.org/cheatsheets/Vulnerability_Disclosure_Cheat_Sheet
[cyclonedx]: https://cyclonedx.org/
[cyclonedx-bomlink]: https://cyclonedx.org/capabilities/bomlink/
[cyclonedx-notes]: https://cyclonedx.org/capabilities/release-notes/
[cyclonedx-project]: https://owasp.org/projects/cyclonedx/
[cyclonedx-spec]: https://cyclonedx.org/specification/overview/
[cyclonedx-tools]: https://cyclonedx.org/tool-center/
[cyclonedx-vdr]: https://cyclonedx.org/capabilities/vdr/
[cyclonedx-vex]: https://cyclonedx.org/capabilities/vex/
[bov]: https://cyclonedx.org/capabilities/bov/
[hbom]: https://cyclonedx.org/capabilities/hbom/
[mbom]: https://cyclonedx.org/capabilities/mbom/
[mlbom]: https://cyclonedx.org/capabilities/mlbom/
[obom]: https://cyclonedx.org/capabilities/obom/
[saasbom]: https://cyclonedx.org/capabilities/saasbom/
[sbom]: https://cyclonedx.org/capabilities/sbom/
[ecma]: https://ecma-international.org/
[edit050203]: https://github.com/OWASP/DevGuide/blob/main/docs/en/05-implementation/02-dependencies/03-cyclonedx.md
[issue050203]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/02-dependencies/03-cyclonedx
[spotlight21]: https://youtu.be/qEG6cxwl8os
