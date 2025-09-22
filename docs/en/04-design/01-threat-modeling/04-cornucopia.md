![Cornucopia logo](../../../assets/images/logos/cornucopia.png "OWASP Cornucopia"){ align=right width=180 }

OWASP Cornucopia is a mechanism in the form of a card game to assist software development teams identify security
requirements in Agile, conventional and formal development processes. It is language, platform and technology-agnostic.
The idea behind Cornucopia is to help development teams, especially those using Agile methodologies, to identify application
security requirements and develop security-based user stories.
[Cornucopia][cornucopia] is an OWASP production project. The cards can be [downloaded][cornucopia-cards] and printed or
[bought online][online] from its website.
It is also possible to play OWASP Cornucopia online using the cornucopia game engine called [Copi][copi]. Using the
[online game engine][copi], it is possible to play:

* [OWASP Cornucopia Website App][start-game] to gamify threat modeling and requirement analysis for website apps
* [OWASP Cornucopia Mobile App][start-game] to gamify threat modeling and requirement analysis for mobile apps
* [Elevation of Privilege][eop] to do general threat modeling
* [Elevation of MLSec][mlsec] for threat modeling applications that uses machine learning or Gen AI
* [OWASP Cumulus][cumulus] for threat model cloud infrastructure

#### What is Cornucopia?

Cornucopia provides a [set of cards][cornucopia-browser] designed to gamify threat modeling activities,
helping agile development teams to identify weaknesses in applications and then record remediations or requirements.

There are three versions of the Cornucopia deck of threat modeling cards:

* Website App Edition
* Mobile App Edition
* Enterprise App Edition (legacy)

The decks come with several suits according to the application, and always contain an overall 'Cornucopia' suit.

Cornucopia can be played in many different ways, there is no one way,
and there is a suggested [set of rules][cornucopia-play] to start the game off.
Cornucopia provides a [score sheet][cornucopia-score] to can help keep track of the game session and to record outcomes.

#### Website App Edition

Each card in the Website App deck describes a common error or anti-pattern that allows systems to be vulnerable to attack.
Vulnerabilities are arranged in domains as five suits with the additional Cornucopia suit ranging across these domains:

* Data Validation and Encoding
* Authentication
* Session Management
* Authorization
* Cryptography
* Cornucopia

To provide context the Cornucopia Website App cards reference other projects:

* OWASP Application Security Verification Standard ([ASVS][asvs])
* OWASP Developer Guide ([Web Application Checklist][devguide])
* STRIDE
* MITRE's Common Attack Pattern Enumeration and Classification ([CAPEC][capec])
* [SAFEcode][safecode]

#### Mobile App Edition

Similarly to the website application deck, the mobile application deck has five domains/suits,
with Cornucopia cross domain:

* Platform and Code
* Authentication and Authorization
* Network and Storage
* Resilience
* Cryptography
* Cornucopia

For context the Cornucopia Mobile App cards reference these other projects:

* OWASP Mobile Application Security Verification Standard ([MASVS][masvs])
* OWASP Mobile Application Security Testing Guide ([MASTG][mastg])
* MITRE's Common Attack Pattern Enumeration and Classification ([CAPEC][capec])
* [SAFEcode][safecode]

#### Ecommerce Website Edition

This is the original Cornucopia deck and has the same domains/suits, including the Cornucopia cross domain suit,
as the Website App Edition. Some of the vulnerabilities are specific to Ecommerce,
but it references the same projects as the website edition.

#### Why use it?

Cornucopia is useful for both requirements analysis and threat modeling,
providing gamification of these activities within the development lifecycle.
It is targeted towards agile development teams and provides a different perspective to these tasks.

The outcome of the game is to identify possible threats and propose remediations.

#### How to use Cornucopia

The OWASP Spotlight series provides an excellent overview of Cornucopia and how it can be used for gamification:
'Project 16 - [Cornucopia][spotlight16]'. [Videos on the OWASP Cornucopia website][cornucopia-play] also demonstrate several
ways the game can be utilized.

Ideally Cornucopia is played in person using physical cards,
with the development team and security architects in the same room.
The application should already have been described by an architecture diagram or data flow diagram
so that the players have something to refer to during the game.

The suggested order of play is:

1. Pre-sort: the deck, some cards may not be relevant for the web application
2. Deal: the cards equally to the players
3. Play: the players take turns to select a card
4. Describe: the player describes the possible attack using the card played
5. Convince: the other players have to be convinced that the attack is valid
6. Score: award points for a successful attack
7. Follow suit: the next player has to select a card from the same suit
8. Winner: the player with the most points
9. Follow up: each valid threat should be recorded and acted upon

Remember that the outcome of the game is to identify possible threats and propose remediations,
as well as having a good time.

#### References

* Application Security Verification Standard, [ASVS][asvs]
* Common Attack Pattern Enumeration and Classification, [CAPEC][capec]
* [Cornucopia][cornucopia]
* Mobile Application Security Verification Standard, [MASVS][masvs])
* Mobile Application Security Testing Guide, [MASTG][mastg])
* [SAFEcode][safecode]
* [Spotlight][spotlight16] on Cornucopia
* OWASP Developer Guide ([Web Application Checklist][devguide])

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue060104] or [edit on GitHub][edit060104].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[capec]: https://capec.mitre.org/
[cornucopia]: https://cornucopia.owasp.org
[cornucopia-browser]: https://cornucopia.owasp.org/cards
[cornucopia-cards]: https://cornucopia.owasp.org/printing#Current-printable-version
[cornucopia-score]: https://owasp.org/www-project-cornucopia/assets/files/Cornucopia-scoresheet.pdf
[cornucopia-play]: https://cornucopia.owasp.org/how-to-play
[copi]: https://copi.owasp.org
[cumulus]: https://github.com/OWASP/cumulus
[eop]: https://github.com/adamshostack/eop
[edit060104]: https://github.com/OWASP/DevGuide/blob/main/docs/en/04-design/01-threat-modeling/04-cornucopia.md
[issue060104]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2004-design/01-threat-modeling/04-cornucopia
[mastg]: https://mas.owasp.org/MASTG/
[masvs]: https://mas.owasp.org/MASVS/
[mlsec]: https://github.com/kantega/elevation-of-mlsec
[online]: https://cornucopia.owasp.org/webshop
[safecode]: https://safecode.org/
[devguide]: https://devguide.owasp.org/en/04-design/02-web-app-checklist
[spotlight16]: https://youtu.be/NesxjEGX58s
[start-game]: https://copi.owasp.org/games/new
