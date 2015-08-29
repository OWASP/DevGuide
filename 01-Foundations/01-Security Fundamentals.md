# Security Fundamentals

In basis Security is simply about being in control. Control of who can interact your information, control over what they can do with your information and when then can interact with it. These characteristics of control are described through what is called the CIA triad.

![CIA Triad][1]

##  CIA
CIA is the acronym for Confidentiality, Integrity and Availability and are usually depicted in the form of a triangle that shows the strong bond between them. These three are considered the security pillars of an application. Often these are extended with Authorization and Authentication. The CIA is described as a property of data or of a process.

### Confidentiality
Confidentiality is the protection of data against unauthorized disclosure, or otherwise put, to ensure that only those with the correct authorization can access the information. This concept applies to data in rest, but also to data in motion. This concept is related to the broader concept of data privacy.
A model that has the focus on data confidentiality and controlled access is the *Bell-LaPaluda model*.

### Integrity
Integrity is the protection against unauthorized modification of information, or the trustworthiness of the data. The concept contains the notion of *data integrity*, as in that data has not been changed by accident of deliberate. It also contains the notion of *source integrity*, as in that the data came or was changed by a legitimate source.
A model that has the focus on data integrity through access control rules is the *Biba model*.

### Availability
Availability is the protection of the presence of information or resources. This concept relies not just on the protection of the data itself -- for example by using replication of data -- but also on the protection of the services that provide the access to the data --for example by using load balancing.

## Additions
The CIA is often extended with *Authentication* and *Authorisation* as these are closely linked to the concepts. Better put, the CIA has such a dependency to these concepts that the protection of the information can't be performed without them.
Auditing is added as it can provide the mechanism to ensure proof of any interaction with the system.

### Authentication
This is about identifying the entity with whom you communicate, or that wants to communicate with you. It requires that the identity is irrefutably associated.

### Authorization
This is about what rights an authenticated entity has within the environment. These rights describe the permissions regarding access of a resource or information.

### Auditing (non-repudiation)
This is about logging what interaction has taken place within the environment. Auditing can provide not only technical information of what happens within the application, but also proof that particular actions have been executed within the application.

[1]: images/01x01-CIA_Triad.png
