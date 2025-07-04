Logging is recording security information during the runtime operation of an application.
Monitoring is the live review of application and security logs using various forms of automation.

Refer to proactive control [C9: Implement Security Logging and Monitoring][control9]
and its [cheatsheets][csproactive-c9] for more context from the OWASP Top 10 Proactive Controls project,
and use the list below as suggestions for a checklist that has been tailored for the individual project.

#### 1. Security logging

1. Log submitted data that is outside of an expected numeric range
2. Log all apparent tampering events, that involve changes to data and state that should not be modifiable
3. Log requests that violate server-side access control rules
4. Encode and validate any dangerous characters before logging to prevent log injection attacks
5. Do not log sensitive information such as unnecessary system details, session identifiers or passwords
6. Logging controls should support both success and failure of specified security events
7. Use a cryptographic hash function to validate log entry integrity
8. Log attempts to authenticate with invalid or expired credentials
9. Log all input validation failures
10. Log all system exceptions
11. Log all administrative functions, including changes to the security configuration settings
12. Log all backend TLS connection failures
13. Log cryptographic module failures

#### 2. Security logging design

1. Protect log integrity
2. Ensure log entries that include untrusted data will not execute as code in the intended log viewing interface or software
3. Restrict access to logs to only authorized individuals
4. Utilize a central routine for all logging operations
5. Forward logs from distributed systems to a central, secure logging service
6. Follow a common logging format and approach within the system and across systems of an organization
7. Synchronize across nodes to ensure that timestamps are consistent
8. All logging controls should be implemented on a trusted system
9. Ensure that a mechanism exists to conduct log analysis

#### 3. Monitoring

1. Effective monitoring and alerting should be established to detect and respond to suspicious activities quickly
2. Account for attack patterns that bypass standard lockouts, such as using the same passwords against multiple user accounts
   while rotating IP addresses

#### References

* OWASP [Cheat Sheet: Logging][cslogging]
* OWASP [Cheat Sheet: Application Logging Vocabulary][csvocabulary]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060209] or [edit on GitHub][edit060209].

[csproactive-c9]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c9-implement-security-logging-and-monitoring
[control9]: https://top10proactive.owasp.org/the-top-10/c9-security-logging-and-monitoring/
[cslogging]: https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet
[csvocabulary]: https://cheatsheetseries.owasp.org/cheatsheets/Logging_Vocabulary_Cheat_Sheet
[edit060209]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/02-web-app-checklist/09-logging-monitoring.md
[issue060209]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/09-logging-monitoring
[proactive10]: https://top10proactive.owasp.org/
