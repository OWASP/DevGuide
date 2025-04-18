### 7.2 Secure Coding Dojo

The OWASP [Secure Coding Dojo][codedojo-project] is a platform for delivering
secure coding training to software development teams.
Secure Coding Dojo is an OWASP Lab project and has been continuously supported and developed since 2017.

#### What is the Secure Coding Dojo?

The aim of Secure Coding Dojo is to teach developers how to recognize security flaws during code reviews.

The training platform has a set of training lessons and also blocks of code where the developer has to identify
which block of code is written in an insecure way.
A leader board is provided for the development teams to track their progress.

Each lesson is built as an attack/defense pair.
The developers can observe the software weaknesses by conducting the attack
and after solving the challenge they learn about the associated software defenses.
The predefined lessons are based on the MITRE most dangerous software errors (also known as SANS 25)
so the focus is on software errors rather than attack techniques.

The training platform can be customized to integrate with custom vulnerable websites and other CTF challenges.

#### Why use it?

Development teams are often required to have Secure Coding training, and this may be an annual compliance requirement.
The Secure Coding Dojo provides this compliant training in reviewing software
for security bugs in representative source code.

#### How to use it

The OWASP Spotlight series provides an overview of the developer training provided by the Secure Coding Dojo:
'Project 14 - [OWASP Secure Coding Dojo][spotlight14]'.

There is a [demonstration site][codedojo] for Secure Coding Dojo which provides access to the
training modules, code blocks and a public leader board.
Note that the demonstration site does not provide the deliberately insecure web sites, such as the 'Insecure.Inc' Java site,
because this would encourage attack traffic across a public network.

Ideally Secure Coding Dojo is deployed by the organization providing the training, rather than by using the demo site,
because development teams can then log in securely to the Dojo.
Deployment is [straight forward][codedojo-install],
consisting of cloning the repository and running `docker-compose` with environment variables.
This also allows deployment of the associated deliberately [insecure web site][codedojo-insecure]
to practice penetration testing.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0902] or [edit on GitHub][edit0902].

[codedojo]: https://securecodingdojo.owasp.org/
[codedojo-insecure]: https://github.com/OWASP/SecureCodingDojo/wiki/Running-Insecure.Inc
[codedojo-install]: https://github.com/OWASP/SecureCodingDojo/wiki/Deploying-with-Docker
[codedojo-project]: https://owasp.org/www-project-secure-coding-dojo/
[edit0902]: https://github.com/OWASP/DevGuide/blob/main/docs/09-training-education/02-secure-coding-dojo.md
[issue0902]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2009-training-education/02-secure-coding-dojo
[spotlight14]: https://youtu.be/7nVkDkL9cyE
