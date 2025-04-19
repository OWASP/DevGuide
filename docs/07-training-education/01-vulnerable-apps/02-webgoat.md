![WebGoat logo](../../assets/images/logos/webgoat.png "OWASP WebGoat"){: style="height:180px;float:right" }

### 7.1.2 WebGoat

The OWASP [WebGoat][webgoat] project is a deliberately insecure web application that can be
used to attack common application vulnerabilities in a safe environment.
It can also be used to exercise application security tools to practice
scanning and identifying the various vulnerabilities built into WebGoat.

WebGoat is a well established OWASP project and achieved Lab Project status many years ago.

#### What is WebGoat?

WebGoat is primarily a training aid to help development teams put into practice common attack patterns.
It provides an environment where a Java-based web application can be safely attacked
without traversing a network or upsetting a website owner.

The environment is self contained using a container and this ensures attack traffic does not leak to other systems;
this traffic should look like a malicious attack to a corporate intrusion detection system and will certainly light it up.
The WebGoat container contains WebWolf, an attacker client,
which further ensures that attack traffic stays within the container.

In addition there is another WebGoat container available that includes a Linux desktop with some attack tools pre-installed.

#### Why use WebGoat?

WebGoat is one of those tools that has many uses; certainly during training but also when presenting demonstrations,
testing out security tools and so on.
Whenever you need a deliberately vulnerable web application running in a self contained and safe environment then
WebGoat is one of the first to consider.

Reasons to use WebGoat:

* Practical learning how to exploit web applications
* Ready made target during talks and demonstration on penetration testing
* Evaluating dynamic application security testing (DAST) tools; they should identify the known vulnerabilities
* Practicing penetration testing skills
* and there will be more

#### How to use WebGoat

The easiest way to run WebGoat is to use the provided Docker images to run containers.
WebGoat can also be run as a standalone Java application using the downloaded [Java Archive file][goatreleases]
or from the [source itself][goatreleases];
this requires various dependencies, whereas all dependencies are provided within the Docker images.

Access to WebGoat is via the port 8080 on the running Docker container
and this will need to be mapped to a port on the local machine.
Note that mapping to port 80 can be blocked on corporate laptops so it is suggested to map the port to localhost 8080.

1. The Docker daemon will have to be running to do this, get the Docker Engine from the [download site][dockerinstall].
2. Download the WebGoat [docker image][goatdocker] using command `docker pull webgoat/webgoat`
3. Run the container with `docker run --name webgoat -it -p 127.0.0.1:8080:8080 -p 127.0.0.1:9090:9090 webgoat/webgoat`
4. Use a browser to navigate to `localhost:8080/WebGoat` - note that there is no page served on `localhost:8080/`
5. You are then prompted to login, so first thing to do is create a test account from this login page
6. The accounts are retained when the container is stopped, but removed if the container is deleted
7. Creating insecure username/password combinations, such as 'kalikali' with 'Kali1234', is allowed

The browser should now be displaying the WebGoat lessons, such as 'Hijack a session' under 'Broken Access Control'.

#### How to use WebWolf

![WebWolf logo](../../assets/images/logos/webwolf.png "OWASP WebWolf"){: style="height:180px;float:right" }

WebWolf is provided alongside both the WebGoat docker images and the WebGoat JAR file.
WebWolf is accessed using port 9090 on the Docker container,
and this can usually be mapped to localhost port 9090 as in the example given above.

Use a browser to navigate to `http://localhost:9090/WebWolf`, there is no page served on URL `localhost:9090`.
Login to WebWolf using one of the accounts created when accessing the WebGoat account management pages,
such as username 'kalikali' and password 'Kali1234'. All going well you will now have the WebWolf home page displayed.

WebWolf provides:

* File upload area
* Email test mailbox
* JWT tools
* Display of http requests

#### Where to go from here?

Try out the WebGoat desktop environment by running `docker run -p 127.0.0.1:3000:3000 webgoat/webgoat-desktop`
and navigating to `http://localhost:3000/`.

* Try the WebGoat lessons, they will certainly inform and educate
* Exercise available attack tools against WebGoat
* Use WebGoat in demonstrations of your favorite attack chains
* Use WebGoat material in presentations on vulnerabilities

There are various ways of configuring WebGoat, see the [github repo][goatgithub] for more details.

#### References

* OWASP [WebGoat][webgoat] and WebWolf
* [Docker][dockerinstall]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue090102] or [edit on GitHub][edit090102].

[goatdocker]: https://hub.docker.com/r/webgoat/webgoat
[goatgithub]: https://github.com/WebGoat/WebGoat
[goatreleases]: https://github.com/WebGoat/WebGoat/releases
[dockerinstall]: https://docs.docker.com/engine/install/
[edit090102]: https://github.com/OWASP/DevGuide/blob/main/docs/07-training-education/01-vulnerable-apps/02-webgoat.md
[issue090102]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2007-training-education/01-vulnerable-apps/02-webgoat
[webgoat]: https://owasp.org/www-project-webgoat/
