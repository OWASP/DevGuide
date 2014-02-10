
### Overview ###

Access control is the process of enforcing that a particular user identity has sufficient permissions to create, read, update or delete a secured resource, access a secured function, page, or data, or perform a secured business flow. 



### Principles ###

#### Segregation of duties ####

http://en.wikipedia.org/wiki/Separation_of_duties

#### Principle of least privilege ####

http://en.wikipedia.org/wiki/Principle_of_least_privilege

#### Deny all by default ####

Verify that access controls fail securely.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### Policy enforcement on trusted devices ####

Access control can be performed anywhere, but to be effective, it must be enforced on a trusted device, typically the server. 

Verify that all access controls are enforced on the server side.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### Principle of Aggregate Access Control ####

An important update to the OWASP Developer Guide 2013 is the concept of aggregate access control: users may be allowed to access a secured resource n times, but not all records. This prevents secured resource denial of service, or secured resource information disclosure attacks. 

#### Single mechanism ####

Verify that there is a centralized mechanism (including libraries that call external authorization services) for protecting access to each type of protected resource.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### All access control decisions are auditable ####

Verify that all access control decisions can be logged and all failed decisions are logged.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### Protect access control metadata ####

Verify that all user and data attributes and policy information used by access controls cannot be manipulated by end users unless specifically authorized.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


### Common Access Control Schemes ###

#### Role Based Access Control ####

#### Mandatory Access Control ####

#### Capabilities Based Access Control ####

#### Attribute Based Access Control (ABAC) ####

### How to enforce access control ###

#### Services ####

Verify that users can only access secured services and functions for which they possess specific authorization.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### URLs ####

Verify that users can only access secured URLs for which they possess specific authorization.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### Files and directories ####

Verify that users can only access secured data files for which they possess specific authorization.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### Data ####

Verify that direct object references are protected, such that only authorized objects are accessible to each user.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### Functions ####

Verify that the application or framework generates strong random anti-CSRF tokens unique to the user as part of all high value transactions or accessing sensitive data, and that the application verifies the presence of this token with the proper value for the current user when processing these requests.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### Memory and objects ####

Verify that the application verifies access to secured memory and objects
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


#### Presentation ####

Verify that the same access control rules implied by the presentation layer are enforced on the server side for that user role, such that controls and parameters cannot be re-enabled or re-added from higher privilege users.
UML diagram if desirable
Use test cases
Abuse test cases
Applicability


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
