Secure coding libraries and software frameworks with embedded security help software developers guard against
security-related design and implementation flaws.

Refer to proactive control [C4: Address Security from the Start][control4]
and its [cheatsheets][csproactive-c2] for more context from the OWASP Top 10 Proactive Controls project.

For technology specific checklists refer to the appropriate OWASP Cheat Sheets:

* [AJAX_Security][csajax]
* [C-Based toolchain hardening][cscbased]
* [Django security][csdjango]
* [Django REST framework][csdjangorest]
* [Docker security][csdocker]
* [DotNet security][csdotnet]
* [GraphQL security][csgraphql]
* [Infrastructure as Code][csias]
* [Java security][csjava]
* [Javascript management][csjcavascript]
* [Kubernetes][cskube]
* [Laravel security][cslaravel]
* [Microservices security][csmicro]
* [NPM security best practices][csnpm]
* [Node.js security][csnode]
* [Node.js security for Docker][csnodedocker]
* [PHP configuration][csphp]
* [REST APIs][csrest] and [how to assess them][csrassess]
* [Ruby on Rails security][csruby]
* [Symfony framework][cssymfony]
* [Web Services][cswebservice]
* [XML security][csxml]

and use them as the starting point for a checklist that is tailored for the technology used by the project.

In addition consider the following extra checks for frameworks and libraries.

#### 1. Security Frameworks and Libraries

1. Ensure servers, frameworks and system components are running the latest approved versions and patches
2. Use libraries and frameworks from trusted sources that are actively maintained and widely used
3. Review all secondary applications and third party libraries to determine business necessity
4. Validate safe functionality for all secondary applications and third party libraries
5. Create and maintain an inventory catalog of all third party libraries using Software Composition Analysis (SCA)
6. Proactively keep all third party libraries and components up to date
7. Reduce the attack surface by encapsulating the library and expose only the required behavior into your software
8. Use tested and approved managed code rather than creating new unmanaged code for common tasks
9. Utilize task specific built-in APIs to conduct operating system tasks
10. Do not allow the application to issue commands directly to the Operating System
11. Use checksums or hashes to verify the integrity of interpreted code, libraries, executables, and configuration files
12. Restrict users from generating new code or altering existing code
13. Implement safe updates using encrypted channels
14. Use cryptographic signatures when updating your code and ensure the package manager verify those signatures

#### References

* OWASP [Dependency Check][dependency]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060202] or [edit on GitHub][edit060202].

[csajax]: https://cheatsheetseries.owasp.org/cheatsheets/AJAX_Security_Cheat_Sheet
[cscbased]: https://cheatsheetseries.owasp.org/cheatsheets/C-Based_Toolchain_Hardening_Cheat_Sheet
[csdjango]: https://cheatsheetseries.owasp.org/cheatsheets/Django_Security_Cheat_Sheet
[csdjangorest]: https://cheatsheetseries.owasp.org/cheatsheets/Django_REST_Framework_Cheat_Sheet
[csdocker]: https://cheatsheetseries.owasp.org/cheatsheets/Docker_Security_Cheat_Sheet
[csdotnet]: https://cheatsheetseries.owasp.org/cheatsheets/DotNet_Security_Cheat_Sheet
[csgraphql]: https://cheatsheetseries.owasp.org/cheatsheets/GraphQL_Cheat_Sheet
[csias]: https://cheatsheetseries.owasp.org/cheatsheets/Infrastructure_as_Code_Security_Cheat_Sheet
[csjava]: https://cheatsheetseries.owasp.org/cheatsheets/Java_Security_Cheat_Sheet
[csjcavascript]: https://cheatsheetseries.owasp.org/cheatsheets/Third_Party_Javascript_Management_Cheat_Sheet
[cskube]: https://cheatsheetseries.owasp.org/cheatsheets/Kubernetes_Security_Cheat_Sheet
[cslaravel]: https://cheatsheetseries.owasp.org/cheatsheets/Laravel_Cheat_Sheet
[csmicro]: https://cheatsheetseries.owasp.org/cheatsheets/Microservices_Security_Cheat_Sheet
[csnpm]: https://cheatsheetseries.owasp.org/cheatsheets/NPM_Security_Cheat_Sheet
[csnode]: https://cheatsheetseries.owasp.org/cheatsheets/Nodejs_Security_Cheat_Sheet
[csnodedocker]: https://cheatsheetseries.owasp.org/cheatsheets/NodeJS_Docker_Cheat_Sheet
[csphp]: https://cheatsheetseries.owasp.org/cheatsheets/PHP_Configuration_Cheat_Sheet
[csrest]: https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet
[csrassess]: https://cheatsheetseries.owasp.org/cheatsheets/REST_Assessment_Cheat_Sheet.html
[csruby]: https://cheatsheetseries.owasp.org/cheatsheets/Ruby_on_Rails_Cheat_Sheet
[cssymfony]: https://cheatsheetseries.owasp.org/cheatsheets/Symfony_Cheat_Sheet
[cswebservice]: https://cheatsheetseries.owasp.org/cheatsheets/Web_Service_Security_Cheat_Sheet
[csxml]: https://cheatsheetseries.owasp.org/cheatsheets/XML_Security_Cheat_Sheet
[csproactive-c2]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c2-leverage-security-frameworks-and-libraries
[control4]: https://top10proactive.owasp.org/the-top-10/c4-secure-architecture/
[dependency]: https://owasp.org/www-project-dependency-check/
[edit060202]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/02-web-app-checklist/02-frameworks-libraries.md
[issue060202]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/02-frameworks-libraries
[proactive10]: https://top10proactive.owasp.org/
