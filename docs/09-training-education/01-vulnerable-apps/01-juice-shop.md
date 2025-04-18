![Juice Shop logo](../../assets/images/logos/juiceshop.png "OWASP Juice Shop"){: style="height:180px;float:right" }

### 7.1.1 Juice Shop

The OWASP flagship project [Juice Shop][juice] is a deliberately insecure web application.
Juice Shop encompasses vulnerabilities from the entire OWASP Top Ten
along with many other security flaws found in real-world applications.

#### What is Juice Shop?

Juice Shop is an Open Source web application that is free to download and use, and is intentionally insecure.
It is easy to get started with Juice Shop; it includes [Hacking Instructor scripts][juicetutorial]
with an optional tutorial mode to guide newcomers through several challenges
while explaining the underlying vulnerabilities.

Juice Shop is easily installed using a [Docker image][juicedocker]
and runs on Windows/Mac/Linux as well as all major cloud providers.
There are various ways to run Juice Shop:

* [From source](https://hub.docker.com/r/bkimminich/juice-shop#from-sources)
* [Packaged Distributions](https://hub.docker.com/r/bkimminich/juice-shop#packaged-distributions)
* [Docker Container](https://hub.docker.com/r/bkimminich/juice-shop#docker-container)
* [Vagrant](https://hub.docker.com/r/bkimminich/juice-shop#vagrant)
* [Amazon EC2 Instance](https://hub.docker.com/r/bkimminich/juice-shop#amazon-ec2-instance)
* [Azure Container Instance](https://hub.docker.com/r/bkimminich/juice-shop#azure-container-instance)
* [Google Compute Engine Instance](https://hub.docker.com/r/bkimminich/juice-shop#google-compute-engine-instance)

Juice Shop is written in JavaScript using Node.js, Express and Angular.

#### Why use it?

Juice Shop has several uses:

* As the basis for security training programs, with integration for other training systems via a [WebHook][webhook]
* As practice for pentesters and hackers, including many built in coding challenges
* To provide awareness demos, with customizable rebranding for specific corporations or customers
* Support for [Capture the Flag][juicectf] (CTF) events using flag codes
* As a guinea pig for security tools

For example pentesting proxies or security scanners can use Juice Shop as a 'guinea pig' application
to check how well their tools cope with JavaScript-heavy application frontends and REST APIs.

#### How to use it

There is no 'one way' to use Juice Shop, and so a good starting point is the overview of Juice Shop
provided by the OWASP Spotlight series: 'Project 25 - [OWASP Juice Shop][spotlight25]'.

Get started by [downloading][juicedocker] and installing the Docker image.
The Docker daemon will have to be running to do this; get the Docker Engine from the [download site][dockerinstall].

```text
docker pull bkimminich/juice-shop
docker run --rm -p 3000:3000 bkimminich/juice-shop
```

Using a browser access `http://localhost:3000/#/` and note that you are now interacting with a deliberately insecure
'online' shopping web application, so be suspicious of everything you see :)

Once Juice Shop is running the next step is to follow the [Official Companion Guide][juiceguide]
that can be downloaded from the Juice Shop shop.
This guide provides overviews of each Juice Shop application vulnerability
and includes hints on how to spot and exploit them.
In the appendix there is a complete step-by-step solution to every challenge for when you are stuck or just curious.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue090101] or [edit on GitHub][edit090101].

[dockerinstall]: https://docs.docker.com/engine/install/
[edit090101]: https://github.com/OWASP/DevGuide/blob/main/docs/09-training-education/01-vulnerable-apps/01-juice-shop.md
[issue090101]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2009-training-education/01-vulnerable-apps/01-juice-shop
[juice]: https://owasp.org/www-project-juice-shop/
[juicectf]: https://owasp.org/www-project-juice-shop/#div-ctf
[juicedocker]: https://hub.docker.com/r/bkimminich/juice-shop
[juiceguide]: https://owasp.org/www-project-juice-shop/#div-ecosystem
[juicetutorial]: https://owasp.org/www-project-juice-shop/#div-learning
[webhook]: https://pwning.owasp-juice.shop/companion-guide/latest/part4/integration.html#_challenge_solution_webhook
[spotlight25]: https://youtu.be/--50rE76EeA
