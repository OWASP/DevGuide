Dynamic application security testing (DAST) represents a non-functional testing process to identify security weaknesses and
vulnerabilities in applications. The testing process can be carried out manually or be automated. Manual assessment of an
application involves human intervention to identify security flaws which might slip from an automated tool. Usually
business logic errors, race condition checks, and certain zero-day vulnerabilities can only be identified using manual
assessments.

### 6.2.1 DAST tools

DAST tools are programs which communicates with a web application through the web front-end in order to identify potential
security vulnerabilities in the web application and architectural weaknesses. It performs a black-box test. Unlike static
application security testing tools, DAST tools do not have access to the source code and therefore detect vulnerabilities
by actually performing attacks.

#### Different DAST tools

The OWASP Community contains a [list of DAST tools][dast] that can be used to conduct DAST.
All of these tools have their own strengths and weaknesses.
If you are interested in the effectiveness of DAST tools, check out the [OWASP Benchmark][benchmark] project,
which attempts to scientifically measure the effectiveness of all types of
vulnerability detection tools, including DAST.

#### Why use it?

The big advantage of these types of tools are that they can scan year-round to be constantly searching for vulnerabilities.
With new vulnerabilities being discovered regularly this allows companies to find and patch vulnerabilities before they
can become exploited.

#### Cons

Because these tools does dynamic testing, it cannot cover 100% of the source code of the application and then, the
application itself. The penetration tester should look at the coverage of the web application or of its attack surface to
know if the tool was configured correctly or was able to understand the web application.

#### References

* [Dynamic application security testing][wikipedia]
* [Vulnerability Scanning Tools][dast]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue080201] or [edit on GitHub][edit080201].

[benchmark]: https://owasp.org/www-project-benchmark/
[dast]: https://owasp.org/www-community/Vulnerability_Scanning_Tools
[edit080201]: https://github.com/OWASP/DevGuide/blob/main/docs/08-verification/02-tools/01-dast.md
[issue080201]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2008-verification/02-tools/01-dast
[wikipedia]: https://en.wikipedia.org/wiki/Dynamic_application_security_testing
