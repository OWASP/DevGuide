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

## Testing for Risks
The following sections describe specific attack vectors against your site session management system and tell you how to test for the vulnerability and how to fix it, should it exist. It should be noted that some of the fixes are simply options on your session management system, whereas others will affect higher-level parts of your system design and should be considered before your application is written, to avoid the potential difficulty of retro-fitting these controls afterwards.

### Session Token Transmission
If a session token is captured in transit through network interception, a web application account is then trivially prone to a replay or hijacking attack. Typical web encryption technologies include but are not limited to Secure Sockets Layer (SSL) and Transport Layer Security (TLS) protocols in order to safeguard the state mechanism token.
### How to determine if you are vulnerable
Visit a page on your site and/or login to cause the system to create a new session. Using your browser developer tools, view the cookies for the site and find the session cookie. If it is not marked as secure and your site url is not https then you are vulnerable. Alternatively, if you know your site does not support SSL/TLS at all, then you are also vulnerable.
### How to protect yourself
Set up SSL/TLS on your web server and set the Secure flag on your session cookie. Verify the fix by visiting your site, causing it to create a session cookie and using your developer tools to ensure the Secure flag is checked proving that the browser has downloaded the cookie on a secure connection.


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

