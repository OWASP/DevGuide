# Data Protection

Allocated to AJV

## Background

Data protection is one of the top issues with secure development, and one of the least well developed from an API point of view. 

Various laws and regulations exist to protect user privacy. Users expect their data to be handled well as a baseline requirement, particularly when it comes to the cloud. 

With recent events exposing both mass surveillance of the Internet, as well as the memory scraping attacks favored by attackers, it is important for developers to include countermeasures to protect data at rest, during processing and data in transit. 

## Principles (if any)

### Encrypt sensitive data at rest 

Data stored in the cloud, or even bulk data collections require protection from interception and exfiltration. Generally, high value records should be protected, such as:

Data that could be considered a private record under privacy legistlation, which may include (but is not limited to):

* Name, phone, e-mail and address (generally taken together, but refer to your local privacy laws)
* Gender
* Political affliations
* Health records or status
* TBA (need to look at privacy legislation)

It is important to understand that simply using database engine "encryption" facilities does not protect against application level attacks against bulk data stored in the database, nor does it stop database administrators from accessing that data. Therefore, it should be up to the application to ensure that the data being encrypted cannot be viewed or decrypted without obtaining the private key held on the application server. 

This approach allows for safe storage in the cloud, as long the key is not stored with the data. If you store the key with the data, that is called "plain text equivalent" and provides no real protection. 

For more information, please see TBA below and in the cryptography chapter. 

### Encrypt all data in transit

With the collection and analysis of meta data shown to be a clear and present danger to the Internet at large, it is important to ensure that all communications to and from your services are encrypted. This doesn't prevent mass surveillence understanding the size or who connects to your services, but it does prevent basic data leakage, which is very common with older web apps and many mobile applications.

For more information, please see TBA below. 

### Protect direct object references

A common security flaw is direct object references, where a URL design, particularly in RESTful webservices:

http://example.com/webservice/member/32351/edit

But what happens when you change the URL to the following?

http://example.com/webservice/member/32352/edit

If your application does not protect against this issue, which is also the OWASP Top 10 #4 software flaw, data protection is at risk. It is important to enforce direct object reference security wherever a primary key is used to access data. 

For more information, please see TBA below. 

### Clear memory as soon as you're done with it

One of the most common modern attack tecniques is to inject malware into an application, and scrape the application's memory for sensitive data. With a large virtual memory space, this can include the memory allocator's work pages, which are often not zeroed out. This means that if you create a sensitive string in memory, such as a password or a certificate, or a special value such as account roles or balances, an attacker can scrape your memory and obtain these values. 

For more information, please see TBA below. 

## Positive controls 

### Control
How to build a secure <thing> using Control to help you, including (or even just) UML diagrams. I prefer swim lanes, but as long as it prints in landscape mode, I'm cool. I don't want portrait diagrams as this is impossible to reflow automatically using our tools.

### Control
How to build a secure <thing> using Control to help you


## Unit or Integration Test Cases

## Abuse Cases

## Negative patterns

### Control that should never ever appear under pain of infinite nyan cat

e.g. shared knowledge questions or answers, or dynamic SQL queries

## References

***

## Secure strings



## Data retention


## Privacy
## Data at rest controls
## PCI DSS requirements
