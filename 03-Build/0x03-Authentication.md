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

The Principle of Complete Mediation requires all secured pages, functions and data to be protected by an authentication control. At its simplest, complete mediation could be implemented by 

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

Authenticating an entity entails proving a secret is known, a tangible object is possessed, or an inherent characteristic is present. A secret could be a password or pin number. A tangible object example might be an employee ID card or Yubikey. An inherent characteristic might be biometric data like a fingerprint, retinal scan, or voice recognition.

But the main point is that only one of these 'challenges' to the entity is used to compare against some known good data stored in single factor authentication. For some trivial purposes, the weak security provided by a password only authentication may be sufficient.

#### Multi-factor authentication ####

As laws and regulations change regularly, the reader should be aware of the regulatory environments they operate in. OWASP is not a source of legal advice. That being said, the following may be used as starting points for further research.

When protecting resources from the unauthorized, two-factor authentication is the bare minimum. Usual implementations employ an intangible secret with a real world factor like a physical key or palm print. The most popular implementation is with YubiKey type token generators either with a physical real world generator device or software token generator. It is rare to see multi-factor authentication security with biometric and physical infrastructure outside of government, medical, and banking applications but not unheard of.

For matters in the United States HIPAA for healthcare, Office of Management &amp; Budget Memorandum 07-16 for government, and Special Publication 800-63 Electronic Authentication Guideline from the National Institute of Standards and Technology all specify when two factor authentication is part of best practices if not required.

Australian federal government departments must comply with the first four of the ASD Top 35 in addition to Australian Privacy Principles and Medicare Act if maintaining health records.

Additionally, documents from ISO 2000x (specifically ISO 20007), ISO 31000 (derived from AS/NZS 4360), NZIM, Jericho Forum, ENISA IAF, BSI Germany, and BITS Shared Assessments - AUP / SIG may apply in regards to acceptable international security practices.



#### Knowledge based authentication ####

There are two forms of knowledge based authentication(KBA). The first is static KBA where the system requests responses for secret information to be used during authentication. This is a frequently used method. It is straight forward to design and implement the storage of information the user provides. Unfortunately, the information requested is often not difficult to derive from other sources. For example date of birth, mother's maiden name, high school attended, pet's name, or last four digits of a Social Security number can be discovered for most people. The second type of knowledge based authentication is dynamic KBA where the system obtains data already known to the system and presents the user a challenge to verify the user knows the data the system found. Needless to say, these systems are generally more sophisticated and require more planning to execute well. A common example of dynamic KBA might include knowing the amount and/or date of the last transaction for a bank account. The bank knows when someone made their last transaction at the ATM and for what amount. This is an excellent use for knowledge based authentication because finding this information in public data stores would be unlikely. To authenticate the user in control of the bank account, the user would provide matching information to the data stored with the bank.

#### Risk based authentication ####

Risk based authentication takes into account available information and ramps up the security as specified for the profile that is built from the information gathered. A known machine accessing resources from an internally recognized IP address during customary business hours will likely generate a very low risk profile. So, the login challenge presented to the user will likely be fast and easy. By comparison a previously unseen mobile device from outside the internal network at odd hours should generate a higher risk profile and presentation of a more involved challenge or challenges would be appropriate.

#### Claims based identity ####

This method of identifying a user involves trust. Anyone that has logged in with facebook or google has used claims based identity. The basic idea is that a third-party provides the confirmation that a user has been sufficiently vetted as being that user. This allows separation of identification and authorization &amp; access control which can simplify a lot of registration issues.



#### Biometric authentication ####

Biometric authentication

Biometric authentication is not suitable for most devices or systems on the following basis:

A) The user is covering a system owner's risk with their life and body parts. This is an unacceptable risk. 
B) Biometric credentials cannot be revoked, only removed. This means biometric credentials fail the most basic attribute of a credential - revocation. 
C) Biometric authentication relies on trust of the biometric device, which unless it is strictly controlled (such as under constant vigilance such at a border crossing), is not true.
D) The false positive rate within large user populations means that biometrics cannot be used as a single factor authentication mechanism.
E) The cost of biometric devices is relatively high compared to secure alternatives, such as transaction signing tokens or SMS one time passwords.

Biometric authentication can be a useful mechanism where the user has a device under their control, and is the only enrolled user 

### Authentication Patterns ###

#### Self-registration UML ####

![user based registration](https://cloud.githubusercontent.com/assets/306802/3176074/60166f42-ec01-11e3-9730-f5b555b555e0.png "user based registration")

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
