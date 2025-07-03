Input validation is a collection of techniques that ensure only properly formatted data
may enter a software application or system component.

It is vital that input validation is performed to provide the starting point for a secure application or system.
Without input validation the software application/system will continue to be vulnerable to new and varied attacks.

Refer to proactive control [C3: Validate All Input & Handle Exceptions][control3] and its [cheatsheets][csproactive-c5]
for more context from the OWASP Top 10 Proactive Controls project,
and use the list below as suggestions for a checklist that has been tailored for the individual project.

#### 1. Syntax and semantic validity

1. Identify all data sources and classify them into trusted and untrusted
2. Validate all input data from untrusted sources such as client provided data
3. Encode input to a common character set before validating
4. Specify character sets, such as UTF-8, for all input sources
5. If the system supports UTF-8 extended character sets then validate after UTF-8 decoding is completed
6. Verify that protocol header values in both requests and responses contain only ASCII characters
7. Validate data from redirects
8. Validate data range and also data length
9. Utilize canonicalization to address obfuscation attacks
10. All validation failures should result in input rejection
11. Validate all input against an allowlist of characters, whenever possible

#### 2. Libraries and frameworks

1. Conduct all input validation on a trusted system [^SCP1]
2. Use a centralized input validation library or framework for the whole application
3. If the standard validation routine cannot address some inputs then use extra discrete checks
4. If any potentially hazardous input _must_ be allowed then implement additional controls
5. Validate for expected data types using an allow-list rather than a deny-list

#### 3. Validate serialized data

1. Implement integrity checks or encryption of the serialized objects
    to prevent hostile object creation or data tampering
2. Enforce strict type constraints during deserialization before object creation;
    typically a definable set of classes is expected
3. Isolate features that deserialize so that they run in very low privilege environments such as temporary containers
4. Log security deserialization exceptions and failures
5. Restrict or monitor incoming and outgoing network connectivity from containers or servers that deserialize
6. Monitor deserialization, for example alerting if a user agent constantly deserializes

#### References

* OWASP [Cheat Sheet: Input Validation][ivcs]
* OWASP [Java HTML Sanitizer Project][sanitizer]
* OWASP [Top 10 Proactive Controls][proactive10]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060205] or [edit on GitHub][edit060205].

[^SCP1]: Secure Coding Practices checklist

[csproactive-c5]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c5-validate-all-inputs
[control3]: https://top10proactive.owasp.org/the-top-10/c3-validate-input-and-handle-exceptions/
[ivcs]: https://cheatsheetseries.owasp.org/cheatsheets/Input_Validation_Cheat_Sheet
[edit060205]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/02-web-app-checklist/05-validate-inputs.md
[issue060205]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/05-validate-inputs
[proactive10]: https://top10proactive.owasp.org
[sanitizer]: https://www.owasp.org/index.php/OWASP_Java_HTML_Sanitizer
