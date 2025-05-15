Cryptography is fundamental to the Confidentiality and Integrity of applications and systems.
The OWASP [Cheat Sheet][csproject] series describes the use of cryptography and some of these are
listed in the further reading at the end of this section.

#### Overview

This section provides a brief introduction to cryptography (often simply referred to as "crypto") and the terms used.
Cryptography is a large subject and can get very mathematical,
but fortunately for the majority of development teams a general understanding of the concepts is sufficient.
This general understanding, with the guidance of security architects, should allow implementation
of cryptography by the development team for the application or system.

#### Uses of cryptography

Although cryptography was initially restricted primarily to the military and the realm of academia,
cryptography has become ubiquitous in securing software applications.
Common every day uses of cryptography include mobile phones, passwords, SSL VPNs, smart cards, and DVDs.
Cryptography has permeated through everyday life, and is heavily used by many web applications.

Cryptography is one of the more advanced topics of information security,
and one whose understanding requires the most schooling and experience.
It is difficult to get right because there are many approaches to encryption,
each with advantages and disadvantages that need to be thoroughly understood by solution architects.

The proper and accurate implementation of cryptography is extremely critical to its efficacy.
A small mistake in configuration or coding will result in removing most of the protection
and rending the crypto implementation useless.

A good understanding of crypto is required to be able to discern between solid products and snake oil.
The inherent complexity of crypto makes it easy to fall for fantastic claims from vendors about their product.
Typically, these are "a breakthrough in cryptography" or "unbreakable" or provide "military grade" security.
If a vendor says "trust us, we have had experts look at this," chances are they weren't experts!

#### Confidentiality

For the purposes of this section, confidentiality is defined as "no unauthorized disclosure of information".
Cryptography addresses this via encryption of either the data at rest or data in transit by
protecting the information from all who do not hold the decryption key.
Cryptographic hashes (secure, one way hashes) to prevent passwords from disclosure.

#### Authentication

[Authentication][csauthn] is the process of verifying a claim that a subject is who it says it is
via some provided corroborating evidence.
Cryptography is central to authentication:

1. to protect the provided corroborating evidence (for example hashing of passwords for subsequent storage)
2. in authentication protocols often use cryptography to either directly authenticate entities
    or to exchange credentials in a secure manner
3. to verify the identity one or both parties in exchanging messages,
    for example identity verification within [Transport Layer Security][tls] (TLS)

OpenID Connect is widely used as an identity layer on top of the OAuth 2.0 protocol,
see the [OAuth 2.0 Protocol][csoauth] Cheat Sheet.

#### Integrity

Integrity ensures that even authorized users have performed no accidental or malicious alternation of information.
Cryptography can be used to prevent tampering by means of Message Authentication Codes (MACs) or digital signatures.

The term 'message authenticity' refers to ensuring the integrity of information,
often using symmetric encryption and shared keys,
but does not authenticate the sending party.

The term 'authenticated encryption' also ensures the integrity of information,
and, if asymmetric encryption is used, can authenticate the sender.

#### Non-repudiation

Non-repudiation of sender ensures that someone sending a message should not be able to deny later that they have sent it.
Non-repudiation of receiver means that the receiver of a message should not be able to deny that they have received it.
Cryptography can be used to provide non-repudiation by providing unforgeable messages or replies to messages.

Non-repudiation is useful for financial, e-commerce, and contractual exchanges.
It can be accomplished by having the sender or recipient digitally sign some unique transactional record.

#### Attestation

Attestation is the act of "bearing witness" or certifying something for a particular use or purpose.
Attestation is generally discussed in the context of a Trusted Platform Module (TPM),
Digital Rights Management (DRM), and UEFI Secure Boot.

For example, Digital Rights Management is interested in attesting that your device
or system hasn't been compromised with some back-door to allow someone to illegally copy DRM-protected content.

Cryptography can be used to provide a chain of evidence that everything is as it is expected to be,
to prove to a challenger that everything is in accordance with the challenger's expectations.
For example, remote attestation can be used to prove to a challenger that
you are indeed running the software that you claim that you are running.
Most often attestation is done by providing a chain of digital signatures starting with
a trusted (digitally signed) boot loader.

#### Cryptographic hashes

Cryptographic hashes, also known as message digests, are functions that map arbitrary length bit strings
to some fixed length bit string known as the 'hash value' or 'digest value'.
These hash functions are many-to-one mappings that are compression functions.

Cryptographic hash functions are used to provide data integrity (i.e., to detect intentional data tampering),
to store passwords or pass phrases, and to provide digital signatures in a more efficient manner
than using asymmetric ciphers.
Cryptographic hash functions are also used to extend a relatively small bit of entropy
so that secure random number generators can be constructed.

When used to provide data integrity, cryptographic functions provide two types of integrity:
keyed hashes, often called 'message authentication codes', and unkeyed hashes called 'message integrity codes'.

#### Ciphers

A cipher is an algorithm that performs encryption or decryption.
Modern ciphers can be categorized in a couple of different ways.
The most common distinctions between them are:

* Whether they work on fixed size number of bits (block ciphers) or on a continuous stream of bits (stream ciphers)
* Whether the same key is used for both encryption and decryption (symmetric ciphers)
    or separate keys for encryption and decryption (asymmetric ciphers)

#### Symmetric Ciphers

Symmetric ciphers encrypt and decrypt using the same key.
This implies that if one party encrypts data that a second party must decrypt,
those two parties must share a common key.

Symmetric ciphers come in two main types:

1. Block ciphers, which operate on a block of characters (typically 8 or 16 octets) at a time.
    An example of a block cipher is AES
2. Stream ciphers, which operate on a single bit (or occasionally a single byte) at a time.
    Examples of a stream ciphers are RC4 (aka, ARC4) and Salsa20

Note that all block ciphers can also operate in 'streaming mode' by selecting the appropriate cipher mode.

#### Cipher Modes

Block ciphers can function in different modes of operations known as "cipher modes".
This cipher mode algorithmically describes how a cipher operates to repeatedly
apply its encryption or decryption mechanism to a given cipher block.
Cipher modes are important because they have an enormous impact on both the confidentiality
and the message authenticity of the resulting ciphertext messages.

Almost all cryptographic libraries support the four original DES cipher modes of ECB, CBC (Cipher Block Chaining)
OFB (Output Feedback), and CFB (Cipher Feedback). Many also support CTR (Counter) mode.

#### Initialization vector

A cryptographic initialization vector (IV) is a fixed size input to a block cipher's encryption / decryption primitive.
The IV is recommended (and in many cases, required) to be random or at least pseudo-random.

#### Padding

Except when they are operating in a streaming mode, block ciphers generally operate on fixed size blocks.
These block ciphers must also operate on messages of any size,
not just those that are an integral multiple of the cipher's block size,
and so the message can be padded to fit into the next fixed-size block.

#### Asymmetric ciphers

Asymmetric ciphers  encrypt and decrypt  with two different keys.
One key generally is designated as the private key and the other is designated as the public key.
Generally the public key is widely shared and the private key is kept secure.

Asymmetric ciphers are several orders of magnitude slower than symmetric ciphers.
For this reason they are used frequently in hybrid cryptosystems, which combine asymmetric and symmetric ciphers.
In such hybrid cryptosystems, a random symmetric session key is generated
which is only used for the duration of the encrypted communication.
This random session key is then encrypted using an asymmetric cipher and the recipient's private key.
The plaintext data itself is encrypted with the session key.
Then the entire bundle (encrypted session key and encrypted message) is all sent together.
Both [TLS][tls] and S/MIME are common cryptosystems using hybrid cryptography.

#### Digital signature

Digital signatures are a cryptographically unique data string that is used to ensure data integrity
and prove the authenticity of some digital message, and that associates some input message with an originating entity.
A digital signature generation algorithm is a cryptographically strong algorithm that is used
to generate a digital signature.

#### Key agreement protocol

Key agreement protocols are protocols whereby N parties (usually two) can agree on a common key
without actually exchanging the key.
When designed and implemented properly, key agreement protocols prevent adversaries
from learning the key or forcing their own key choice on the participating parties.

#### Application level encryption

Application level encryption refers to encryption that is considered part of the application itself;
it implies nothing about where in the application code the encryption is actually done.

#### Key derivation

A key derivation function (KDF) is a deterministic algorithm to derive a key of a given size from some secret value.
If two parties use the same shared secret value and the same KDF, they should always derive exactly the same key.

#### Key wrapping

Key wrapping is a construction used with symmetric ciphers to protect cryptographic key material
by encrypting it in a special manner.
Key wrap algorithms are intended to protect keys while held in untrusted storage
or while transmitting keys over insecure communications networks.

#### Key exchange algorithms

Key exchange algorithms (also referred to as key establishment algorithms) are protocols
that are used to exchange secret cryptographic keys
between a sender and receiver in a manner that meets certain security constraints.
Key exchange algorithms attempt to address the problem of securely sharing a common secret key with two parties
over an insecure communication channel in a manner that no other party can gain access to a copy of the secret key.

The most familiar key exchange algorithm is Diffie-Hellman Key Exchange.
There are also password authenticated key exchange algorithms.
RSA key exchange using PKI or webs-of-trust or trusted key servers are also commonly used.

#### Key transport protocols

Key Transport protocols are where one party generates the key and sends it securely to the recipient(s).

#### Key agreement protocols

Key Agreement protocols are protocols whereby N parties (usually two) can agree on a common key
with all parties contributing to the key value.
These protocols prevent adversaries from learning the key or forcing their own key choice on the participating parties.

#### References

* OWASP Cheat Sheet series
  * [Authentication][csauthn]
  * [Authorization][csauthz]
  * [Cryptographic Storage][cscs]
  * [Key Management][kmcs]
  * [OAuth 2.0 Protocol][csoauth]
  * [SAML Security][sscs]
  * [Secure Product Design][spdcs]
  * [User Privacy Protection][uppcs]

----

The OWASP Developer Guide is a community effort; if there is something that needs changing
then [submit an issue][issue0404] or [edit on GitHub][edit0404].

[csauthn]: https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet
[csauthz]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet
[csoauth]: https://cheatsheetseries.owasp.org/cheatsheets/OAuth2_Cheat_Sheet
[csproject]: https://owasp.org/www-project-cheat-sheets/
[cscs]: https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet
[edit0404]: https://github.com/OWASP/DevGuide/blob/main/docs/en/02-foundations/04-crypto-principles.md
[issue0404]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/04-crypto-principles
[kmcs]: https://cheatsheetseries.owasp.org/cheatsheets/Key_Management_Cheat_Sheet
[sscs]: https://cheatsheetseries.owasp.org/cheatsheets/SAML_Security_Cheat_Sheet
[spdcs]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet
[tls]: https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet
[uppcs]: https://cheatsheetseries.owasp.org/cheatsheets/User_Privacy_Protection_Cheat_Sheet
