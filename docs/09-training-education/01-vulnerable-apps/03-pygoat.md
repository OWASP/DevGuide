### 7.1.3 PyGoat

The OWASP [PyGoat project][pygoat] is an intentionally insecure web application,
and is written in python using the Django framework.
PyGoat is used to practice attacking a python-based web application in an isolated and secure environment

PyGoat is a relatively new OWASP project, its first commit was in May 2020,
and although it is presently an Incubator project it should soon gain Lab project status.

#### What is PyGoat?

The purpose of PyGoat is to give both developers and testers an isolated platform
for learning how to test applications and how to code securely.
It provides examples of traditional web application exploits that follow the OWASP Top Ten vulnerabilities,
as well as providing a vulnerable web application for further exploitation / testing.

PyGoat also provides a view of the python source code to determine where the mistake was made that caused the vulnerability.
This allows you to make changes to the web application and test whether these changes have secured it.

PyGoat can be installed from [source repository][pygoatrepo] via scripts or pip, from a [Docker hub][pygoathub] image,
or using a Docker image [built locally][pygoatdocker].

#### Why use it?

PyGoat is an easy to use demonstration and learning platform that provides a secure way to try and attack web applications.
It is less fully featured than either Juice Shop or WebGoat, and this makes it a simple and direct learning experience.
PyGoat provides example labs for the complete OWASP Top Ten (both 2021 and 2017 versions) along with explanatory notes.

PyGoat also provides a python / Django web application which complements Juice Shop's Node.js
and WebGoat's Java applications; it is important to learn how to attack all of these frameworks.

So if you are looking for a direct and easy way to start attacking a vulnerable web application
then PyGoat is one of the first to consider.

#### How to use it

The easiest way to run PyGoat is by downloading the Docker image and running it as a Docker container.
The Docker daemon will have to be running to do this, so get the Docker Engine from the [download site][dockerinstall].

Follow the instructions from the [Docker hub project][pygoathub] page:

```text
docker pull pygoat/pygoat
docker run --rm -p 8000:8000 pygoat/pygoat
```

The internal container port 8000 is mapped to external port 8000, so browse to `http://127.0.0.1:8000/login/`.

A user account needs to be set up before the labs can be accessed. This account is local to the container;
it will be deleted if the Docker container is stopped or deleted.
It can be any test account such as username 'user' and password 'Kali1234'.
To set up a user account access the login page and click on the 'Here' text within 'Click Here to register'
(it is not entirely obvious at first) and then enter the new username and password.

Once a user account has been set up then login to access the labs.
A handy feature of PyGoat is the inclusion of the 2021 version of the OWASP Top Ten as well as the 2017 version,
these are provided side by side and aid cross referencing to the latest OWASP Top Ten.

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue090103] or [edit on GitHub][edit090103].

[dockerinstall]: https://docs.docker.com/engine/install/
[edit090103]: https://github.com/OWASP/DevGuide/blob/main/draft/09-training-education/01-vulnerable-apps/03-pygoat.md
[issue090103]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2009-training-education/01-vulnerable-apps/03-pygoat
[pygoat]: https://owasp.org/www-project-pygoat/
[pygoatdocker]: https://github.com/adeyosemanputra/pygoat/blob/master/README.md#from-docker-compose
[pygoathub]: https://hub.docker.com/r/pygoat/pygoat
[pygoatrepo]: https://github.com/adeyosemanputra/pygoat/blob/master/README.md#from-sources
