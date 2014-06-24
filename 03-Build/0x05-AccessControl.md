
### Overview ###

Allocated to Jerry

Access control is the process of enforcing that a particular user identity has sufficient permissions to create, read, update or delete a secured resource, access a secured function, page, or data, or perform a secured business flow. 



### Principles ###

#### Separation of duties ####

[Separation of duties](http://en.wikipedia.org/wiki/Separation_of_duties) is the concept of having more than one person required to complete a task.


#### Principle of least privilege ####

The [principle of least privilege](http://en.wikipedia.org/wiki/Principle_of_least_privilege) requires that in a particular abstraction layer of a computing environment, every module (such as a process, a user or a program depending on the subject) must be able to access only the information and resources that are necessary for its legitimate purpose


#### Deny all by default ####

Design access controls so that they fail securely.  Default access to protected resources should be denial, with access granted only if the requestor has been explicitly assigned access rights (by reason of the requestor's identity, role or attributes depending on the access control model being used).



#### Policy enforcement on trusted devices ####

Access control can be performed anywhere, but to be effective, it must be enforced on a trusted device, typically the server.  For usability or performance (latency) reasons, access control logic can be done at the client _in addition_ to server side.  However, client side code can be altered or bypassed, and so should not be trusted.



#### Principle of Aggregate Access Control ####

An important update to the OWASP Developer Guide 2013 is the concept of aggregate access control: users may be allowed to access a secured resource a _reasonable_ number of times, or within a specified overall system limit. This prevents secured resource denial of service, or secured resource information disclosure attacks. 

For example, the number of HTTP requests to a particular resource, or the web service overall, from a particular source or all sources, should be limited.  Queries on data tier should be limited to prevent unnecessary full table scans or excess data downloads.

Establishing limits is dependent on the business needs of the application and capacity of the server and data stores, as well as security policy.  It is advisable to design limits to be configurable, in order to adapt the application to changing business needs and capacity.

#### Single mechanism ####

Use a centralized mechanism (including libraries that call external authorization services) for protecting access to each type of protected resource.  De-centralizing access control is both inefficient and can be insecure.  If access control decisions are made separately in each application component, updates to access policy may not be reflected in all parts of the application.  

If developing in Java or JavaScript, consider using the [OWASP ESAPI](https://www.owasp.org/index.php/Category:OWASP_Enterprise_Security_API) _AccessController_ interface.



#### All access control decisions are auditable ####

Log all access control decisions that result in access denial.  This allows forensic analysis for any security incidents, and can also be used proactively to detect possible attack attempts.

If feasible, log all access control decisions, including those granting access.



#### Protect access control metadata ####

The integrity of all user and data attributes and policy information used by access controls should be considered critical. Ensure these data cannot be manipulated by end users unless specifically authorized, using access control measures and data integrity measures covered elsewhere in this guide.



### Common Access Control Schemes ###

![Access Control Models](https://cloud.githubusercontent.com/assets/5155869/3372592/4e3139be-fbac-11e3-8269-8048da77abb6.png "Access Control Models")

ACL (Access Control List), RBAC (Role Based Access Control),  and ABAC (Attribute Based Access Control) are described in this guide.  PBAC (Policy Based Access Control) is another perspective on ABAC.  RAdAC (Risk Adaptive Access Control) is still experimental, and so is not further discussed in this guide.

#### Role Based Access Control ####

"A role based access control ([RBAC](http://csrc.nist.gov/rbac/ferraiolo-kuhn-92.pdf)) policy bases access control decisions on the functions a user is allowed to perform within an organization. The users cannot pass access permissions on to other users at their discretion."

![Role Based Access Control](https://cloud.githubusercontent.com/assets/5155869/3372041/3557c3e0-fba7-11e3-9f1a-73b9fda45bf5.jpg "Role Based Access Control")

Access permissions (in terms of operations such as read/write) are assigned to _roles_, not users.  Users (or _subjects_) are then granted roles. An access control decision for a subject is determining whether the subject has any role (one is sufficient) with the requested access.  Role _hierarchies_ allow specification of roles which contain other roles.

#### Mandatory Access Control ####

Mandatory access control ([MAC](http://en.wikipedia.org/wiki/Mandatory_access_control)) refers to a type of access control by which the operating system constrains the ability of a subject or initiator to access or generally perform some sort of operation on an object or target.  With mandatory access control, users do not have the ability to override the policy and, for example, grant access to files that would otherwise be restricted. This is in contrast to discretionary access control ([DAC](http://en.wikipedia.org/wiki/Discretionary_access_control)), such as that used for UNIX file permissions.

#### Capabilities Based Access Control ####

[Capability based security](http://en.wikipedia.org/wiki/Capability-based_security) controls access on the basis of possession of a _capability_, defined to be a protected object reference which, by virtue of its possession by a user process, grants that process specifc access to the referenced object.  A capability is typically implemented as a privileged data structure that consists of a section that specifies access rights, and a section that uniquely identifies the object to be accessed.

Capability based security and access control requires supporting infrastructure, typically the operating system, to provide secure capabilitiy generation and transmission.

[Windows and .Net _claims_](http://msdn.microsoft.com/en-us/library/ff423674.aspx) are similar to capabilities.  Claims are tokens that make a claim (such as possession of a role or access privilege) that can be trusted by the resource owner (the claim token may be digitally signed by a truster issuer, for instance).  Claims based access control is used in [Microsoft Azure Access Control Service (ACS)](http://msdn.microsoft.com/en-us/library/hh446534.aspx).


#### Attribute Based Access Control (ABAC) ####

[ABAC](http://csrc.nist.gov/projects/abac/) is a logical access control model that is distinguishable because it controls access to objects by evaluating rules against the attributes of the entities (subject and object) actions and the environment relevant to a request. Attributes may be considered characteristics of anything that may be defined and to which a value may be assigned. In its most basic form, ABAC relies upon the evaluation of attributes of the subject, attributes of the object, environment conditions, and a formal relationship or access control rule defining the allowable operations for subject-object attribute and environment condition combinations. 

![Attribute Based Access Control](https://cloud.githubusercontent.com/assets/5155869/3372532/d7b2d0fe-fbab-11e3-8f79-60aacd82204d.png "Attribute Based Access Control")



### How to enforce access control ###

Check out the [OWASP Access Control Cheat Sheet](https://www.owasp.org/index.php/Access_Control_Cheat_Sheet).

#### Services ####

Ensure that users can only access secured services and functions for which they possess specific authorization.

Services are often realized in web applications as [JEE (Java Enterprise Edition) servlets](http://en.wikipedia.org/wiki/Java_Servlet), [REST](http://en.wikipedia.org/wiki/Representational_state_transfer#Applied_to_web_services) resources identified as URIs, [SOAP (Simple Object Access Protocol)](http://en.wikipedia.org/wiki/Simple_Object_Access_Protocol) request servers, or [W3C Web Services](http://www.w3.org/2002/ws/).

If developing in Java or JavaScript, consider using the [OWASP ESAPI](https://www.owasp.org/index.php/Category:OWASP_Enterprise_Security_API) _AccessController (assertAuthorizedForService method)_ interface to control access to services.  Otherwise, use a similar interface to a centralized service access control decision point.

#### URLs ####

Ensure that users can only access secured URLs for which they possess specific authorization.

If developing in Java or JavaScript, consider using the [OWASP ESAPI](https://www.owasp.org/index.php/Category:OWASP_Enterprise_Security_API) _AccessController (assertAuthorizedForURL method)_ interface to control access to URLs.  Otherwise, use a similar interface to a centralized service access control decision point.



#### Files and directories ####

Ensure that users can only access secured data files for which they possess specific authorization.

If developing in Java or JavaScript, consider using the [OWASP ESAPI](https://www.owasp.org/index.php/Category:OWASP_Enterprise_Security_API) _AccessController (assertAuthorizedForFile method)_ interface to control access to files.  Otherwise, use a similar interface to a centralized file access control decision point.


#### Data ####

Ensure that direct object references are protected, such that only authorized objects are accessible to each user.

If developing in Java or JavaScript, consider using the [OWASP ESAPI](https://www.owasp.org/index.php/Category:OWASP_Enterprise_Security_API) _AccessController (assertAuthorizedForData method)_ interface to control access to data.  Otherwise, use a similar interface to a centralized data access control decision point.


#### Functions ####

Functions may be realized in a Web application as SOAP request types, REST operations encoded in the URI, etc.

Ensure that the application or framework generates strong random anti-CSRF (Cross Site Request Forger) tokens unique to the user as part of all high value transactions or accessing sensitive data, and that the application verifies the presence of this token with the proper value for the current user when processing these requests.  This protection measure can prevent [CSRF](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)_Prevention_Cheat_Sheet) attacks from succeeding, and is known as the [Synchronizer Token Pattern](http://www.corej2eepatterns.com/Design/PresoDesign.htm).

Randomization is discussed in the Cryptography chapter of this guide.  

If developing in Java or JavaScript, consider using the [OWASP ESAPI](https://www.owasp.org/index.php/Category:OWASP_Enterprise_Security_API) _User (resetCSRFToken method)_ interface to create anti-CSRF tokens, and the _HTTPUtilities (verifyCSRFToken method)_ interface to verify the token.

Better yet, consider centalizing anti-CSRF token generation and verification by using the [OWASP ESAPI](https://www.owasp.org/index.php/Category:OWASP_Enterprise_Security_API) _AccessController (assertAuthorizedForFunction method)_ interface to control access to functions, including anti-CSRF token verification.  Otherwise, use a similar interface to a centralized function access control decision point.

#### Memory and objects ####

If end users need direct access to data objects, ensure that the application verifies access to secured memory and objects before granting access.

If developing in Java or JavaScript, consider using the [OWASP ESAPI](https://www.owasp.org/index.php/Category:OWASP_Enterprise_Security_API) _AccessController (assertAuthorizedForData method)_ interface to control access to objects.  Otherwise, use a similar interface to a centralized object access control decision point.


#### Presentation ####

Ensure that the same access control rules implied by the presentation layer are enforced on the server side for that user role, such that controls and parameters cannot be re-enabled or re-added from higher privilege users.  Consistency between presentation and server side also avoids user confusion.



### Web Services ###

#### OAuth2 ####

##### Authorization Server #####

##### Providers #####

##### Clients #####

##### Access Tokens #####

##### Interoperability #####

##### Establishing authorization using OAuth2 #####

##### Calling an API using OAuth2 #####

##### Asking users for permission #####

#### REST ####

##### Claims based access control (Windows Azure) #####

#### XACML ####

Look at PicketBox, an open source XACML implementation for more details.


##### ABAC #####

##### Delegation #####

##### Policy Enforcement Point #####

##### Policy Decision Point #####

##### Policy Retrieval Point #####

#### Relying Party ####

### References ###
