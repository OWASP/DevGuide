If you're assigned this chapter, please refactor what's here and make it modern!

New content ->

## Overview
Session management is required to track the state of a users journey through a web application. It is the role of a developer/designer to create or use a session management system in a way that is secure, avoiding the leaking of this
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
weaknesses including access of this session value via malicious Javascript or a man-in-the-middle who can read and then re-use the session ID in another browser.

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
a 24 character alpanumeric identifier (which will be web safe, as opposed to a binary value).

#### Where to store the session data
Although it is possible to store almost any session data in a cookie, this is not recommended and for any authorization type information should never be done. Security is best handled on a server, not decided by the contents of a small text file which is easy
to see and modify. It is preferable to only store the session id in the cookie and store the remaining data either in a database at the server-side or in memory on the web server. There are performance and cost considerations to these choices, depending on the number
of users on the system and how much data is stored in the session. There are also special considerations if you are using a web server farm due to the memory not being shared. In these cases, if you want to use a memory-based session, you need to use some type of
shared memory or a mechanism provided by your hosting provider for this purpose.

#### What to store in the session
One of the ways to reduce the burden on the session storage is to only keep the minimum amount of information in the session that you need to. For instance, a language choice might be kept in a cookie to keep it away from the server and based on the fact that it
is neither secret or dangerous if it was tampered with. Certain data can also be stored in the URL e.g. the current ordering of a gridview since, again, it is generally not secret and should probably not be kept in a session. Anything that is kept in hidden fields
on a page is actually visible to anyone who looks. If this data is secret, you should either keep it store in the session or in a related database table.

#### HTTP Only Cookies
A session cookie in any good framework should default to setting an HTTPOnly flag. This tells the browser that the cookie cannot be accessed by Javascript to read the session of another user who has somehow got malware script running in a site they are visiting.

#### SSL Only Flag
It is also possible and recommended, wherever possible, to set the Secure flag on the cookie which enforces that the cookie is only allowed to be downloaded via HTTPS. This will only work if your site implements SSL/TLS but prevents a man-in-the-middle being able to read the contents of the cookie.

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
It is possible that your REST system does not require any particular session data and simply needs to authenticate each request to ensure that the client is authorised to use the service or endpoint. This requires at the very least a reliable way of obscuring login credentials, that must necessarily be passed in.

The password/secret should NEVER be passed in the query string, which can be exposed by caches, search engines and in the browser.

At a minimum, SSL/TLS should be used to secure the endpoints. In most cases, if you do NOT use SSL/TLS, many authentication systems are vulnerable to network sniffing. Even if the password/secret is obscured in some way, an attacker can often easily replay the request with the obscured data and still achieve unauthorised access to the service.

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
As previously stated, any session data in the case of REST is exposed directly to and stored by the client. For this reason, by default, we should assume that people will attempt to modify that data to maliciously or otherwise alter the behaviour of the REST service. For this reason, the data should be protected with a MAC, such that tampering can easily be detected. This works since only the server should every change or set session data and by using a MAC based on a key only known to the server, the user could alter the session but the MAC would then not match and the server can take appropriate action. Since the client does not known the session MAC signing key, they cannot re-compute the MAC to match the altered data.

As with all unshared secrets, the key should be of a suitably long length (256 bits or longer) and generated pseudo-randomly so that the chance of guessing or brute-forcing it is unfeasible. It can also be changed over a suitable period of time (every 3 months) since only the server needs to use this as the signing key.

### Revoking sessions
Revoking sessions cannot actually be performed independently of blocking a user account since no session information is stored on the server. This means that scenarios that would normally require a session to be deleted such as logging out or intrusion detection would be carried out differently. Logging out does not occur in RESTful services since logging in is by definition a stateful process, which is not how REST is designed to work.

The main area where this might be of concern is in response to a detected attack, where a session might need removing to prevent the attack gaining privileges from a session that has been hijacked. In this case, the likely attack vector is that someone has stolen a session cookie from another user and is using it with their valid credentials. In this case, the session should be validated against the MAC and against the user. Since the server cannot store the link between session and user, it would have to form part of the session MAC e.g.

sessionMac = Base64(hmac-sha1(sessioncontents, secretmackey + thisuserid));






***

Old content ->



## Objective

To ensure that authenticated users have a robust and cryptographically secure association with their session
enforce authorization checks prevent common web attacks, such as replay, request forging and man-in-the-middle attacks 

## Description
Thick client applications innately store local data ("state") in memory allocated by the operating system for the duration of the program's run, such as global, heap and stack variables. With web applications, the web server serves up pages in response to client requests. By design, the web server is free to forget everything about pages it has rendered in the past, as there is no explicit state. 

This works well when rendering static content, such as a brochure or image, but not so well when you want to do real work, such as filling out a form, or if you have multiple users you need to keep separate, such as in an online banking application.

Web servers are extended by application frameworks, such as J2EE or ASP.NET, implementing a state management scheme tying individual user's requests into a "session" by tying a cryptographically unique random value stored in a cookie (or elsewhere within client submitted data) against state held on the server, giving users the appearance of a stateful application. The ability to restrict and maintain user actions within unique sessions is critical to web security.

Although most users of this guide will be using an application framework with built in session management capabilities, others will use languages such as Perl CGI that do not. They are at an immediate disadvantage as the developers may be forced to create a session management scheme from scratch. These implementations are often weak and breakable. Another common mistake is to implement a weak session management scheme on top of a strong one. It is theoretically possible to write and use a cryptographically secure session management scheme, which is the focus of this chapter. However, for mere mortals, it cannot be stressed highly enough to use an application framework which has adequate session management. There is no value in re-writing such basic building blocks.

Application frameworks such as J2EE, PHP, ASP and ASP.NET take care of much of the low level session management details and allow fine level control at a programmatic level, rather than at a server configuration level. For example, ASP.NET uses an obfuscated tamper-resistant "view state" mechanism, which renders a hidden field in each page. View state can be used to transmit insensitive variables, web control locations, and so on. Using programmatic means, it's possible to include or exclude a variable from the view state, particularly if you don't need a control’s state to be available between different pages of the same application. It is also possible to encrypt view state if you are likely to transmit sensitive data to the user, but it is better if such variables are kept in the server-side session object. This can save download time, reduce bandwidth, and improve execution times. Careful management of the view state is the difference between a well-optimized application, and a poorly performing application. 

## Best practices

Best practice is to not re-write the wheel, but to use a robust, well-known session manager. Most popular web application frameworks contain a suitable implementation. However, early versions often had significant weaknesses. Always use the latest version of your chosen technology, as its session handler will likely be more robust and use cryptographically strong tokens. Use your favorite search engine to determine if this is indeed the case. 

Consider carefully where you store application state:
* Authorization and role data should be stored on the server side only
* Navigation data is almost certainly acceptable in the URL as long as it can be validated and authorization checks are effective
* Presentation flags (such as theme or user language) can belong in cookies.
* Form data should not contain hidden fields – if it is hidden, it probably needs to be protected and only available on the server side. However, hidden fields can (and should) be used for sequence protection and to prevent brute force pharming attacks

Data from multi-page forms can be sent back to the user in two cases: 
* When there are integrity controls to prevent tampering
* When data is validated after every form submission, or at least by the end of the submission process

Application secrets (such as server-side credentials and role information) should never be visible to the client. These must be stored in a session or server-side accessible way
If in doubt, do not take a chance and stash it in a session.

## Misconceptions

Sessions have an undeserved poor reputation with some programmers, particularly those from Java backgrounds who prefer the ease of programming stateless server side components. However, this is simply wrong from a security and performance perspective, as state must be stored somewhere, and sensitive state must be stored on the server in some fashion. The alternative, storing all state within each request, leads to extensive use of hidden fields and extra database queries to avoid server-side session management, and is vulnerable to replay and request forgery attacks, as well as producing complex code.

Another common misperception is that they take up valuable server resources. This was true when servers were RAM constrained, but is not true today. Indeed, transmitting session data to a client, and then decoding, de-serializing, performing tampering checks, and lastly validating the data upon each request requires higher server resource consumption than keeping it safe inside a session object.

Session authentication

Session management is by its nature closely tied to authentication, but this does not mean users should be considered authenticated until the web application has taken positive action to tie a session with a trusted credential or other authentication token.

For example, just connecting to a PHP application will issue every end user with a valid PHPSessionID cookie, but that does not mean that users should be trusted or you should ship them goods. Only once they have proven that they are known to your web application should they be trusted.
How to determine if you are vulnerable
Use a browser to connect to a protected page or action deep in the application. If a new session ID is generated and the page works, the authorization controls make a false assumption about the validity of the session variable. 

How to protect yourself

* When starting a fresh session object for a user, make sure they are in the “logged off” state and are granted no role 
* Ensure that each protected page or action checks the authentication state and authorization role before performing any significant amount of work, including rendering content. 
* Ensure that all unprotected pages use as few resources as possible to prevent denial of service attacks, and do not leak information about the protected portion of the application

## (CSRF) Page Tokens

Page specific tokens or "nonce’s" may be used in conjunction with session specific tokens to provide a measure of authenticity when dealing with client requests. Used in conjunction with transport layer security mechanisms, page tokens can aide in ensuring that the client on the other end of the session is indeed the same client which requested the last page in a given session. Page tokens are often stored in cookies or query strings and should be completely random. It is possible to avoid sending session token information to the client entirely through the use of page tokens, by creating a mapping between them on the server side, this technique should further increase the difficulty in brute forcing session authentication tokens.

### How to protect yourself
TODO

## Session Fixation

### How to determine if you are vulnerable

### How to protect yourself

## Weak Session Cryptographic Algorithms 

If a session handler issues tokens which are predictable, an attacker does not need to know 
Session tokens should be user unique, non-predictable, and resistant to reverse engineering. 
How to determine if you are vulnerable

Ask for 1000 session IDs and see if they are predictable (plotting them helps identify this property)
Investigate the source of the session handler to understand how session IDs are generated. They should be created from high quality random sources.

### How to protect yourself

* A trusted source of randomness should be used to create the token (like a pseudo-random number generator, Yarrow, EGADS, etc.).
* Additionally, for more security, session tokens should be tied in some way to a specific HTTP client instance to prevent hijacking and replay attacks. 

Examples of mechanisms for enforcing this restriction may be the use of page tokens that are unique for any generated page and may be tied to session tokens on the server. In general, a session token algorithm should never be based on or use as variables any user personal information (user name, password, home address, etc.)

## Appropriate Key Space

Even cryptographically secure algorithms allow an active session token to be easily determined if the keyspace of the token is not sufficiently large. Attackers can essentially "grind" through most possibilities in the token's key space with automated brute-force scripts. A token's key space should be sufficiently large enough to prevent these types of brute force attacks, keeping in mind that computation and bandwidth capacity increases will make these numbers insufficient over time.

## Session Token Entropy

The session token should use the largest character set available to it. If a session token is made up of say 8 characters of 7 bits the effective key length is 56 bits. However if the character set is made up of only integers that can be represented in 4 bits giving a key space of only 32 bits. A good session token should use all the available character set including case sensitivity.

## Session Time-out

Session tokens that do not expire on the HTTP server can allow an attacker unlimited time to guess or brute-force a valid authenticated session token. An example is the "Remember Me" option on many retail websites. If a user's cookie file is captured or brute-forced, then an attacker can use these static-session tokens to gain access to that user's web accounts. This problem is particularly severe in shared environment, where multiple users have access to one computer. Additionally, session tokens can be potentially logged and cached in proxy servers that, if broken into by an attacker, could be exploited if the particular session has not been expired on the HTTP server.

### How to determine if you are vulnerable

* Idle “Protection” - Does the application do a meta-refresh or similar Javascript trick to force the session to never idle out? If so, the application is vulnerable.
* Remember me? - Does the application have a “remember me” feature? If so, the application is vulnerable

## Faulty idle timeout
* Login to the application
* Go to lunch
* Try to use the application. Did it work? If so, the application is vulnerable

### How to protect yourself

Set the idle timeout to 5 minutes for highly protected applications through to no more than 20 minutes for low risk applications

For highly protected applications:
* Do not write idle defeat mechanisms
* Do not write “remember me” functionality

## Regeneration of Session Tokens
Description

To reduce the risk from session hijacking and brute force attacks, the HTTP server can seamlessly expire and regenerate tokens. This shortens the window of opportunity for a replay or brute force attack. Token regeneration should be performed based on number of requests (high value sites) or as a function of time, say every 20 minutes.

How to determine if you are vulnerable
How to protect yourself

## Session Forging/Brute-Forcing Detection and/or Lockout

Many websites have prohibitions against unrestrained password guessing (e.g., it can temporarily lock the account or stop listening to the IP address), however an attacker can often try hundreds or thousands of session tokens embedded in a legitimate URL or cookie without a single complaint from the web site. Many intrusion-detection systems do not actively look for this type of attack; penetration tests also often overlook this weakness in web e-commerce systems. Designers can use "booby trapped" session tokens that never actually get assigned but will detect if an attacker is trying to brute force a range of tokens. 
Resulting actions could be:

Go slow or ban the originating IP address (which can be troublesome as more and more ISPs are using transparent caches to reduce their costs. Because of this: always check the "proxy_via" header)
Lock out an account if you're aware of it (which may cause a user a potential denial of service).
Anomaly/misuse detection hooks can also be built in to detect if an authenticated user tries to manipulate their token to gain elevated privileges.

There are Apache web server modules, such as mod_dosevasive and mod_security, that could be used for this kind of protection. Although mod_dosevasive is used to lessen the effect of DoS attacks, it could be rewritten for other purposes as well

### How to determine if you are vulnerable
### How to protect yourself

## Session Token Transmission

If a session token is captured in transit through network interception, a web application account is then trivially prone to a replay or hijacking attack. Typical web encryption technologies include but are not limited to Secure Sockets Layer (SSLv2/v3) and Transport Layer Security (TLS v1) protocols in order to safeguard the state mechanism token.

### How to determine if you are vulnerable

TODO

### How to protect yourself

TODO

## Session Tokens on Logout

With the popularity of Internet Kiosks and shared computing environments on the rise, session tokens take on a new risk. A browser only destroys session cookies when the browser thread is torn down. Most Internet kiosks maintain the same browser thread. 

### How to determine if you are vulnerable

* “Logout” of the application
* Check the cookies to see if the session ID has changed or has been removed
* Check the cookies to see if all non-session related variables have been removed

### How to protect yourself

When the user logs out of the application:
* Destroy the session 
* Overwrite session cookies.

## Session Hijacking

When an attacker intercepts or creates a valid session token on the server, they can then impersonate another user. Session hijacking can be mitigated partially by providing adequate anti-hijacking controls in your application. The level of these controls should be influenced by the risk to your organization or the client's data; for example, an online banking application needs to take more care than a application displaying cinema session times.

The easiest type of web application to hijack are those using URL based session tokens, particularly those without expiry. This is particularly dangerous on shared computers, such as Internet cafés or public Internet kiosks where is nearly impossible to clear the cache or delete browsing history due to lockdowns. To attack these applications, simply open the browser's history and click on the web application's URL. Voila, you're the previous user.

### How to determine if you are vulnerable
TODO

### How to protect yourself

Provide a method for users to log out of the application. Logging out should clear all session state and remove or invalidate any residual cookies.

Set short expiry times on persistent cookies, no more than a day or preferably use non-persistent cookies.
Do not store session tokens in the URL or other trivially modified data entry point.

## Session Authentication Attacks

One of the most common mistakes is not checking authorization prior to performing a restricted function or accessing data. Just because a user has a session does not authorize them to use all of the application or view any data.

A particularly embarrassing real life example is the Australian Taxation Office's GST web site, where most Australian companies electronically submit their quarterly tax returns. The ATO uses client-side certificates as authentication. Sounds secure, right? However, this particular web site initially had the ABN (a unique number, sort of like a social security number for companies) in the URL. These numbers are not secret and they are not random. A user worked this out, and tried another company's ABN. To his surprise it worked, and he was able to view the other company's details. He then wrote a script to mine the database and mail each company's nominated e-mail address, notifying each company that the ATO had a serious security flaw. More than 17,000 organizations received e-mails.

### How to determine if you are vulnerable
* TODO

### How to protect yourself

Always check that the currently logged on user has the authorization to access, update or delete data or access certain functions.

## Session Validation Attacks

Just like any data, the session variable must be validated to ensure that is of the right form, contains no unexpected characters, and is in the valid session table.

In one penetration test the author conducted, it was possible to use null bytes to truncate session objects and due to coding errors in the session handler, it only compared the length of the shortest string. Therefore, a one character session variable was matched and allowed the tester to break session handling. During another test, the session handling code allowed any characters.

### How to determine if you are vulnerable
TODO

### How to protect yourself

Always check that the currently logged on user has the authorization to access, update or delete data or access certain functions.

## Preset Session Attacks

An attacker will use the properties of your application framework to either generate a valid new session ID, or try to preset a previously valid session ID to obviate access controls.
### How to determine if you are vulnerable

* Test if your application framework generates a new valid session ID by simply visiting a page. 
* Test if your application framework allows you to supply the session ID anywhere but a non-persistent cookie. 

For example, if using PHP, grab a valid PHPSESSIONID from the cookie, and insert it into the URL or as a post member variable like this:

http://www.example.com/foo.php?PHPSESSIONID=xxxxxxx

If this replay works, your application is at some risk, but at an even higher risk if the session ID can be used after the session has expired or the session has been logged off.

### How to protect yourself

* Ensure that the frameworks’ session ID can only be obtained from the cookie value. This may require changing the default behavior of the application framework, or overriding the session handler. 
* Use session fixation controls (see next section) to strongly tie a single browser to a single session
* Don’t assume a valid session equals logged in – keep the session authorization state secret and check authorization on every page or entry point.

## Man in the middle attacks

In a man in the middle (MITM) attack, the attacker tries to insert themselves between the server and the client. Acting as the client for the server and acting as a server for the client. So all data sent from the client to the real server is not going directly but though the attacker. It is difficult for the client and server to detect this attack.

### How to determine if you are vulnerable

TODO

### How to protect yourself

Use SSL, especially for sites with privacy or high value transactions. One of the properties of SSL is that it authenticates the server to the clients, with most browsers objecting to certificates that do not have adequate intermediate trust or if the certificate does not match the DNS address of the server. This is not full protection, but it will defeat many naive attacks. Sensitive site operations, such as administration, logon, and private data viewing / updating should be protected by SSL in any case.

## Session Brute forcing

Some e-Commerce sites use consecutive numbers or trivially predictable algorithms for session IDs. On these sites, it is easy to change to another likely session ID and thus become someone else. Usually, all of the functions available to users work, with obvious privacy and fraud issues arising.

### How to determine if you are vulnerable
* Use a session brute force tool, like Brutus

### How to protect yourself
* Use a cryptographically sound token generation algorithm. Do not create your own algorithm, and seed the algorithm in a safe fashion. Or just use your application framework's session management functions.
* Preferably send the token to the client in a non-persistent cookie or within a hidden form field within the rendered page.
* Put in "telltale" token values so you can detect brute forcing.
* Limit the number of unique session tokens you see from the same IP address (ie 20 in the last five minutes).
* Periodically regenerate tokens to reduce the window of opportunity for brute forcing.
* If you are able to detect a brute force attempt, completely clear session state to prevent that session from being used again.

## Session token replay

Session replay attacks are simple if the attacker is in a position to record a session. The attacker will record the session between the client and the server and replay the client's part afterwards to successfully attack the server. This attack only works if the authentication mechanism does not use random values to prevent this attack.

### How to determine if you are vulnerable

* Take a session cookie and inject it into another browser
* Try simultaneous use – should fail
* Try expired use – should fail

### How to protect yourself

Tie the session to a particular browser by using a hash of the server-side IP address (REMOTE_ADDR) and if the header exists, PROXY_FORWARDED_FOR. Note that you shouldn’t use the client-forgeable headers, but take a hash of them. If the new hash doesn’t match the previous hash, then there is a high likelihood of session replay.
Use session token timeouts and token regeneration to reduce the window of opportunity to replay tokens.
Use a cryptographically well-seeded pseudo-random number generator to generate session tokens.
Use non-persistent cookies to store the session token, or at worst, a hidden field on the form.
Implement a logout function for the application. When logging off a user or idle expiring the session, ensure that not only is the client-side cookie cleared (if possible), but also the server side session state for that browser is also cleared. This ensures that session replay attacks cannot occur after idle timeout or user logoff.

## Split Session Attacks

TODO

### How to determine if you are vulnerable

TODO

### How to protect yourself

TODO


## Further Reading
David Endler, "Brute-Force Exploitation of Web Application Session IDs" http://downloads.securityfocus.com/library/SessionIDs.pdf

