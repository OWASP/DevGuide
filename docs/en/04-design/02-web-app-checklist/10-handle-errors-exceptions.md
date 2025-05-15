Handling [exceptions and errors][cserror] correctly is critical to making your code reliable and secure.
Error and exception handling occurs in all areas of an application including critical business logic
as well as security features and framework code.

Refer to proactive control [C3: Validate all Input & Handle Exceptions][control3]
and its [cheatsheets][csproactive-c10] for more context from the OWASP Top 10 Proactive Controls project,
and use the list below as suggestions for a checklist that has been tailored for the individual project.

#### 1. Errors and exceptions

1. Manage exceptions in a centralized manner to avoid duplicated try/catch blocks in the code
2. Ensure that all unexpected behavior is correctly handled inside the application
3. Ensure that error messages displayed to users do not leak critical data,
    but are still verbose enough to enable the proper user response
4. Ensure that exceptions logs give enough information for support, QA, forensics or incident response teams
5. Carefully test and verify error handling code
6. Do not disclose sensitive information in error responses, for example
    system details, session identifiers or account information
7. Use error handlers that do not display debugging or stack trace information
8. Implement generic error messages and use custom error pages
9. The application should handle application errors and not rely on the server configuration
10. Properly free allocated memory when error conditions occur
11. Error handling logic associated with security controls should deny access by default

#### References

* OWASP [Code Review Guide: Error Handling][review]
* OWASP [Improper Error Handling][handle]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060210] or [edit on GitHub][edit060210].

[cserror]: https://cheatsheetseries.owasp.org/cheatsheets/Error_Handling_Cheat_Sheet
[csproactive-c10]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c10-handle-all-errors-and-exceptions
[control3]: https://top10proactive.owasp.org/the-top-10/c3-validate-input-and-handle-exceptions/
[edit060210]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/02-web-app-checklist/10-handle-errors-exceptions.md
[handle]: https://owasp.org/www-community/Improper_Error_Handling
[issue060210]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/10-handle-errors-exceptions
[proactive10]: https://top10proactive.owasp.org/
[review]: https://owasp.org/www-project-code-review-guide/
