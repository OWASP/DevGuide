### Release process

The [web document][latest] is always the latest version that has been accepted via the pull request process.

If major or significant minor changes are made then it is good to tag this with a semantic version, such as `4.1.8`.

To do this:

1. Ensure that all pull-requests are up to date
2. navigate to the [release area][release]
3. Click on the 'Draft a new release' button to create a [new release][new-release]
4. Choose a tag, for example `v4.1.8` and select target branch to be 'main'
5. Provide the release title, such as 'Version 4.1.8'
6. Describe the release in the Description, consider including the text below
7. Obtain the latest PDF file form the latest (successful) [commit action][commits]
8. Upload this PDF file to the draft release
9. Ensure 'Set as the latest release' is selected
10. Apply 'Publish release'
11. Announce on Slack channel
12. Announce on Blue Sky channel


```
Contact the current [leaders][leaders] for any queries about this version.

The [PDF][pdf-guide] version of the [web document][devguide] can be downloaded for version 4.1.8 .

[devguide]: devguide.owasp.org
[leaders]: https://github.com/OWASP/www-project-developer-guide/blob/main/leaders.md
[pdf-guide]: https://github.com/OWASP/threat-dragon/releases/download/v4.1.8/OWASP_Developer_Guide-V4.1.8.pdf
```

----

OWASP DevGuide: _accessible security for developers_

[commits]: https://github.com/OWASP/DevGuide/actions/workflows/ci.yaml
[latest]: https://devguide.owasp.org/
[new-release]: https://github.com/OWASP/DevGuide/releases/new
[release]: https://github.com/OWASP/DevGuide/releases
