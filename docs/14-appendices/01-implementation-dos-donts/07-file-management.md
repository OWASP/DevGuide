## 12.1.7 File Management

Here is a collection of Do's and Don'ts when it comes to file management, gathered from practical experiences.

* Validate all filenames and directories before use, ensuring that there are no special characters
    that might lead to accessing an unintended file
* Use safe directories for all file access except those initiated by the end user
    e.g. document saving and restoring to a user-chosen location
* Use a sub-domain with one way trust for the downloaded files.
    Such that any compromise of the sub-domain does not impact the main domain.
    Do not save files in the same web context as the application.
    Files should either go to the content  server or in the database
* Have at least 64 bits of randomness in all temporary file names
* where applicable, require authentication before allowing a file to be uploaded
* Limit the type of files that can be uploaded to only those types that are needed for business purposes
* Validate uploaded files are the expected type by checking file headers
* Prevent or restrict the uploading of any file that may be interpreted by the web server
* Turn off execution privileges on file upload directories
* Implement safe uploading in UNIX by mounting the targeted file directory as a logical drive
    using the associated path or the chrooted environment
* When referencing existing files, use an allow list of allowed file names and types.
    Validate the value of the parameter being passed and if it does not match one of the expected values,
    either reject it or use a hard coded default file value for the content instead
* Do not pass user supplied data into a dynamic redirect.
    If this must be allowed, then the redirect should accept only validated, relative path URLs
* Do not pass directory or file paths, use index values mapped to pre-defined list of paths
* Never send the absolute file path to the client
* Ensure application files and resources are read-only
* Scan user uploaded files for viruses and malware

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue140107] or [edit on GitHub][edit140107].

[edit140107]: https://github.com/OWASP/DevGuide/blob/main/draft/14-appendices/01-implementation-dos-donts/07-file-management.md
[issue140107]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%20/14-appendices/01-implementation-dos-donts/07-file-management
