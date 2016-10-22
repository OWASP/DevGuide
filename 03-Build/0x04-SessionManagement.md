Assigned to LB

## Overview
Session management is required to track the state of a user's journey through a web application. It is the role of a developer/designer to create or use a session management system in a way that is secure, avoiding the leaking of this
information to an attacker, leading to common attack vectors such as replay of state, forging state or intercepting the state of another user.

## Introduction
The web, by design, is stateless. In its original use case, a request would be made e.g. GET, PUT, DELETE and once the action had occurred, the protocol was complete, the previous state of the system was unknown and unimportant. Naturally,
as more complex applications have developed, it is rarely possible to create a stateless web application. As well as knowing who the user is, by means of Authentication, it is common to want to know where the user has been or is going and
whether they have done anything in the process e.g. added an item to a shopping basket, so that this information can be used at a later date. Session management is concerned with how this data is linked to the user securely and how it is
stored and ultimately used or deleted.

Although session management might be seen as a dangerous vulnerability to a web application, it can also be dangerous to try and avoid session completely, since that is more likely to cause secret information being passed in URLs or hidden fields.
It also runs counter to security best-practice which is to keep something simple in order to make mistakes easier to see or find. A correctly managed session system is not a security vulnerability any more than correctly filtered inputs or
correctly used encryption. Another objection that session is resource-intensive is not generally true, but that depends on correctly designing the content of your session data and not simply storing everything in the session. Data can be stored in
the main database or in some restricted cases, in the cookies.

### Types of Attack Vector
In its most simple (and insecure) form, a session management system might simply associate a cookie with a userid and store any session data into this cookie, which would then be sent to the web client and returned to the server on subsequent
requests. This example can demonstrate the common types of attack vectors in session management. Firstly, imagine the userid and whether they are logged in are stored in the cookie. An attacker hijacks the session simply by creating a local cookie
with their target userid and a logged in flag and then visits a page on the site, they are immediately logged in to another user's account - a simple session hijack. Secondly, imagine the type of user was stored in this session cookie (user or administrator). An attacker can easily
change their user type and get elevated privileges - a session forgery. In fact, it is common for session data to be stored on the server but there still needs to exist a link between this stored data and the user who is performing the request,
which is most commonly achieved with a session cookie recording a single identity value which is then mapped onto the session data on the server. This identity will be sent in the cookie with each request but this in itself can lead to potential
weaknesses including access of this session value via malicious JavaScript or a man-in-the-middle who can read and then re-use the session ID in another browser.

### Using a Framework
In most cases, a web application will (and generally should) use a framework. These frameworks should all include their own session management system but in the world of security, we should not automatically trust that these systems are implemented
correctly. They might be partially complete, have a bug or perhaps have not been updated recently. Also, we must remember that frameworks are usually designed to meet the widest range of needs and not necessarily the most secure implementation. It
is essential that designers or developers investigate their chosen framework in line with the information contained in this document to ensure that best practice is followed and there are no differences between the security requirements of your application
and the actual framework implementation.

In some cases, your chosen framework might not contain a session management system or perhaps you are not using a framework at all. In general, this must be considered poor security practice since one of the best weapons in the security battle is to
have a lot of public exposure to a system to prove that it is reliable and secure. Writing your own system or trying to improve a poor implementation is theoretically possible but carries risk depending on your ability to correctly identify and mitigate all of the
potential weaknesses.

## Elements of Secure Session Management
#### Cryptographically secure session identifier generation
As mentioned previously, it is common to store session data on the server and to generate a session identifier to store in a cookie. If this session identifier is not cryptographically secure (such as just using the userid of the current user) or is not suitably
random, such as incrementing a number, then the session identifier is easy to guess and the session easy to hijack by an attacker. A good session management system will generate a cryptographically secure value for a session identifier. For example, ASP.Net uses
a 24 character alphanumeric identifier (which will be web safe, as opposed to a binary value).

#### Where to store the session data
Although it is possible to store almost any session data in a cookie, this is not recommended and for any authorization type information should never be done. Security is best handled on a server, not decided by the contents of a small text file which is easy
to see and modify. It is preferable to only store the session id in the cookie and store the remaining data either in a database at the server-side or in memory on the web server. There are performance and cost considerations to these choices, depending on the number
of users on the system and how much data is stored in the session. There are also special considerations if you are using a web server farm due to the memory not being shared. In these cases, if you want to use a memory-based session, you need to use some type of
shared memory or a mechanism provided by your hosting provider for this purpose.

#### What to store in the session
One of the ways to reduce the burden on the session storage is to only keep the minimum amount of information in the session that you need to. For instance, a language choice might be kept in a cookie to keep it away from the server and based on the fact that it
is neither secret or dangerous if it was tampered with. Certain data can also be stored in the URL e.g. the current ordering of a gridview since, again, it is generally not secret and should probably not be kept in a session. Anything that is kept in hidden fields
on a page is actually visible to anyone who looks. If this data is secret, you should either keep it stored in the session or in a related database table.

#### HTTP Only Cookies
A session cookie in any good framework should default to setting an HTTPOnly flag. This tells the browser that the cookie cannot be accessed by JavaScript to read the session of another user who has somehow got malware script running in a site they are visiting.

#### SSL Only Flag
It is also recommended, wherever possible, to set the Secure flag on the cookie which enforces that the cookie is only allowed to be downloaded via HTTPS. This will only work if your site implements SSL/TLS but prevents a man-in-the-middle being able to read the contents of the cookie.

#### CSRF Tokens
One of the weaknesses inherent in most session systems is that tabs in a browser share session and it is therefore possible for an attacker to take a victim to a malicious site, which will then call an operation on a vulnerable target site. This visit to the target site will automatically send any relevant cookie/session data and if this in itself is enough to do something dangerous (transfer money, extract data etc.) then the attack has succeeded without the victim necessarily knowing. This is called a Cross-Site Request Forgery (CSRF).

A straight-forward way to stop this involves creating a page-unique token which is stored on the server against the session id. This unique token is stored in the page that the user requests and would be sent back as part of the next site request. If a malicious site accessed the same site, although the cookie (and session) information would be available, the unique token would not since it is embedded in another page. The site would then recognize that there is no CSRF token present (or it does not match the previous one linked to the session) and would fail validation. Most modern frameworks support this feature.

#### Logging and audit
One of the most important but sometimes least appreciated systems is related to logging and audit. If your organisation is unfortunate to suffer some kind of attack, one of the ways in which it can be mitigated is being able to supply law enforcement with useful data to catch the attacker as well as seeing things happening that are unusual, which might warn you of an attack that is pending. The worst case is not knowing what has happened and why and therefore not being able to prevent it happening again. Reputation is important in business and being able to deal with attacks professionally by collecting a good amount of data is important. Please see the chapter on logging for more information.

## Testing for Risks
The following sections describe specific attack vectors against your site session management system and tell you how to test for the vulnerability and how to fix it, should it exist. It should be noted that some of the fixes are simply options on your session management system, whereas others will affect higher-level parts of your system design and should be considered before your application is written, to avoid the potential difficulty of retro-fitting these controls afterwards.

### Session Token Transmission
If a session token is captured in transit through network interception, a web application account is then trivially prone to a replay or hijacking attack. Typical web encryption technologies include but are not limited to Secure Sockets Layer (SSL) and Transport Layer Security (TLS) protocols in order to safeguard the state mechanism token. A variation on this vulnerability means that a man-in-the-middle could intercept the session id and interact directly with the server to perform additional operations without the knowledge of the user.
#### Applies to frameworks
All frameworks are potentially at risk
#### How to determine if you are vulnerable
Visit a page on your site and/or login to cause the system to create a new session. Using your browser developer tools, view the cookies for the site and find the session cookie. If it is not marked as secure and your site url is not https then you are vulnerable. Alternatively, if you know your site does not support SSL/TLS at all, then you are also vulnerable.
#### How to protect yourself
Set up SSL/TLS on your web server and set the Secure flag on your session cookie. Verify the fix by visiting your site, causing it to create a session cookie and using your developer tools to ensure the Secure flag is checked proving that the browser has downloaded the cookie on a secure connection.

### Weak Session Cryptographic Algorithms
If your session i.d. is generated in a predictable way, it is possible for an attacker to guess an id that relates to another session and potentially hijack that other session.
#### Applies to frameworks
Generally applies to older frameworks. Does NOT apply to latest .Net frameworks or PHP frameworks that use the built-in PHP session functions.
#### How to determine if you are vulnerable
Determine a way to obtain 1000 ids within a short period of time and plot these on a graph as numbers to determine if there is a pattern. Alternatively, research your session id generation framework/function to see whether it is known to be cryptographically secure.
#### How to protect yourself
In general, you should not create a generation function yourself but prefer to use an alternative library/framework or update your framework to a later version that does use a secure generation protocol. A secure function will use a recognized source of randomness and optionally tie the id to the client ip address and/or a CSRF token.

### Lack of Session ID Keyspace or Entropy
Even if the generation of a session id is cryptographically strong, if the output is restricted to a short number of bits or is restricted to, for instance, integers only, then the session is still potentially brute-forcible.
#### Applies to frameworks
Generally applies to older or homemade frameworks. Does NOT apply to the latest .Net framework or PHP frameworks that use the built-in session functions.
#### How to determine if you are vulnerable
Either research your framework to determine how strong the keyspace and entropy is or generate multiple session keys and ensure they are at least 20 alpha-numeric characters. Use a tool like Brutus to attempt to brute-force session ids if you cannot determine directly whether your application is vulnerable.
#### How to protect yourself
As with any legacy weaknesses, prefer to use another framework/library or to upgrade your framework to the latest version. It is not generally recommended to produce your own session id generation function, since you will lack the exposure and experience that has been applied to publically available frameworks.


### Lack of session timeout
Any session that does not have a suitably low session time out can create an attack vector on the application. Since many end-users will forget to log out and especially in shared computer environments, the longer the session is allowed to remain active, the more time an attacker has to attempt an attack. “Remember me” functionality is particularly susceptible to this vulnerability, if it allows privileged access to the application without any further checks.
#### Applies to frameworks
Does NOT generally apply to newer frameworks by default but applications can be made vulnerable if session features are added to enhance the user experience!
#### How to determine if you are vulnerable
An application that uses any kind of trick to automate extending the user session is vulnerable.
An application that has a “remember me” function is potentially vulnerable.
A faulty or extensive session timeout can be checked easily by logging in, taking a lunch break and then attempting to continue using the application. If you are allowed to, your application is vulnerable.
#### How to protect yourself
Set the idle timeout for your application to between 5 and 20 minutes and ENSURE that it works by testing it. For the most protected applications, do not auto-extend the session and do not use “Remember Me” functionality. On lower risk applications, ensure that “Remember Me” is a convenience to only remember certain low-value information, such as auto-populating an email text box and does not remember e.g. a login unless you have fully risk-assessed what value that would have to an attacker.

### Regeneration of Session Tokens
If a session token is kept alive for an extended period of time, even if the user is actively using the site, it extends the window that an attacker has to brute-force a specific user or to attempt to replay a previous action using the stolen session id. By recreating session ids regularly, these types of attack are mitigated.
#### Applies to frameworks
Applies to all frameworks
#### How to determine if you are vulnerable
Either research your framework to determine its default or optional regeneration functionality or stay actively logged into a site for an hour (ensure the session doesn’t expire) and see whether the session id ever changes.
#### How to protect yourself
If possible, regenerate tokens, either after a number of requests from a single user e.g. 30 requests = regenerate or if the traffic is lower, then after a fixed period of time e.g. 20 minutes.


### Persistent Session Tokens
Even if your application uses session tokens to store its session, these are only destroyed when the browser is closed. In the case of shared environments, this is not necessarily true and if not done can expose a valid session id to an attacker.
#### Applies to frameworks
Applies to all frameworks
#### How to determine if you are vulnerable
Login to the application and check the session id. Logout and then using the browser developer tools, check to see whether the session cookie is still present with the same session id. Check to see whether other non-session id data has been removed from the cookie (if used). Any residual data or the same session id being present means your application is vulnerable
#### How to protect yourself
When the user logs out, destroy the session, with all its data and if possible, overwrite the session cookies with a newly generated (but useless) session id.


### Session id Validation
Since many systems are designed to work correctly with the correct data, they don’t always fail in a predictable way when incorrect data is used. For instance, if a malformed session id is sent to the server and the server is not coded correctly, the logic for checking the session might break and either allow access to another session or cause some other kind of data leakage or error.
#### Applies to frameworks
Generally applies to older or homemade frameworks.
#### How to determine if you are vulnerable
A direct code inspection is most helpful to find out if and how the session id is validated before it is used to lookup a session. If this is not possible, various tests should be made by passing invalid session ids to the application being tested to ensure that the system behaves in a desired way, either recreating a valid id or displaying an error. These tests should include but not be limited to session ids that are too long, too short, have unexpected characters in, are only one character long or have unusual characters such as the NULL character (0x0) or other control characters.
#### How to protect yourself
Use a framework or library that performs correct validation or in the case of a homemade session function, ensure the session id is pessimistically validated before being used, for example by using a regular expression.


### Session token replay or hijack
This vulnerability exists where an attacker can obtain a session token from a victim and use this to obtain their own access to the system under the pretence of being the victim. This works because many systems tie session to identity. The session id might be obtained from an undeleted session cookie, a user who did not log out, intercepted data from a network or simply by visiting a previous site on a shared computer.
#### Applies to frameworks
Potentially applies to all frameworks
#### How to determine if you are vulnerable
Take a session cookie and inject it into the application from another browser. If you are able to use the session at the same time in different browsers or if logging out from one browser session does not prevent the other from continuing to use the session, your application is vulnerable.
#### How to protect yourself
Use a library or framework that can tie the session to a unique browser id. Attempting access from another browser should either fail or cause intrusion detection to log out the first user.
Use a library or framework that supports session id regeneration to shorten the window of attack. 
Do not use persistent cookies for session ids, which expose the session id more easily to an attacker. 
Force cleanup of session data during logout including server-side session so that a replay cannot occur after the user has logged out.

### Session fixation
If an attacker can force a victim into using a known value for session, then it is possible for the victim to login to the known session and thereby allow the attacker to access a session that is now authenticated with a web application.
#### Applies to frameworks
Any framework that allows session ids to be passed in forms or the querystring are particularly vulnerable. Other frameworks may be vulnerable.
#### How to determine if you are vulnerable
Research or test whether it is possible to pass a session id on the querystring, that is accepted and used by the application. If your application URL is a sub-domain (e.g. subdomain.example.com) where you have no control over the other sub-domains, you are potentially vulnerable if an attacker controls another subdomain.
#### How to protect yourself
Do not allow session ids to be passed in except via an HTTP cookie.
Regenerate the session id after logging in. This way, if an attacker did force the victim to login to a pre-known session, it would become invalid as soon as the victim logs in.
Some frameworks will automatically generate a new session if a session id is presented in a cookie, even if it wasn’t generated on the server. To avoid this, set a flag in the session when it is generated on the server-side and if this flag is not set when a user connects, regenerate the session id.
Perform correct wiping of session data and overwrite cookies on log out.
Use some form of browser fingerprinting including client ip address to fix a session id to a client. Although not perfect, this is a very effective against attacks from arbitrary attackers.


### Detecting brute-forcing of session ids
Although a range of measures in other areas of this document are very effective in preventing session attacks, including brute-forcing, it might be desirable to attempt to detect attempted brute-forcing in order to take relevant action. Intrusion detection of this type can be detailed and complicated and will not be fully explained here but the actions you can take are reasonably limited and include IP address blocking (which does not identify individual users), account blocking (which might be real or a hacked account) or some kind of bandwidth throttling. In many cases, Intrusion Detection actions are temporary but long enough to thwart most attempts to brute-force.
#### Applies to frameworks
All frameworks
#### How to determine if you are vulnerable
Attempt to pass multiple session ids using some kind of test program in quick succession and see whether the system responds in a way that slows or prevents this happening.
#### How to protect yourself
You can booby-trap certain session ids and ensure these are never used in real sessions, perhaps every 100th number. If these are sent back to the server, you know someone has guessed the id and you can take any action you deem necessary such as:
1.Temporary IP address ban. Remember that commonly there are multiple users behind an IP address so a permanent ban is unlikely to be a good idea.
2.Throttle the speed for the given ip address for a certain amount of time.
3.If the user is logged on, block their account either permanently or temporarily, possibly requiring a call to reset it.
4.Investigate possible third-party solutions or libraries that might perform this work for your chosen language/framework.


### Tying session to authentication or authorization incorrectly
In some applications, authentication, authorization and session are seen to be equivalent whereas in reality they are not. If they are seen as the same thing then session = authenticated = authorized. Clearly, having a session does not and should not imply that you are authenticated and even authenticated users are not necessarily authorized for a particular action.
Note that this topic overlaps with the authentication and authorization chapters.
#### Applies to frameworks
All frameworks
#### How to determine if you are vulnerable
Log into two browsers with two different users. Take the session id from one session and replace the session id in the other session. If your application is vulnerable, the server should detect the mismatch between authentication and the session id and immediately error with a forced logout. 
If the system allows you to continue as the user that you logged in with (but the wrong session) then your application is vulnerable but the risk of this depends on what information is stored in the session.
If the system changes the user you are logged in with as a result of the changed session id then your system is vulnerable.
#### How to protect yourself
Your framework should link the session with the authenticated user (the authentication information will usually be present in a separate cookie) in a way that means that if they don’t match, this is detected and forces the user to logout, as well as deleting the session data. Your system then needs to handle what happens if two users (the legitimate one and the attacker) are both logged in when the attacker causes the system to log them out – it shouldn’t break the legitimate user’s account but would need to log them out also with a relevant message.
Use browser identification to prevent the session being used by a second person and therefore avoiding the need to logout the user and destroy the session.


### Split Session Attacks
If the server has no way of linking a session id to a client, it might be possible for an attacker to piggy-back a victim’s session, possibly seeing what the victim is doing or has done. 
#### Applies to frameworks
All frameworks
#### How to determine if you are vulnerable
Log into a site from one browser and then copy the session id into a cookie in another browser (or another computer). If it is possible for both users to remain in their respective browser sessions with the same session id, the session has effectively split between two different clients.
#### How to protect yourself
Utilise a framework or library that ties session to a specific client using a browser fingerprint and client ip address.
Use session regeneration at suitable intervals, at which point the old session can be deleted leaving one user without a session – which might be the victim!
Require re-authentication for high-value operations and regenerate the session id at this point.

## Sessions in RESTful applications
RESTful applications create a special kind of session problem. The idea behind a RESTful service or application is that no state is stored server-side, all of the relevant information is stored on the client and passed in with the request, either as parameters or implied from the url that is accessed for the request. This brings special considerations for a session scheme, such as how to prevent tampering, hijacking, fixating and replay attacks. 

One of the special considerations is what data can be stored in the session. Since the session is necessarily exposed outside of the server, it cannot contain any information that we cannot trust the client not to modify. For example, setting the users privilege level in a cookie that is sent to the user would not normally be done in a non-REST situation due to the chance of someone attempting to elevate their privilege but in the case of REST, there is no choice, in which case the design should not depend on storing such sensitive information in the session cookie.

Any system needs to consider encryption, hashing and message signatures to provide the necessary protections and although there are various ways to provide the required mechanisms, it is recommended that professional advice is taken before implementing a REST session system in a high-value application.

The following test cases relate to specific attack vectors on REST-based sessions.

### Simple session authentication with signing
It is possible that your REST system does not require any particular session data and simply needs to authenticate each request to ensure that the client is authorized to use the service or endpoint. This requires at the very least a reliable way of obscuring login credentials, that must necessarily be passed in.

The password/secret should NEVER be passed in the query string, which can be exposed by caches, search engines and in the browser.

At a minimum, SSL/TLS should be used to secure the endpoints. In most cases, if you do NOT use SSL/TLS, many authentication systems are vulnerable to network sniffing. Even if the password/secret is obscured in some way, an attacker can often easily replay the request with the obscured data and still achieve unauthorized access to the service.

The recommended way to pass the password or secret into the system is by using some kind of message authentication code (MAC) and instead of using the secret directly, using it to sign the remainder of the request. By doing this, the server can repeat the process without the secret actually being passed (it is pre-shared) and this will verify that the secret is correct and that the request has not been tampered with. If the date/time is also used in generating the signature, it will also reduce the replay window although you will have to account for slight differences in the time between client and server due to incorrect time settings and network latency.

The following example is based on Amazon Web Services and how they derive their authorization signature:

StringToSign = HTTP-Verb + "\n" +
________Content-MD5 + "\n" +
________Content-Type + "\n" +
________Date + "\n" +
________CanonicalizedAmzHeaders +
________CanonicalizedResource;

Signature = Base64(HMAC-SHA1(UTF-8-Encoding-Of(YourSecretAccessKeyID), StringToSign));

Authorization = "AWS" + " " + AWSAccessKeyId + ":" + Signature;

### Replaying authentication or session
Since the server should not keep track of session in a RESTful system, it cannot track any nonces that could normally be used to prevent replay attacks. For this reason, replay attacks can only be mitigated in REST rather than removed. This must take place by tying the request signatures to the current date/time which will reduce (but not remove) the attack replay window. By using SSL/TLS to encrypt client to server communications, the short replay window of perhaps 5-10 minutes should suitably reduce the risk of replays.

Another mitigation is to use the userid or equivalent in a session authentication code which can be passed as part of the session and which then makes it unusable by another user since when the server checks the MAC of the session coming back, they can determine whether this session was produced for this user or not.

1.Produce relevant session data for user and sign the results with a secret HMAC key and the userid or equivalent
2.Send the session cookie back with the data and the MAC code
3.The correct user sends back the session with the next request, the server re-computes the HMAC and it matches so it can proceed.
4.An attacker attempts to send back the correct users’ session cookie. The server attempts to generate the signature from the attacker’s use id and it doesn’t match. The request is denied.

### Modifying session data to elevate privileges
As previously stated, any session data in the case of REST is exposed directly to and stored by the client. For this reason, by default, we should assume that people will attempt to modify that data to maliciously or otherwise alter the behaviour of the REST service. For this reason, the data should be protected with a MAC, such that tampering can easily be detected. This works since only the server should ever change or set session data and by using a MAC based on a key only known to the server, the user could alter the session but the MAC would then not match and the server can take appropriate action. Since the client does not know the session MAC signing key, they cannot re-compute the MAC to match the altered data.

As with all unshared secrets, the key should be of a suitably long length (256 bits or longer) and generated pseudo-randomly so that the chance of guessing or brute-forcing it is unfeasible. It can also be changed over a suitable period of time (every 3 months) since only the server needs to use this as the signing key.

### Revoking sessions
Revoking sessions cannot actually be performed independently of blocking a user account since no session information is stored on the server. This means that scenarios that would normally require a session to be deleted such as logging out or intrusion detection would be carried out differently. Logging out does not occur in RESTful services since logging in is by definition a stateful process, which is not how REST is designed to work.

The main area where this might be of concern is in response to a detected attack, where a session might need removing to prevent the attack gaining privileges from a session that has been hijacked. In this case, the likely attack vector is that someone has stolen a session cookie from another user and is using it with their valid credentials. In this case, the session should be validated against the MAC and against the user. Since the server cannot store the link between session and user, it would have to form part of the session MAC e.g.

sessionMac = Base64(hmac-sha1(sessioncontents, secretmackey + thisuserid));






***
