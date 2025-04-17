### 12.1.6 Exception and Error Handling

Here is a collection of Do's and Don'ts when it comes to exception and error handling, gathered from practical experiences.
Some of these are language specific and others have more general applicability.

* Ensure that all method/function calls that return a value have proper error handling and return value checking
* Ensure that exceptions and error conditions are properly handled
* Ensure that no system errors can be returned to the user
* Ensure that the application fails in a secure manner
* Ensure resources are released if an error occurs.
* Ensure that stack trace is not thrown to the user.
* Swallowing exceptions into an empty catch() block is not advised as an audit trail
    of the cause of the exception would be incomplete
* Code that might throw exceptions should be in a try block and code that handles exceptions in a catch block
* If the language in question has a finally method, use it. The finally method is guaranteed to always be called
* The finally method can be used to release resources referenced by the method that threw the exception
* This is very important. An example would be if a method gained a database connection from a pool of connections,
    and an exception occurred without finally, the connection object shall not be returned
    to the pool for some time (until the timeout)
* This can lead to pool exhaustion. finally() is called even if no exception is thrown
* Handle errors and exception conditions in the code
* Do not expose sensitive information in user sessions
* When working with a multi-threaded or otherwise asynchronous environment,
    ensure that proper locking APIs are used to lock before the if statement;
    and unlock when it has finished.
* Types of errors:
  * The result of business logic conditions not being met
  * The result of the environment wherein the business logic resides fails
  * The result of upstream or downstream systems upon which the application depends fail
  * Technical hardware / physical failure
* Failures are never expected, but they do occur.
    In the event of a failure, it is important not to leave the "doors" of the application open
    and the keys to other "rooms" within the application sitting on the table.
    In the course of a logical workflow, which is designed based upon requirements,
    errors may occur which can be programmatically handled,
    such as a connection pool not being available, or a downstream server not being contactable
* This is a very tricky guideline.
    To fail securely, areas of failure should be examined during the course of the code review.
    It should be examined if all resources should be released in the case of a failure
    and during the thread of execution if there is any potential for resource leakage,
    resources being memory, connection pools, file handles etc
    Include a statement that defaults to safe failure
* The review of code should also include pinpointing areas where the user session should be terminated or invalidated.
Sometimes errors may occur which do not make any logical sense from a business logic perspective
or a technical standpoint;
    e.g: ""A logged in user looking to access an account which is not registered to that user
    and such data could not be inputted in the normal fashion."""
* Examine the application for 'main()' executable functions and debug harnesses/backdoors
    In their basic form, backdoors are user id / password combination with the required privileges, embedded in the code,
    which can be used later on by the developer to get into the system without having to request for login credentials
* Search for commented out code, commented out test code, which may contain sensitive information
* Search for any calls to the underlying operating system or file open calls and examine the error possibilities

#### Logging

* Ensure that no sensitive information is logged in the event of an error
* Ensure the payload being logged is of a defined maximum length and that the logging mechanism enforces that length
* Ensure no sensitive data can be logged; E.g. cookies, HTTP GET method, authentication credentials
* Examine if the application will audit the actions being taken by the application on behalf of the client
    (particularly data manipulation/Create, Read, Update, Delete (CRUD) operations)
* Ensure successful and unsuccessful authentication is logged
* Ensure application errors are logged
* Examine the application for debug logging with the view to logging of sensitive data
* Ensure change in sensitive configuration information is logged along with user who modified it.
    Ensure access to secure storage areas including crypto keys are logged
* Credentials and sensitive user data should not be logged
* Does the code include poor logging practice of not declaring Logger object as static and final?
* Does the code allow entering invalidated user input to the log file?
* Capture following details for the events:
  * User identification
  * Type of event
  * Date and time
  * Success and failure indication
  * Origination of event
  * Identity or name of affected data, system component, resource, or service (for example, name and protocol)
* Log file access, privilege elevation, and failures of financial transactions
* Log all administrators actions. Log all actions taken after privileges are elevated - `runas` / `sudo`
* Log all input validation failures
* Log all authentication attempts, especially failures
* Log all access control failures
* Log all apparent tampering events, including unexpected changes to state data
* Log attempts to connect with invalid or expired session tokens
* Log all system exceptions
* Log all administrative functions, including changes to the security configuration settings
* Log all backend TLS connection failures
* Log cryptographic module failures
* Use a cryptographic hash function to validate log entry integrity

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue140106] or [edit on GitHub][edit140106].

[edit140106]: https://github.com/OWASP/www-project-developer-guide/blob/main/draft/14-appendices/01-implementation-dos-donts/06-exception-error-handling.md
[issue140106]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%20/14-appendices/01-implementation-dos-donts/06-exception-error-handling
