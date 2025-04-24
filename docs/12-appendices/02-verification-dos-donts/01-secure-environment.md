Here is a collection of Do's and Don'ts when it comes to creating a secure environment, gathered from practical experiences.
Some of these are language specific and others have more general applicability.

* The WEB-INF directory tree contains web application classes, pre-compiled JSP files, server side libraries,
    session information, and files such as `web.xml` and `webapp.properties`.
    So be sure the code base is identical to production.
    Ensuring that we have a “secure code environment” is also an important part of
    an application secure code inspection.
  
* Use a “deny all” rule to deny access and then grant access on need basis.
  
* In Apache HTTP server, ensure directories like WEB-INF and META-INF are protected.
    If permissions for a directory and subdirectories are specified in `.htaccess` file,
    ensure that it is protected using the “deny all” rule.
  
* While using Struts framework, ensure that JSP files are not accessible directly
    by denying access to `*.jsp` files in `web.xml`.
  
* Maintain a clean environment. remove files that contain source code but are not used by the application.
  
* Ensure production environment does not contain any source code / development tools
    and that the production environment contains only compiled code / executables.
  
* Remove test code / debug code (that might contain backdoors).
    Commented code can also be removed as at times, it might contain sensitive data. Remove file metadata e.g., .git
  
* Set “Deny All” in security constraints (for the roles being set up)
    while setting up the application on the web server.
  
* The listing of HTTP methods in security constraints works in a similar way to deny-listing.
    Any verb not explicitly listed is allowed for execution. Hence use “Deny All”
    and then allow the methods for the required roles.
    This setting carries weightage while using “Anonymous User” role.
    For example, in Java, remove all `<http-method>` elements from `web.xml` files.
  
* Configure web and application server to disallow HEAD requests entirely.
  
* Comments on code and Meta tags pertaining to the IDE used or technology used to develop the application
    should be removed. Some comments can divulge important information regarding bugs in code
    or pointers to functionality. This is particularly important with server side code such as JSP and ASP files.
  
* Search for any calls to the underlying operating system or file open calls and examine the error possibilities.
  
* Remove unused dependencies, unnecessary features, components, files, and documentation.
  
* Only obtain components from official sources over secure links.
    Prefer signed packages to reduce the chance of including a modified, malicious component
  
* Monitor for libraries and components that are unmaintained or do not create security patches for older versions.
    If patching is not possible, consider deploying a virtual patch to monitor, detect,
    or protect against the discovered issue.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue140201] or [edit on GitHub][edit140201].

[edit140201]: https://github.com/OWASP/DevGuide/blob/main/docs/12-appendices/02-verification-dos-donts/01-secure-environment.md
[issue140201]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2012-appendices/02-verification-dos-donts/01-secure-environment
