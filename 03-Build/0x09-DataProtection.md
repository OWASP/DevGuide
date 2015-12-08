# Data Protection

Allocated to AJV

## Background

Data protection is one of the top priorities of secure development, and yet one of the least well developed from an API point of view. It is possible to increase the trust of your application considerably with a few well chosen data protection controls. 

Various laws and regulations exist to protect user privacy. Users expect their data to be handled well as a baseline requirement, particularly when it comes to the cloud. It is no longer sufficient to protect against SQL injection and consider data protection done. Users expect more from software vendors. Organisations will not trust their data with you unless you have a strong end to end data protection architecture. 

With recent events exposing both mass surveillance of the Internet, as well as the memory scraping attacks favored by attackers, it is important for developers to include countermeasures to protect data at rest, during processing and data in transit. 

## Principles

### Encrypt all data in transit

Ten years ago, it was very common for the majority of applications to transmit all their data unencrypted. There is still strong resistance to the idea of encrypting all data, but end to end encryption is essential to building trust between you and your users. 

With the collection and analysis of metadata shown to be a clear and present danger to the Internet at large, it is important to ensure that all communications to and from your services are encrypted. This doesn't prevent mass surveillence understanding the size or who connects to your services, but it does prevent basic data leakage, which is very common with older web apps and many mobile applications.

For more information, please see TBA below. 

### Encrypt sensitive data at rest 

Data stored in the cloud, or even bulk data collections require protection from interception and exfiltration. Generally, high value records should be protected, such as:

Data that could be considered a private record under privacy legislation, which may include (but is not limited to):

* Name, phone, e-mail and address (generally taken together, but refer to your local privacy laws)
* Gender
* Political affiliations
* Health records or status
* TBA (need to look at privacy legislation)

It is important to understand that simply using database engine "encryption" facilities does not protect against application level attacks against bulk data stored in the database, nor does it stop database administrators from accessing that data. Therefore, it should be up to the application to ensure that the data being encrypted cannot be viewed or decrypted without obtaining the private key held on the application server. 

This approach allows for safe storage in the cloud, as long the key is not stored with the data. If you store the key with the data, that is called "plain text equivalent" and provides no real protection. 

For more information, please see TBA below and in the cryptography chapter. 

### Protect sensitive data in processing

A common security flaw is direct object references, where a URL design, particularly in RESTful webservices:

http://example.com/webservice/member/32351/edit

But what happens when you change the URL to the following?

http://example.com/webservice/member/32352/edit

If your application does not protect against this issue, which is also the OWASP Top 10 #4 software flaw, data protection is at risk. It is important to enforce direct object reference security wherever a primary key is used to access data. 

For more information, please see TBA below. 

### Clear memory as soon as you're done with it

One of the most common modern attack techniques is to inject malware into an application, and scrape the application's memory for sensitive data. With a large virtual memory space, this can include the memory allocator's work pages, which are often not zeroed out. This means that if you create a sensitive string in memory, such as a password or a certificate, or a special value such as account roles or balances, an attacker can scrape your memory and obtain these values. 

For more information, please see TBA below. 

## Positive controls 

### Use end to end encryption for data in transit

The simplest and easiest method is to encrypt all communications to and from your application. As shown recently, this should also include connections to back end systems such as cloud data storage, application analytics, databases, data warehouses, and web services, as it can no longer be assumed that interception of backend traffic is unlikely. In fact, interception of data center traffic is likely

Although there are numerous methods to encrypt traffic between systems, the most common is the use of Transport Layer Security (TLS), often called "SSL encryption" by the lay person. Your application framework or application server should contain instructions on TLS configuration, not only in the traditional sense to web and mobile clients, but also to back end systems such as database servers. 

For more information, please review the Cryptography chapter, section TBA. 

### Create per-installation encryption keys for data at rest

Encrypting data at rest needs to protect against a few different attack scenarios:

* Bulk data extraction, such as from SQL injection attacks
* Malicious administrator attacks, where an administrator accesses data directly from database administration tools
* Internal attacks, such as logging on to the database using application credentials
* Accidental loss, such as backups being exposed or lost

All of these scenarios can be protected against by encrypting sensitive data in the application's data models. There are a few drawbacks to this approach, including loss of indexing. However, as long as the data is stored on a system other than the application server, dividing the application encryption key and the encrypted data apart will raise the bar for any but the most determined and advanced attackers. 

For the highly sensitive data, encrypting within a hardware st

### Use secure strings

With ASP.NET 2.0 and later, and with Java ???, it is possible to use secure string classes that protect against memory scraping attacks. 

However, in most programming languages, it is not possible to keep memory safe from memory scraping attacks, so the best advice is to ensure sensitive data is zeroed as fast as possible once the use for the sensitive 


### Use prepared statements, parameterized queries, Active Record, ORMs, or data bindings

As a developer, you should be familiar with the concept of SQL injection (TBA: link to Testing Guide). You can completely avoid SQL injection via the use of prepared statements (also known as parameterized queries), Active Record data access pattern, or Object Relational Mapping engines (ORMs). 

All major platforms have support for one or more of these safer alternatives to dynamic queries. You should be using them unless you have a very specific requirement for dynamic queries, such as report writing. 

If you have to use dynamic queries, you are responsible for escaping data provided by end users, as this data can be both hostile or accidentally damaging to your database. 

NB: it is not possible to escape table names, SQL DDL (such as "ORDER BY", or "DESC" or "ASC", etc), and so on. If your dynamic query relies upon user supplied input for this unescapable data, you should strongly validate that data, and review if you could use another data access mechanism, such as prepared statements or an ORM. 

## Unit or Integration Test Cases

### testForEncryption()

Ensure integration and unit tests can test for secure sockets are in use between the end user and application server, as well as between application server and any other trust boundaries, such as database server, in app analytics, content delivery networks, and so on. 

### testValidDirectObjectReference()

Test your data model to ensure that user A's records can be created, read, updated and deleted by User A. 

For example, create a setUp() that logs in as User A (Alice), and then inserts a record. 

Then for the test, login as User A (Alice), and as Alice try to create a new record, read both records, updates one or both records, and finally deletes Alice's records. 

### testInvalidDirectObjectReference()

Test your data model to ensure that trying to read an invalid data direct object reference does not work. This will prevent an attacker possibly reading the random user data. 

For example, create a setUp() that logs in as User A (Alice) and creates valid records for Alice. 

Then for the test, either don't login, or login as another valid user, such as "


### testsomeOneElsesDirectObjectReference()

Test your data model to ensure that user A's records cannot be accessed or manipulated by user M. 

For example, create a setUp() that logs in as User A (Alice), and inserts a record. Then for the test, login as User M (Mallory), and as Mallory try to create, read, update or delete Alice's records. 




## Abuse Cases

### Protect against direct object references

## Negative patterns

### Using dynamic queries for SQL or LDAP access



### Control that should never ever appear under pain of infinite nyan cat

e.g. shared knowledge questions or answers, or dynamic SQL queries

## References

***

## Secure strings



## Data retention


## Privacy
## Data at rest controls
## PCI DSS requirements
