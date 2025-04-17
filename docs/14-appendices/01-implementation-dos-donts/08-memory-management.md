### 12.1.8 Memory Management

Here is a collection of Do's and Don'ts when it comes to memory management, gathered from practical experiences.

* Check that the buffer is as large as specified
* When using functions that accept a number of bytes to copy, such as `strncpy()`,
    be aware that if the destination buffer size is equal to the source buffer size,
    it may not NULL-terminate the string
* Check buffer boundaries if calling the function in a loop and make sure there is no danger
    of writing past the allocated space
* Truncate all input strings to a reasonable length before passing them to the copy and concatenation functions
* Specifically close resources, do not rely on garbage collection. (for example connection objects, file handles, etc.)
* Properly free allocated memory upon the completion of functions and at all exit points.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue140108] or [edit on GitHub][edit140108].

[edit140108]: https://github.com/OWASP/www-project-developer-guide/blob/main/draft/14-appendices/01-implementation-dos-donts/08-memory-management.md
[issue140108]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2014-appendices/01-implementation-dos-donts/08-memory-management
