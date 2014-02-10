### Overview ###

Overview

Authentication is TBA.


### Principles ###

#### Evidence of Identity ####

Authentication is the process of establishing a strong link between a person and an electronic identity principal, which is generally stored in a user object store, like an LDAP server, database, or Active Directory. 
The evidence of identity in the registration process should be in line with the business risk of the application. For example, the evidence of identity for a tax return application or banking application should be quite rigorous, as anti-money laundering laws and other local laws and regulations apply, whereas the evidence of identity for social networks can be very relaxed unless there are local laws requiring real names to be used. 
Evidence of identity post registration applies even if anonymous usage is encouraged or mandated. For example, under many Privacy regimes, there is a requirement that users must be given an opportunity to deal with an organization anonymously, and all business processes and storage preserves that anonymity. For example, if a user wishes to register for a competition, their name should not appear as a winner unless the user has consented to that usage. 
Another misconception about evidence of identity is that it only applies during registration, but it also applies for all authentication attempts. For example, user X of a whistle blowing application expects that no one else can impersonate user X. This means adequate proof of identity is provided when logging in, such as the use of multi-factor authentication. The use of passwords alone is no longer considered safe, and so authentication should be multi-factor or risk based to prevent attackers obtaining an account improperly. 


#### Complete mediation ####

The Principle of Complete Mediation requires all secured pages, functions and data to be protected by an authentication control. At it's simplest, complete mediation could be implemented by 

#### Enforce authentication ####

Authentication must be enforced in a trusted environment, such as at a policy enforcement point or server. If authentication is enforced in an untrusted location, such as on a mobile device or browser, authentication can always be bypassed. 

#### Protect credentials in transit ####

Credentials, including session, API and function tokens, must be protected in transit to prevent disclosure to eavesdroppers. The dangers of unencrypted or clear text sessions has been amply shown by tools such as FireSheep, DriftNet and Dsniff. 

#### Protect credentials at rest ####

Credentials, particularly API keys and passwords, must be properly protected from exposure. 

API keys must be protected from disclosure, including in source revision control systems, as they are equivalent to username and passwords, and often allow direct remote access to an application's inner workings. 

Passwords should be salted and hashed using a modern algorithm, with cryptographic agility to allow multiple salting and hash algorithm choices. A safe password storage scheme does not allow for the reversal of password hashes into clear text. A safe alternative today is the use of a random salt:

password' = hash(password + salt)

DerivedKey = PBKDF2(PRF, password, salt, c, dkLen)

Where PRF is a pseudo random function, such as SHA1-HMAC 

A strong hashing algorithm should take a considerable amount of time on a modern computer, such as multiple rounds of SHA256 or PBKDF2. 

### Classification of system ###

### Authentication Models ###

#### Single factor ####

#### Multi-factor authentication ####

#### Knowledge based authentication ####

#### RIsk based authentication ####

#### Claims based Identity ####

#### Biometric authentication ####

Biometric authentication

Biometric authentication is not suitable for most devices or systems on the following basis:

A) The user is covering a system owner's risk with their life and body parts. This is an unacceptable risk. 
B) Biometric credentials cannot be revoked, only removed. This means biometric credentials fail the most basic attribute of a credential - revocation. 
C) Biometric authentication relies on trust of the biometric device, which unless it is strictly controlled (such as under constant vigilance such at a border crossing), is not true.
D) The false positive rate within large user populations means that biometrics cannot be used as a single factor authentication mechanism.
E) The cost of biometric devices is relatively high compared to secure alternatives, such as transaction signing tokens or SMS one time passwords.

Biometric authentication can be a useful mechanism where the user has a device under their control, and the only enrolled user 

### Authentication Patterns ###

#### Self-registration UML ####

#### Credential reset UML ####

#### Forgot credential UML ####

#### REST or API Authentication ####

#### Login UML ####

#### Login UML using WS-Security* ####

#### Login UML using OAuth2 ####

#### High value transaction signing UML ####

#### Logout UML ####

### Negative patterns ###

#### Questions and answers ####

#### Credential enumeration ####

#### Horizontal and vertical brute force ####
