# Input validation

Allocated to Viral

## Background

Majority of today’s applications get exploited because it fails to validate the input coming from users, files, third party applications, infrastructure, external entities, database systems or by other processes. Almost every application on the web requires some sort of input from the listed entity. These input sources can be a great starting point for an attacker. Hence, all inputs to an application must be checked and validated before processing it.

Following are a detailed list of vulnerabilities against which an application can be protacted just by validating an input:
- HTML Injection
- Buffer Overflow
- Code Insertion
- Social Engineering

## Principles
<H3> Assume every input field is vulnerable and user has malicious intention </H3>
It is a good practice to assume that all the user input has malicious intention. Developer must develope a proper logic where an application can draw a boundry between malicious and trusted user input. For example, if you call an external Web service that returns strings, how do you know that malicious commands are not present? Also, if several applications write to a shared database, when you read data, how do you know whether it is safe? 

<H3>Validation should be the core part of the application</H3>
Developers should consider a centralized appraoch to validate every input area of an application. Input validation strategy should be a core element during the development process. 

Sometimes it is difficult to apply a common strategy application wide in such case individual fields of the forms of an application require a special validation, for example, with specifically developed regular expressions. However, you can frequently factor out common routines to validate regularly used fields such as e-mail addresses, titles, names, postal addresses including ZIP or postal codes, and so on. 

<H3>Client-side validation are easy to bypass</H3>
Server-side code should perform its own validation. Client side validation code are easily seen by an attacker using view source facility in browsers and hence can be bypassed. Also, if the user has congifured their browser to not run JavaScript then in that case the validation will fail.

Use client-side validation to help reduce the number of round trips to the server but do not rely on it for security. This is an example of defense in depth. 

<H3> Reject all known bad input </H3> - paraphrasing required
Deny "bad" data; although do not rely completely on this approach. This approach is generally less effective than using the "allow" approach described earlier and it is best used in combination. To deny bad data assumes your application knows all the variations of malicious input. Remember that there are multiple ways to represent characters. This is another reason why "allow" is the preferred approach.

While useful for applications that are already deployed and when you cannot afford to make significant changes, the "deny" approach is not as robust as the "allow" approach because bad data, such as patterns that can be used to identify common attacks, do not remain constant. Valid data remains constant while the range of bad data may change over time. 

<H3>Encrypt sensitive cookie state </H3> - paraphrasing required and put good example from Apple documentation
Cookies may contain sensitive data such as session identifiers or data that is used as part of the server-side authorization process. To protect this type of data from unauthorized manipulation, use cryptography to encrypt the contents of the cookie. Make sure that users do not bypass your checks. Make sure that users do not bypass your checks by manipulating parameters. URL parameters can be manipulated by end users through the browser address text box. For example, the URL http://www.<YourSite>/<YourApp>/sessionId=10 has a value of 10 that can be changed to some random number to receive different output. Make sure that you check this in server-side code, not in client-side JavaScript, which can be disabled in the browser. 



## Positive controls 

### Control
How to build a secure <thing> using Control to help you, including (or even just) UML diagrams. I prefer swim lanes, but as long as it prints in landscape mode, I'm cool. I don't want portrait diagrams as this is impossible to reflow automatically using our tools.

### Control
How to build a secure <thing> using Control to help you


## Unit or Integration Test Cases

## Abuse Cases

## Negative patterns

### Control that should never ever appear under pain of infinite nyan cat

e.g. shared knowledge questions or answers, or dynamic SQL queries

## References

***

## Positive input validation
## Negative input validation
## Sanitization
## No input validation
## Web service and REST input validation

