![Developer guide logo](../assets/images/dg_logo.png "OWASP Developer Guide"){: style="height:180px;float:right" }

## 4. Design

Referring to the [Secure Product Design Cheat Sheet][spdcs], the purpose of secure architecture and design is to ensure
that all products meet or exceed the security requirements laid down by the organization,
focusing on the security linked to components and technologies used during the development of the application.

Secure Architecture Design looks at the selection and composition of components that form the foundation of the solution.
Technology Management looks at the security of supporting technologies used during development, deployment and operations,
such as development stacks and tooling, deployment tooling, and operating systems and tooling.

A secure design will help establish secure defaults, minimize the attack surface area
and fail securely to well-defined and understood defaults.
It will also consider and follow various principles, such as:

* Least Privilege and Separation of Duties
* Defense-in-Depth
* Zero Trust
* Security in the Open

A Secure Development Lifecycle (SDLC) helps to ensure that all security decisions made about the product being developed
are explicit choices and result in the correct level of security for the product design.
Various secure development lifecycles can be used and they generally include threat modeling in the design process.

Checklists and Cheat Sheets are an important tool during the design process;
they provide an easy reference of knowledge and help avoid repeating design errors and mistakes.

Software application [Design][sammd] is one of the major business functions described in
the [Software Assurance Maturity Model (SAMM)][samm], and includes security practices:

* [Threat Assessment][sammdta]
* [Security Requirements][sammdsr]
* [Security Architecture][sammdsa]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing then [submit an issue][issue0600].

[issue0600]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2006-design/00-toc
[samm]: https://owaspsamm.org/about/
[sammd]: https://owaspsamm.org/model/design/
[sammdsa]: https://owaspsamm.org/model/design/secure-architecture/
[sammdsr]: https://owaspsamm.org/model/design/security-requirements/
[sammdta]: https://owaspsamm.org/model/design/threat-assessment/
[spdcs]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet
