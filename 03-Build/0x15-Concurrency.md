# Concurrency 

## Background

Concurrency true to its roots refers to actions that flow together. On a single processor machine that may refer to time sharing the CPU between several independent processes, splitting asynchronous tasks across multiple CPU cores, or even similar separation of work thathat might be spread over multiple devices in overlapping time spans. The concept refers to making sure, regardless of the distribution of the parts, that everything happens in an order that, optimally, does not generate any negative impact.
 
## Principles (if any)
TBD

## Positive controls 
TBD

### Control
(TBD How to build a secure <thing> using Control to help you, including (or even just) UML diagrams. I prefer swim lanes, but as long as it prints in landscape mode, I'm cool. I don't want portrait diagrams as this is impossible to reflow automatically using our tools.)
Reliable timestamps and server time settings become very helpful if not essential.

Locking can be employed to stop a resource from being read or modified when it is being manipulated.

Notifications and other forms of messaging from one process to another can help asynchronous tasks coordinate or sync as needed.

Intelligent waiting that attempts to sense a trigger can fire off processing in concert with one another. Events in Javascript for instance often trigger code to run after a click, pointer movement, or key press among many others.

Polling, for when the best use case is for a process to query a resource about the impending state and actions related to itself.

Timeouts can be employed to kill processes not performing to expectations or requirements.

Feedback upon successful completion is often easy and it can facilitate orchestration of related processes as a type of message. If you are lucky you will also have easily accessible logic structures that handle failures for processes when an undesirable or unexpected outcome occurs.

### Control
(TBD How to build a secure <thing> using Control to help you)


## Unit or Integration Test Cases
While testing, it will likely be necessary to institute 'mock' objects, services, and other system related assets to fake the required branching of the code in regards to seeing just how fast or slow the prior process can complete before a related process might fail.
## Abuse Cases
The most obvious abuse cases that spring to mind are financial in nature where one might subvert limits by creating multiple transactions before the system can respond in the planned and expected way. Say for instance an individual has a $500 bank account balance. The Fictional Federal Bank system requires roughly five seconds to properly update the value of the funds held in the account. Without proper controls, a user could submit several transfers before the system might realize there wre insufficient funds. However, it can also refer to simply making use of 'undocumented features' which is a scary solution to employ. Concurrency is often a concern when processes running at the same time rely on instructions that execute by chance due to some unplanned obscure operation.

## Negative patterns
Using poorly devised logic without locking, notifications, waiting, or polling to  positively avoid race conditions leaves you with potential risks. Additionally, the language you may be working in potentially has data structures that facilitate sharing the state of the data with more than one process, thread, or device. Concurrency issues often are related to persistent data storage. Care should be taken to avoid full-table database locking that would prevent other concurrent operations involving independent data.

### Control that should never ever appear under pain of infinite nyan cat
A further extension of DB example would be to tie up multiple tables and locking them.
Arbitrarily waiting and hoping the prerequisite operations completed may work. However, it is the bad kind of lazy as well as a code smell.

e.g. shared knowledge questions or answers, or dynamic SQL queries

## References
TBD

***
## Race conditions
## Memory management
## REST API threadedness
## Preventing side channel attacks
