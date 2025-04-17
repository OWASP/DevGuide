### 4.2.1 Checklist: Define Security Requirements

A security requirement is a statement of security functionality that ensures software security is being satisfied.
Security requirements are derived from industry standards, applicable laws, and a history of past vulnerabilities.

Refer to proactive control [C4: Address Security form the Start][control4] and its [cheatsheets][csproactive-c1]
for more context from the OWASP Top 10 Proactive Controls project,
and use the lists below as suggestions for a checklist that has been tailored for the individual project.

#### 1. System configuration

1. Restrict applications, processes and service accounts to the least privileges possible
2. If the application must run with elevated privileges, raise privileges as late as possible, and drop as soon as possible
3. Remove all unnecessary functionality and files
4. Remove test code or any functionality not intended for production, prior to deployment
5. The security configuration store for the application should be available in human readable form to support auditing
6. Isolate development environments from production and provide access only to authorized development and test groups
7. Implement a software change control system to manage and record changes to the code both in development and production

#### 2. Cryptographic practices

1. Use peer reviewed and open solution cryptographic modules
2. All cryptographic functions used to protect secrets from the application user must be implemented on a trusted system
3. Cryptographic modules must fail securely
4. Ensure all random elements such as numbers, file names, UUID and strings are generated
    using the cryptographic module approved random number generator
5. Cryptographic modules used by the application are compliant to FIPS 140-2 or an equivalent standard
6. Establish and utilize a policy and process for how cryptographic keys will be managed
7. Ensure that any secret key is protected from unauthorized access
8. Store keys in a proper secrets vault as described below
9. Use independent keys when multiple keys are required
10. Build support for changing algorithms and keys when needed
11. Build application features to handle a key rotation

#### 3. File management

1. Do not pass user supplied data directly to any dynamic include function
2. Require authentication before allowing a file to be uploaded
3. Limit the type of files that can be uploaded to only those types that are needed for business purposes
4. Validate uploaded files are the expected type by checking file headers rather than by file extension
5. Do not save files in the same web context as the application
6. Prevent or restrict the uploading of any file that may be interpreted by the web server.
7. Turn off execution privileges on file upload directories
8. When referencing existing files, use an allow-list of allowed file names and types
9. Do not pass user supplied data into a dynamic redirect
10. Do not pass directory or file paths, use index values mapped to pre-defined list of paths
11. Never send the absolute file path to the client
12. Ensure application files and resources are read-only
13. Scan user uploaded files for viruses and malware

#### References

* OWASP [Application Security Verification Standard][asvs] (ASVS)
* OWASP [Mobile Application Security][mas]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060201] or [edit on GitHub][edit060201].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[csproactive-c1]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c1-define-security-requirements
[control4]: https://top10proactive.owasp.org/the-top-10/c4-secure-architecture/
[edit060201]: https://github.com/OWASP/www-project-developer-guide/blob/main/draft/06-design/02-web-app-checklist/01-define-security-requirements.md
[issue060201]: https://github.com/OWASP/www-project-developer-guide/issues/new?labels=enhancement&template=request.md&title=Update:%2006-design/02-web-app-checklist/01-define-security-requirements
[mas]: https://mas.owasp.org/
[proactive10]: https://top10proactive.owasp.org/
