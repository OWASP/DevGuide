“Secure-by-Default” means products are resilient against prevalent exploitation techniques out of the box
without additional charge. Software should start in a secure state without requiring extensive user configuration,
ensuring the default settings are always the most secure option.

Refer to proactive control [C5: Secure By Default Configurations][control5] and the
[Infrastructure as Code Security Cheatsheet][csproactive-c5]
for more context from the OWASP Top 10 Proactive Controls project,
and use the lists below as suggestions for a checklist that has been tailored for the individual project.

#### 1. System configuration (SC)

1. Restrict applications, processes and service accounts to the least privileges possible
2. Code which defines the infrastructure should follow the principle of least privilege.
3. Remove all unnecessary functionality such as files, accounts, software, and demo capabilities
4. Remove test code or any functionality not intended for production, prior to deployment
5. The security configuration store for the application should be available in human readable form to support auditing
6. Isolate development environments from production and provide access only to authorized development and test groups
7. Implement a software change control system to manage and record changes to the code both in development and production
8. Prevent accidentally accessible and sensitive pages from appearing in search engines using a robots.txt file,
the
    X-Robots-Tag response header or a robots html meta tag
9. Disable unnecessary HTTP methods, such as WebDAV extensions. If an extended HTTP method that supports file handling is
    required, utilize a well-vetted authentication mechanism
10. Remove unnecessary information from HTTP response headers related to the OS, web-server version and application
    frameworks unless implemented to confuse an attacker
11. Ensure the .git, .svn folders or any source control metadata aren't deployed together alongside the application in
    away that makes these directly accessible externally or indirectly through the application
12. Do not store passwords, secrets, connection strings, key material, secret management integrations or other
    sensitive information in clear text or in any non-cryptographically secure manner on the client, in source code, or build
    artifacts
13. Remove or restrict access to internal application and system documentation (such as for internal APIs) as this can
    reveal backend system or other useful information to attackers

#### 2. File management (FM)

1. Turn off directory listings
2. Do not save files in the same web context as the application
3. Turn off execution privileges on file upload directories
4. Ensure application files and resources are read-only
5. Restrict access to files or other resources, including those outside the application's direct control using an allow list
    or the equivalent thereof.

#### 3. Cloud security (CS)

1. Enforce JIT (Just-In-Time) access management
2. Use security vetted container images that is scanned for package and component vulnerabilities and pulled from a private
    container registry
3. Utilize Infrastructure-as-Code templates for automated provisioning and configuration of your cloud and on-
    premises infrastructure
4. Utilize Policy-as-Code to enforce policies including privilege assignments

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060201] or [edit on GitHub][edit060201].

[control5]: https://top10proactive.owasp.org/the-top-10/c5-secure-by-default/
[csproactive-c5]: https://cheatsheetseries.owasp.org/cheatsheets/Infrastructure_as_Code_Security_Cheat_Sheet.html
[edit060201]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/02-web-app-checklist/01-secure-by-default.md
[issue060201]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/01-secure-by-default
