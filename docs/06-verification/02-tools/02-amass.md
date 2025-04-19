### 6.2.2 Amass

The OWASP Amass is a tool that provides  attack surface management for an organization's web sites and applications.
It used during penetration testing for network mapping of attack surfaces
and external asset discovery by integrating various existing security tools.

The Amass [breaker/tool project][amass] is an OWASP Flagship Project and installers can be
downloaded from the project's github repository [release area][amass-download].

#### What is Amass?

Amass is a command line tool that provides information on an organization's web sites,
using various open source information gathering tools and active reconnaissance techniques.

It is run from the command line with [subcommands][amass-docs] :

1. 'amass intel' collects intelligence on the target organization
2. 'amass enum' performs DNS enumeration and network mapping to populate the results database
3. 'amass db'

Each command comes with a wide set of options that controls the tools used and the format of the findings.

#### Why use it?

Amass is an important tool for security test teams. Amass is included in the [Kali Linux][kali] distribution,
which is widely used by penetration testing teams, with Amass providing a straightforward way
of running a wide set of reconnaissance and enumeration tools.

In addition Amass is an easily used tool that is available to both legitimate test teams and malicious actors.
It is very likely that any given organization has been scanned and enumerated by Amass at some point,
either maliciously or legitimately,
so it is important that the tool is run to determine what information a malicious actor can obtain.

#### How to use it

If [Kali Linux][kali] is being used then Amass comes ready installed,
otherwise a wide set of [installers][amass-install] is provided for other platforms.

The extensive [Amass tutorial][amass-tutorial] provides the best way of learning to use Amass and its features.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue080202] or [edit on GitHub][edit080202].

[amass]: https://owasp.org/www-project-amass/
[amass-docs]: https://github.com/owasp-amass/amass/blob/master/doc/user_guide.md
[amass-download]: https://github.com/owasp-amass/amass/releases
[amass-install]: https://github.com/owasp-amass/amass/blob/master/doc/install.md
[amass-tutorial]: https://github.com/owasp-amass/amass/blob/master/doc/tutorial.md
[edit080202]: https://github.com/OWASP/DevGuide/blob/main/docs/06-verification/02-tools/02-amass.md
[issue080202]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/02-tools/02-amass
[kali]: https://www.kali.org/
