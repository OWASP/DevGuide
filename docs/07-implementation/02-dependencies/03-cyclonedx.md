## 5.2.3 CycloneDX

![CycloneDX logo](../../assets/images/logos/cyclonedx.png "OWASP CycloneDX"){: style="height:180px;float:right" }

OWASP [CycloneDX][cyclonedx] is a full-stack Bill of Materials (BOM) standard
that provides advanced supply chain capabilities for cyber risk reduction.
This [project][cyclonedx-project] is one of the OWASP flagship projects.

#### What is CycloneDX?

CycloneDX is a widely used standard for various types of [Bills of Materials][cyclonedx-spec].
It provides an organization's [supply chain][cschain] with software security risk reduction.
The specification supports:

* [Software Bill of Materials][cyclonedx-sbom] (SBOM)
* [Software-as-a-Service Bill of Materials][cyclonedx-saasbom] (SaaSBOM)
* [Hardware Bill of Materials][cyclonedx-hbom] (HBOM)
* [Machine-learning Bill of Materials][cyclonedx-mlbom] (ML-BOM)
* [Manufacturing Bill of Materials][cyclonedx-mbom] (MBOM)
* [Operations Bill of Materials][cyclonedx-obom] (OBOM)
* [Bill of Vulnerabilities][cyclonedx-bov] (BOV)
* [Vulnerability Disclosure Reports][cyclonedx-vdr] (VDR)
* [Vulnerability Exploitability eXchange][cyclonedx-vex] (VEX)
* Common [Release Notes][cyclonedx-notes] format
* Syntax for [Bill of Materials linkage][cyclonedx-bomlink] (BOM-Link)

The CycloneDX project provides standards in XML, JSON, and Protocol Buffers.
There is a large collection of official and community supported tools that consume and create CycloneDX BOMs
or interoperate with the CycloneDX standard.

#### Why use it?

CycloneDX is a very well established standard for SBOMs and various other types of BOM.
There is a huge ecosystem built around CycloneDX and it is used globally by many companies.
In addition SBOMs are mandatory for many industries and various governments - at some point every organization
will have to provide SBOMs for their customers and CycloneDX is an accepted standard for this.

CycloneDX also provides standards for other types of BOMs that may be required in the supply chain
along with standards for release notes and [responsible disclosure][csdisclose].
It is useful to use CycloneDX throughout the supply chain as it promotes interoperability between the various tools.

#### How to use it

The OWASP Spotlight series provides an overview of CycloneDX along with the a demonstration of using SBOMs:
'Project 21 - [OWASP CycloneDX][spotlight21]'.

CycloneDX is an easy to understand standard that can be augmented to suit all parts of a supply chain,
and there are [many tools][cyclonedx-tools] (more than 220 as of February 2024) that interoperate with CycloneDX.

The easiest way to use CycloneDX is to select tools from this list for any of the supported BOM types,
with both proprietary/commercial and open source tools included in the list.
A common example is for a customer to request that an SBOM is provided for a web application,
and [various tools][cyclonedx-tools] can be chosen that are able to export the SBOM in various formats.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue070203] or [edit on GitHub][edit070203].

[cschain]: https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet
[csdisclose]: https://cheatsheetseries.owasp.org/cheatsheets/Vulnerability_Disclosure_Cheat_Sheet
[cyclonedx]: https://cyclonedx.org/
[cyclonedx-bomlink]: https://cyclonedx.org/capabilities/bomlink/
[cyclonedx-bov]: https://cyclonedx.org/capabilities/bov/
[cyclonedx-hbom]: https://cyclonedx.org/capabilities/hbom/
[cyclonedx-mbom]: https://cyclonedx.org/capabilities/mbom/
[cyclonedx-mlbom]: https://cyclonedx.org/capabilities/mlbom/
[cyclonedx-notes]: https://cyclonedx.org/capabilities/release-notes/
[cyclonedx-obom]: https://cyclonedx.org/capabilities/obom/
[cyclonedx-project]: https://owasp.org/www-project-cyclonedx/
[cyclonedx-saasbom]: https://cyclonedx.org/capabilities/saasbom/
[cyclonedx-sbom]: https://cyclonedx.org/capabilities/sbom/
[cyclonedx-spec]: https://cyclonedx.org/specification/overview/
[cyclonedx-tools]: https://cyclonedx.org/tool-center/
[cyclonedx-vdr]: https://cyclonedx.org/capabilities/vdr/
[cyclonedx-vex]: https://cyclonedx.org/capabilities/vex/
[edit070203]: https://github.com/OWASP/DevGuide/blob/main/draft/07-implementation/02-dependencies/03-cyclonedx.md
[issue070203]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2007-implementation/02-dependencies/03-cyclonedx
[spotlight21]: https://youtu.be/qEG6cxwl8os
