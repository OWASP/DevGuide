# Static Application Security Testing

## What is SAST?

SAST stands for Static Application Security Testing. SAST is a technique that lets you analyze and detect potential security issues in your code. SAST can be used early in the development lifecycle to detect vulnerable code before production.

## Why use SAST?

SAST has benefits like early vulnerability detection, quick feedback and support for shift-left security practices.

## How SAST works

- SAST examines source code or compiled/intermediate representations without running the application.
- It can use rules, patterns or models to identify potentially unsafe code.
- When a SAST tool performs data-flow or taint analysis, it can track untrusted data from the source, through its propagation, to a sink.
- The analysis produces findings but not automatically confirmed vulnerabilities.

## SAST in the development lifecycle

1. SAST can run locally in the IDE that you normally use. It can also be configured on push, on pull request or in CI/CD pipelines.
2. SAST can be integrated early in the development stage. This can help to reduce remediation costs and find problems before they reach later stages.
3. Shift-left security is supported by SAST.
4. Findings can be classified or prioritized by severity and context in order to be reviewed.
5. Not all the findings should automatically block the CI/CD pipeline.
6. The development team can also define policies or security gates to decide when the pipeline should be blocked.

## Limitations

- SAST could produce false positives, which appear to indicate a vulnerability, but are not actually exploitable.
- It could produce false negatives with undetected real vulnerabilities.
- Precision depends on rules, models and tool features.
- Complex flows between methods, classes or files could be difficult to track.
- Frameworks, reflection, generated code or dynamic configurations could reduce coverage.
- A finding should be reviewed, but it should not be automatically considered a real vulnerability.
- SAST does not replace manual review or other security testing techniques.

## Complementary security testing

- SAST does not cover all risk types.
- SCA helps to identify vulnerabilities in libraries or third-party dependencies.
- DAST tests the application while running.
- Manual review can identify logical problems or context that automatic tools could not take into account.
- It is important to know that these techniques complement each other giving a stronger security strategy. They should not be treated as replacements for one another.

## References

- [OWASP Static Code Analysis](https://community.owasp.org/controls/Static_Code_Analysis)
- [OWASP Source Code Analysis Tools](https://community.owasp.org/Source_Code_Analysis_Tools)
- [OWASP Secure Code Review Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Secure_Code_Review_Cheat_Sheet.html)
- [OWASP SAMM - Security Testing](https://owaspsamm.org/model/verification/security-testing/)
- [Semgrep Community Edition](https://semgrep.dev/products/community-edition/)
