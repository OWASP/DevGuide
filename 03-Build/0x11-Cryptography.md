
# Cryptography

Note: Email [me](mailto:kevin.w.wall@gmail) if you have questions.

## Objective

This cryptography guide presents a complete cryptographic toolbox with a minimal set of tools and guidance on how to use them safely (and what the dangers are).

This cryptography guide is split into the following sections: 

1. Recommendations – an executive summary or cheatsheet 
1. Understanding Cryptography – the basics – covers cryptographic properties, primitives and schemes 
1. Using Cryptography to Solve Practical Problems – applying the tools for data in transit and data at rest – overview of well known protocols

It will not cover: 

1. How to break cryptography (i.e., cryptanalysis), but will point out the properties and limitations of the cryptographic tools, and the dangers to watch out for 
1. How to design or implement cryptographic algorithms. Moreover, it discourages you from doing so 
1. PKI and X.509 certificates

## Platforms Affected

All Relevant COBIT Topics

-   DS5.8 – Cryptographic Key Management




## Glossary of Cryptographic Terms

Like most specialized technical areas, cryptography has its own specific jargon. Rather than trying to define each term as it is used and cause possible distractions for those with familiarity with these terms, we will refer you to the definitions in the following glossaries:

-   [http://nvlpubs.nist.gov/nistpubs/ir/2013/NIST.IR.7298r2.pdf](http://nvlpubs.nist.gov/nistpubs/ir/2013/NIST.IR.7298r2.pdf)
-   [http://www.cryptomuseum.com/crypto/glossary.htm](http://www.cryptomuseum.com/crypto/glossary.htm)
-   [http://www.ciphersbyritter.com/GLOSSARY.HTM](http://www.ciphersbyritter.com/GLOSSARY.HTM)

There is also more general Internet security glossaries here:

-   [http://tools.ietf.org/html/rfc4949](http://tools.ietf.org/html/rfc4949)
-   [](http://www.garlic.com/%7Elynn/secure.htm "http://www.garlic.com/~lynn/secure.htm")[http://www.garlic.com/~lynn/secure.htm](http://www.garlic.com/\~lynn/secure.htm "http://www.garlic.com/~lynn/secure.htm")

## Description


### Uses of Cryptography

Filler / introductory sentence – TBD.

Initially primarily restricted to the military and the realm of academia, cryptography has become ubiquitous thanks to the Internet. Common every day uses of cryptography include mobile phones, passwords, SSL VPNs, smart cards, and DVDs. Cryptography has permeated through everyday life, and is heavily used by many web applications.

Cryptography (or crypto) is one of the more advanced topics of information security, and one whose understanding requires the most schooling and experience. It is difficult to get right because there are many approaches to encryption, each with advantages and disadvantages that need to be thoroughly understood by web solution architects and developers.

The proper and accurate implementation of cryptography is extremely critical to its efficacy. A small mistake in configuration or coding will result in removing most of the protection and rending the crypto implementation useless.

A good understanding of crypto is required to be able to discern between solid products and snake oil. The inherent complexity of crypto makes it easy to fall for fantastic claims from vendors about their product. Typically, these are "a breakthrough in cryptography" or "unbreakable" or provide "military grade" security. If a vendor says "trust us, we have had experts look at this," chances are they weren't experts!

### NIST Approved Algorithms

Throughout this cryptographic guide, NIST approved algorithms (published as [FIPS](http://csrc.nist.gov/publications/PubsFIPS.html "http://csrc.nist.gov/publications/PubsFIPS.html") documents or [Special Publications](http://csrc.nist.gov/publications/PubsSPs.html "http://csrc.nist.gov/publications/PubsSPs.html")) are referenced and recommended. While many other standardisation and approval bodies (e.g. ISO, ANSI, IEEE, IETF) could have been used instead, NIST represents the most holistic, current, conservative, and freely accessible set. Referenced standards link to the online standard for further reading. NIST standards reference or standardize standards from these other groups.

[NSA Suite B](http://en.wikipedia.org/wiki/NSA_Suite_B_Cryptography "http://en.wikipedia.org/wiki/NSA_Suite_B_Cryptography") is a minimal subset of NIST approved algorithms designed for interoperability. It is mentioned for reference though recommendations include other algorithms outside this set.

### Primitives, Schemes, Protocols

Cryptography algorithms can be characterised as:

1.  Primitives – the basic building blocks that form the basis for the desired properties E.g. block ciphers, stream ciphers, hash functions, integer factorization, discrete logs.
2.  Schemes – How the primitives are configured to be used safely for a given purpose E.g. Authenticated Encryption (with Associated Data), MACs, Public Key Encryption or Signatures. The NIST approved schemes have a theoretical proof of security.
3.  Protocols – How the schemes are used to meet the end use case e.g. securing data in transit via TLS, S/MIME.

## Recommendations


### Avoid creating your own cryptography!

1.  Use existing protocols if possible, else use existing schemes to implement your protocol.
2.  Do not use symmetric key and asymmetric key primitives directly.
3.  Note: Typically, protocols are designed to support different and new cryptographic schemes e.g. TLS cipher-suites, e.g. S/MIME CMS types support different schemes. This allows your application to support newer cryptographic schemes over time with minimal effort via a new configuration rather than a re-write.

### Use a conservative minimum trusted set of primitives and schemes

1.  A conservative minimal set of building blocks (primitives and schemes) is presented throughout this guide based on [NIST Cryptographic Toolkit](http://csrc.nist.gov/groups/ST/toolkit/index.html "http://csrc.nist.gov/groups/ST/toolkit/index.html") to enable users to “select cryptographic security components and functionality for protecting their data, communications, and operations. The toolkit currently includes a wide variety of cryptographic algorithms and techniques, and more will be added in the future”
  1.  Use approved (e.g. NIST approved) widely accepted algorithms and widely accepted implementations that have been in use in the field for a significant period of time. This will reduce the risk of vulnerabilities or backdoors.
2.  To understand beyond the recommendations in this section, see the following (or consult with a recognised expert):
  1.  NIST [SP 800-131A Transitions: Recommendation for Transitioning the Use of Cryptographic Algorithms and Key Lengths](http://csrc.nist.gov/publications/PubsSPs.html#800-131A "http://csrc.nist.gov/publications/PubsSPs.html#800-131A") provides more specific guidance for transitions to the use of stronger cryptographic keys and more robust algorithms (than original publication NIST [SP 800-57 Recommendation for Key Management: Part 1](http://csrc.nist.gov/publications/PubsSPs.html#800-57pt1 "http://csrc.nist.gov/publications/PubsSPs.html#800-57pt1")).
  2.  [Algorithms, key size and parameters report – 2014](http://www.enisa.europa.eu/activities/identity-and-trust/library/deliverables/algorithms-key-size-and-parameters-report-2014/at_download/fullReport "http://www.enisa.europa.eu/activities/identity-and-trust/library/deliverables/algorithms-key-size-and-parameters-report-2014/at_download/fullReport") from European Union Agency for Network and Information Security.
  3.  [ISO TR 14742 “Recommendations on Cryptographic Algorithms and their use”](https://www.iso.org/obp/ui/#iso:std:iso:tr:14742:ed-1:v1:en "https://www.iso.org/obp/ui/#iso:std:iso:tr:14742:ed-1:v1:en")
  4.  [[5]](http://www.keylength.com/) summarises recommendation results from NIST and other groups

### Use protocols or schemes with consistent strength

1.  In other words, a chain (your overall system) is as strong as the weakest link (the weakest cryptographic primitive or scheme in your system)
2.  Keys must be protected with keys that are at least as strong as the key being protected e.g.
  1.  If an RSA 2048 key e.g. SSL cert private key is stored in an Encrypted File System (EFS) then the EFS should use at least 3TDEA or AES-128 for encryption.
  2.  If an AES-128 key (128 security bits) is protected by a 3TDEA key (112 security bits) then the effective strength/ security bits of the AES-128 key becomes 112 security bits (not 128 security bits ).
            1.  [NIST SP 800-57 Part 1](http://csrc.nist.gov/publications/drafts/800-57/Draft_SP800-57-Part1-Rev3_May2011.pdf "http://csrc.nist.gov/publications/drafts/800-57/Draft_SP800-57-Part1-Rev3_May2011.pdf")[5.6.3 Using Algorithm Suites](http://csrc.nist.gov/publications/drafts/800-57/Draft_SP800-57-Part1-Rev3_May2011.pdf "http://csrc.nist.gov/publications/drafts/800-57/Draft_SP800-57-Part1-Rev3_May2011.pdf") *“*Algorithm suites that combine non-comparable strength algorithms are generally discouraged. However, algorithms of different strengths and key sizes may be used together for performance, availability or interoperability reasons, provided that sufficient protection is provided. In general, the weakest algorithm and key size used to provide cryptographic protection determines the strength of the protection."
3.  If a password is being used to protect keys then the [password strength](http://en.wikipedia.org/wiki/Password_strength "http://en.wikipedia.org/wiki/Password_strength") should be sufficient for the strength of the keys it is protecting.

### Use unique cryptographic keys and cryptographic parameters

1.  cryptographic parameters should be unique: any IVs , nonces, RNG seeds, RNG output, salts, or any other cryptographic parameter should be used once only
2.  Keys should be unique per purpose
      1. A given symmetric key should be used for one purpose only e.g. in payments ([DUKPT](http://en.wikipedia.org/wiki/Derived_unique_key_per_transaction "http://en.wikipedia.org/wiki/Derived_unique_key_per_transaction")), each of the following would require a different key (per transaction):
        1. encryption/decryption of a PIN
        2. encryption/decryption of card data
        3. MAC'ing of card data
      2. A given asymmetric key pair should be used for one purpose only e.g. authentication only, encryption only, key establishment only
      3. A given asymmetric key pair should be used with one scheme only e.g. per [PKCS1 v2.2](http://www.emc.com/emc-plus/rsa-labs/pkcs/files/h11300-wp-pkcs-1v2-2-rsa-cryptography-standard.pdf "http://www.emc.com/emc-plus/rsa-labs/pkcs/files/h11300-wp-pkcs-1v2-2-rsa-cryptography-standard.pdf") “A generally good cryptographic practice is to employ a given RSA key pair in one scheme. This avoids the risk that vulnerability in one scheme may compromise the security of the other.”
3.  Keys should have once-off or limited use
    1.  Limiting how often the same key is used is good practice – especially for the working key i.e. the key that is processing the payload directly.
    2.  Automatic or manual Key rotation should be used.
    3.  Symmetric automatic key updates e.g. [DUKPT](http://en.wikipedia.org/wiki/Derived_unique_key_per_transaction "http://en.wikipedia.org/wiki/Derived_unique_key_per_transaction") derives 3 unique 2TDEA keys per transaction for payment – one to encrypt PIN blocks, one to encrypt data, one to MAC data.
    4.  Asymmetric automatic key updates e.g. TLS supports uses [Ephemeral](http://en.wikipedia.org/wiki/Ephemeral_key "http://en.wikipedia.org/wiki/Ephemeral_key")modes (TLS\_DHE and TLS\_ECDHE) where the asymmetric keys are changed per use; this provides [forward secrecy](http://en.wikipedia.org/wiki/Transport_Layer_Security#Forward_secrecy "http://en.wikipedia.org/wiki/Transport_Layer_Security#Forward_secrecy"). (But the majority of TLS servers use a static asymmetric key pair).
    5.  Keys in buffers should be actively overwritten in memory by software when the software is finished with the keys e.g. write zeros to the key array (rather than leaving them on the stack or heap).
4.  Keys should be unique per device
	  1.  Keys should be unique per device. The exception being backups for disaster recovery or duplication/redundancy for throughput per X9.24.
	
###  Verify and Validate your cryptography
  1. Validation (doing the right thing): Do a proof of concept early on to ensure the chosen cryptographic algorithms and key sizes work for the intended use case e.g. acceptable performance, supported by your tools, meet regulatory requirements, etc...
  2. Verification (doing the thing right):
	  1. [CAVP program](http://csrc.nist.gov/groups/STM/cavp/index.html "http://csrc.nist.gov/groups/STM/cavp/index.html") provides known good test vectors to test cryptographic implementations against i.e. does your solution provide the right answers.
	  2. Ask the vendor what independent verification has been done on their product.
	  3. Follow the vendor's guidance on how to configure and use the solution.
### Limit Error responses to the outside world
  1. While detailed error messages can be useful when building or debugging cryptographic solutions, they can also be very useful for attackers. In general, when an application encounters an error in a cryptographic protocol it should return to a high level context and return a generic failure to the outside observer – not specifics on the exact failure e.g. “invalid MAC”, “error in padding bytes” etc....

### Use Recommended Cryptography Algorithms 
####Security Strength 

|Security Strength |Do NOT use|Legacy/Current|New|
|---|---|---|---|
||80 to <112|112 to <128|\>=128|

The strength of all cryptographic primitives can be assessed quantitatively (called “bits of security”) that is based on known attacks on the algorithms.
This allows combination of different Cryptographic Primitives of equal strength to achieve an overall required system strength.

E.g. ACME bank overall system requires 128 bits of security. Therefore, the following can be used

1. AES-128
1. RSA-3072 or ECC 256
1. SHA-256


|Security Strength|Symmetric Key Algorithms|RSA Key public modulus length (bits)|ECC|Digital Signatures and hash-only applications|
|---|---|---|---|---|
|80|2TDEA (2 key Triple DES)|1024|160-223|SHA-1 SHA-224  SHA-256  SHA-384 SHA-512|
|112|3TDEA (3 key Triple DES)|2048|224-255|SHA-224 SHA-256 SHA-384 SHA-512|
|128|AES-128|3072|256-383|SHA-256 SHA-384 SHA-512|
|192|AES-192|7680|384-511|SHA-384 SHA-512|
|256|AES-256|15360|512+|SHA-512|


Note:
hash lengths are twice as long as the security bits offered by the symmetric/asymmetric algorithm e.g. SHA-224 for 3TDEA (112 security bits), SHA-256 for AES-128 (128 security bits) (due to the [http://en.wikipedia.org/wiki/Birthday_attack Birthday Attack])

####Primitives
|Primitives  |Do NOT use|Legacy/Current|New|Notes|
|---|---|---|---|---|
|Primitives||||Use higher-level Schemes instead Use CCM Authenticated Encryption Scheme instead of using AES Primitive directly|
|Symmetric Block Ciphers|DES or 2TDEA (2 key Triple DES)|3TDEA (Triple DES with triple length key)|AES-128||
|Hash Functions|MD2 MD4 MD5 SHA-0 (aka SHA)|SHA-224|SHA-256 (SHA-3  when final)|Per NIST SP 800-57 Recommendation for Key Management Part 1) SHA-1 is permitted in special circumstances only for legacy/current (hash-based message authentication codes (HMACs) key derivation functions (KDFs) and random number generators (RNGs). SHA-2 is better.|
|Hash Functions|Non-cryptographic hash function e.g. Cyclic Redundancy Check (CRC)||||
|Asymmetric Ciphers|RSA 1024 e=3|RSA 2048  e=65537|RSA 3072|Short Public Exponents e.g. 3 should be avoided|
|Asymmetric Ciphers||ECC 224|ECC 256||
|Asymmetric Ciphers||DSA group 2048 key224|||
  
#### Schemes
|Schemes|Do NOT use|Legacy/Current|New|Notes|
|---|---|---|---|---|
|Schemes||||Use higher-level Protocols instead e.g. use TLS 1.2 to secure data in transit rather than create your own protocol with crypto schemes or primitives.|
|Block Cipher Confidentialty Modes|ECB for encrypting data larger than a block length|Use Authenticated Encryption (with Associated Data) modes instead.|Use Authenticated Encryption (with Associated Data) modes instead.||
|Stream Ciphers||Use a  Block Cipher in streaming mode instead.|Use a  Block Cipher in streaming mode instead.||
|Block Cipher Authenticated Encryption Mode||CCM (preferable over GCM)|CCM (preferable over GCM)||
|Block Cipher Authenticated Encryption Mode||GCM|GCM||
|Block Cipher Authenticated Encryption Mode||AEAD_AES_128_CBC_HMAC_SHA_256|||
|Block Cipher Based MACs|CBC-MAC|CMAC|CMAC||
|Hash Function Based MACs||HMAC-SHA-224|HMAC-SHA-256 ||
|Public Key Encryption|RSAES-PKCS1-v1_5|RSAES-OAEP OAEPWithSha256AndMgf1|RSAES-OAEP OAEPWithSha256AndMgf1|X9.44 says the MGF1 should be X9-approved hash function with at least the target security level|
|Public Key Encryption||RSAES-KEM-KWS| RSAES-KEM-KWS||
|Public Key Signature||RSASSA-PKCS-v1_5  SHA-256|RSASSA-PKCS-v1_5  SHA-256||
|Public Key Signature||RSA PSS|RSA PSS||
|Public Key Signature||DSA|DSA||
|Public Key Signature||ECDSA using P-256 and SHA-256|ECDSA [FIPS 186-3  ANSI X9.62]| |
|Random Number Generator|DUAL_EC_DRBG |RBGs specified in SP 800-90 Rev 1 draft (HASH  HMAC  CTR) and ANS X9.62-2005 (HMAC)||NOTE: DUAL_EC_DRBG was withdrawn (due to vulnerabilities and controversy) and the standard was updated as  NIST SP 800-90 A Rev. 1 DRAFT Recommendation for Random Number Generation Using Deterministic Random Bit Generators|
|Key Agreement||DH [NIST SP 800-56A]|||
|Key Agreement||ECDH [NIST SP 800-56A]|||
|Key Agreement||ECMQV [NIST SP 800-56A]|||
|Key Wrapping||RSA PKCS1 v1.5 [PKCS #1 v2.1]|||
|Key Wrapping||RSA OAEP [NIST SP 800-56B]|||
|Key Wrapping||ECIES [ANSI X9.63]|||
|Key Wrapping||AES and Three-key Triple DES Key Wrap and Unwrap|||
|Key Wrapping||HMAC-based KDF|||
|Key Wrapping||CMAC-based KDF: AES-and Three-key Triple|||
   
#####Protocols
|Protcols  |Notes|Suite B where NSA Suite B is a subset of the NIST approved algorithms|                                                                                                                                                                   
|---|---|---|                                                                                                                                                                        
|TLS|Refer to OWASP Transport Layer Protection Cheat Sheet which references NIST Guidelines for the Selection Configuration and Use of Transport Layer Security (TLS) Implementations | Suite B Profile for Transport Layer Security (TLS) |
|IPSEC||Suite B Profile for Internet Protocol Security (IPsec)|                                                                                                                      
|SSH||See Suite B Cryptographic Suites for Secure Shell (SSH)|                                                                                                                       
|CMS S/MIME|Be aware of signature stripping attack when combining types e.g. EnvelopedData and SignedData together.|Suite B in Secure/Multipurpose Internet Mail Extensions (S/MIME)|


## Understanding Cryptography

![CryptographyOverview](images/CryptographyOverview.png?raw=true)


### Cryptographic Properties (Security Services)

#### Confidentiality

“Confidentiality” is defined as "no unauthorized disclosure of information".

Cryptography addresses this via encryption of either the data at rest or data in transit by protecting the information from all who do not hold the decryption key.

#### Integrity

"Integrity" ensures that no accidental or malicious alternation of data occurs.

Cryptography can be used to ensure integrity by means of Message Authentication Codes (MACs), or Digital Signatures, or hash functions with encryption.

#### Authentication

“Authentication” is the process of verifying a claim that a subject is who it says it is via some provided corroborating evidence. We use cryptography for authentication in several different ways.

##### Data origin authentication

“Data origin authentication” means assurance that a message or data item has been delivered as sent by a specified communication partner. Data origin authentication is a stronger form of integrity. Data origin authentication implicitly provides data integrity (because the origin of a message can only be guaranteed if the message has not changed).

##### Entity authentication

“Entity authentication” refers to assuring the presence of a specified communication partner and can be seen as a special case of data origin/message authentication where the identity of the entity is corroborated.

#### Non-repudiation

Non-repudiation comes in two flavors...non-repudiation of sender ensures that someone sending a message should not be able to deny later that he or she sent it. Non-repudiation of receiver means that the receiver of a message should not be able to deny that she received it. Cryptography can be used to provide non-repudiation by providing unforgeable messages or replies to messages e.g. a digital signature.

Non-repudiation implicitly provides Data origin authentication.

### Cryptographic Primitives

Cryptographic Primitives are the basic building blocks to provide the Cryptographic Properties described above. In general, Cryptographic Primitives should not be used directly; use a cryptographic protocol where possible, else use a cryptographic scheme.

Cryptographic Primitives can be characterised by

-   Strength
-   whether they use a key or not
-   whether they work on fixed size number of bits (block ciphers) or on a continuous stream of bits (stream ciphers)
-   whether same key is used for both encryption and decryption (symmetric ciphers) or separate keys for encryption and decryption (asymmetric ciphers)

#### Symmetric Key Ciphers

Symmetric ciphers encrypt and decrypt using the same key. This implies that if one party encrypts data that a second party must decrypt, those two parties must share a common key.

A simple analogy is a lock and key where the same key is required to lock and unlock a box:

-   only someone with the key required to lock the box can place a secret in a box and lock it
-   the sender and recipient have the key to the lock to open the box to get the secret

The recipient and sender must exchange the key first securely to make sure no one else can copy it.

Examples are DES and [AES](http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-197 "http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-197").

##### Block Ciphers and Stream Ciphers

Symmetric ciphers come in two main types:

1.  Block ciphers operate on a block of characters (typically 8 or 16 bytes) at a time.
2.  Stream ciphers operate on a single bit or byte at a time. Examples of a stream ciphers are RC4 (aka, ARC4) and Salsa20.
    1.  There are no NIST approved algorithms specifically designated as stream ciphers. However, some of the cryptographic modes defined in [SP 800-38](http://csrc.nist.gov/publications/PubsSPs.html#800-38A "http://csrc.nist.gov/publications/PubsSPs.html#800-38A") (CTR, OFB, or CFB) can be used with a symmetric cipher (e.g. AES), to perform the function of a stream cipher. And this is the recommended option over dedicated stream ciphers.
    2.  Do NOT repeat the key / IV pairs for stream ciphers or block ciphers operating in a streaming mode.
        1.  Because of the way stream ciphers work (or block ciphers operating in a streaming cipher mode), if you do use the same encryption key / IV pair to encrypt multiple plaintext messages, an adversary can simply take the resulting ciphertext streams and XOR them together. The result of this operation leaves a bit stream of the two plaintext messages XOR'd together, which the adversary can then analyze using statistical frequency analysis leading to the discovery of the two original plaintext messages. See [[1]](http://courseweb.stthomas.edu/resmith/c/csec/streamattack.html)

#### Hash Functions

[Cryptographic hashes](http://en.wikipedia.org/wiki/Cryptographic_hash_function "http://en.wikipedia.org/wiki/Cryptographic_hash_function"), also known as message digests, are functions that map arbitrary length bit strings to some fixed length bit string (referred to as the "hash value" or "digest value"). These hash functions are many-to-one mappings that are compression functions. To be useful in a cryptographic sense, a hash function H, operating on input x such that digest value d = H(x), must have the following three properties:

1.  **Pre-image resistance:** They must be one-way functions. That is, given hash algorithm H and digest value d, it is computationally infeasible to compute input x.
2.  **Second pre-image resistance:**Given input x such that d = H(x), it is computationally infeasible to find a second input x' not equal to x, such that H(x') yields the same digest value d.
3.  **Collision resistance**:**It is computationally infeasible to find two different inputs, x and x' such that both hash to the same value; that is, such that H(x) == H(x') where x != x'.

Such cryptographic hash functions are used to provide data integrity.

They can be used to:

1.  store a non-secret value derived from the password/passphrase that can be used to validate the password/passphrase without having to store the password/passphrase
2.  extend a relatively small bit of entropy so that secure random number generators can be constructed
3.  implement various Cryptographic Schemes e.g. Hash Function Based MACs

SHA-2 is defined and approved in [FIPS-180-4 Secure Hash Standard (SHS)](http://csrc.nist.gov/publications/PubsFIPS.html#fips180-4 "http://csrc.nist.gov/publications/PubsFIPS.html#fips180-4")

[SHA-3](http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-202 "http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-202") , aka Keccak, is intended to replace SHA2; it is currently a draft publication.

#### Asymmetric Ciphers

Asymmetric ciphers encrypt and decrypt with two different keys. One key generally is designated as the private key and the other is designated as the public key. The public key generally is widely shared.

A simple analogy is a lock and key where no key is required to lock a box, a key is required to unlock the box:

1.  anyone can place a secret in a box and lock it with the recipients lock
2.  only the recipient has the key to the lock to open the box to get the secret

In this case the recipient can send the sender a lock first (without having to send a key). The problem becomes one of ensuring the sender got the recipients lock (not someone else's).

Asymmetric ciphers can be classified by the mathematical problem they are based on:

1.  Integer Factorization Problem: e.g. [(Rivest, Shamir Adleman) RSA](http://en.wikipedia.org/wiki/RSA_(cryptosystem) "http://en.wikipedia.org/wiki/RSA_(cryptosystem)")
2.  Discrete Log Problem
    1.  Finite Field Discrete Log Problem: e.g. [Digital Signature Algorithm](http://en.wikipedia.org/wiki/Digital_Signature_Algorithm "http://en.wikipedia.org/wiki/Digital_Signature_Algorithm") ([DSA](http://en.wikipedia.org/wiki/Digital_Signature_Algorithm "http://en.wikipedia.org/wiki/Digital_Signature_Algorithm"))
    2.  Elliptic Curve Discrete Log Problem: e.g. [Elliptic Curve Digital Signature Algorithm (ECDSA](http://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm "http://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm")

##### ECC vs RSA

ECC can do what RSA does (major downsides being potential [patent issues](http://en.wikipedia.org/wiki/ECC_patents "http://en.wikipedia.org/wiki/ECC_patents"))

ECC can do things that RSA can't do:

1. Scale to stronger keys. RSA key sizes become unwieldly for 256 bits of security. The table in Cryptograpic Strength shows that RSA key sizes (and therefore the resulting encrypted or signed payload) become significantly larger for 128 and 256 bit security strength. EC keys don't.
2.  [Implicit Certificates](http://en.wikipedia.org/wiki/Implicit_certificate "http://en.wikipedia.org/wiki/Implicit_certificate")    e.g. 120 byte certificates rather than the \>= 3KB certificates used for RSA
3.  [Identity Based Encryption](http://en.wikipedia.org/wiki/ID-based_encryption "http://en.wikipedia.org/wiki/ID-based_encryption") (technically you can do IBE with RSA but it's not elegant/standard). Pairings is another primitive or mathematical problem that IBE is based on but out of scope for this guide.
4.  [Short Signature Schemes](http://en.wikipedia.org/wiki/Boneh%E2%80%93Lynn%E2%80%93Shacham "http://en.wikipedia.org/wiki/Boneh%E2%80%93Lynn%E2%80%93Shacham")     if n is the security strength e.g. 128 bits, required then BLS signatures (based on ECC) is 2n (256bits), ECDSA signatures are 4n bits (512 bits) and RSA signature is 3072bits for RSA 3072.
    

### Cryptographic Schemes

### Block Cipher Modes

[Block ciphers](http://en.wikipedia.org/wiki/Block_cipher_modes_of_operation "http://en.wikipedia.org/wiki/Block_cipher_modes_of_operation") can function in different modes of operations known as "cipher modes". This cipher mode algorithmically describes how a cipher operates to repeatedly apply its encryption or decryption mechanism to a given cipher block. Cipher modes are important to have an awareness of because they have an enormous impact on both the confidentiality and the message authenticity of the resulting ciphertext messages.

Only [NIST approved block cipher modes](http://csrc.nist.gov/groups/ST/toolkit/BCM/current_modes.html "http://csrc.nist.gov/groups/ST/toolkit/BCM/current_modes.html") will be referred to below and these should be used where possible. A complete list of (proposed but not approved) modes may be found on the [NIST Modes Development page](http://csrc.nist.gov/groups/ST/toolkit/BCM/modes_development.html "http://csrc.nist.gov/groups/ST/toolkit/BCM/modes_development.html").

[Evaluation of Some Blockcipher Modes of Operation](http://web.cs.ucdavis.edu/~rogaway/papers/modes.pdf "http://web.cs.ucdavis.edu/~rogaway/papers/modes.pdf") is a comprehensive analysis of these modes.

#### Initialization Vectors

In cryptography, an initialization vector (IV) is a fixed size input to a block cipher's encryption / decryption primitive. The IV is recommended (and in many cases, required) to be random or at least pseudo-random. We will discuss IVs and their related requirements later in this document.

#### Padding

Block ciphers generally operate on fixed size blocks (the exception is when they are operating in a "streaming" mode). However, these ciphers must also operate on messages of any sizes, not just those that are an integral multiple of the cipher's block size.

Therefore [padding](http://en.wikipedia.org/wiki/Padding_(cryptography) "http://en.wikipedia.org/wiki/Padding_(cryptography)") schemes are used which pad out the plaintext to a multiple of the block size.

A streaming cipher or a block cipher using a streaming mode such as OFB, CFB, CTR, etc. does not require padding. However, we recommend that you use padding with any block cipher that uses a block mode (e.g., CBC). For symmetric block ciphers, PKCS7 (RFC 5652) or PKCS5 padding are good choices as they are supported by almost all cryptographic libraries. For most practical purposes, PKCS5 padding is the same as PKCS7 padding, except that technically, PKCS5 padding can only be used to pad ciphers whose block size is 64 bits (In fact, the standard SunJCE cryptographic provider in Java supports only PKCS5 padding, but not PKCS7 padding. On the other hand, the .NET Framework supports only PKCS7 padding, but not PKCS5 padding. Fortunately, in practice, these two padding schemes can generally used interchangeably.)

##### Ciphertext Stealing

[NIST SP 800-38A Addendum](http://csrc.nist.gov/publications/PubsSPs.html#800-38A-addendum "http://csrc.nist.gov/publications/PubsSPs.html#800-38A-addendum") defines Ciphertext Stealing for CBC modes that avoids padding (ciphertext expansion). XTS-AES also uses Ciphertext Stealing.

#### Initialization Vectors

In cryptography, an initialization vector (IV) is a fixed size input to a block cipher's encryption / decryption primitive. The IV is recommended (and in many cases, required) to be random or at least pseudo-random. The IV is not secret (Confidentiality) but need to ensure it can't be manipulated (Integrity).

#### Block Cipher Confidentiality Modes

[Five Confidentiality Modes](http://csrc.nist.gov/publications/PubsSPs.html#800-38A "http://csrc.nist.gov/publications/PubsSPs.html#800-38A"): ECB, CBC, CFB, and OFB, CTR mode are defined under [NIST approved block cipher modes](http://csrc.nist.gov/groups/ST/toolkit/BCM/current_modes.html "http://csrc.nist.gov/groups/ST/toolkit/BCM/current_modes.html")

These modes give Confidentiality only i.e. not Integrity or Authenticity. In other words, they hide the plaintext but do not prevent the plaintext from being manipulated by manipulating the ciphertext (such that when the recipient decrypts it they get different plaintext).

**For this reason, Authenticated Encryption modes should be used instead where possible.**

Almost all cryptographic libraries support the four original DES cipher modes of ECB, CBC (Cipher Block Chaining), OFB (Output Feedback), and CFB (Cipher Feedback). Many also support CTR (Counter) mode.The five modes have different properties from one another e.g. error propagation, performance (e.g. in CTR mode the DES/AES computation can be done before the plaintext/ciphertext is available – just leaving an XOR operation to be done when it is, whether the blocks can be encrypted or decrypted in parallel).

##### ECB

The simplest cipher mode, and unfortunately often the only one introduced in introductory textbooks or cryptography examples, is known as Electronic Codebook (ECB). ECB mode is simply a repeated application of the block cipher's raw encryption (or decryption) operation on the corresponding block of plaintext (or ciphertext for decryption). As simple as ECB mode is, it almost always should be avoided as it is fraught with various easily exploitable cryptographic vulnerabilities. This is illustrated clearly in [Electronic Codebook (ECB)](http://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Electronic_Codebook_.28ECB.29 "http://en.wikipedia.org/wiki/Block_cipher_mode_of_operation#Electronic_Codebook_.28ECB.29").

All cipher modes other than ECB require an "initialization vector" (IV) to initialize the encryption process.

Using a cipher in its "raw" form is referred to as Electronic Code Book (ECB) mode. When encrypting using ECB, the plaintext message is divided into blocks (corresponding to the cipher algorithm's block size) and each block is encrypted individually with no interaction with any other blocks. Unfortunately, except when the plaintext message is less than the cipher's block size (typically 128 or 64 bits) ECB mode should generally be avoided because it has many cryptographic weaknesses.

##### CBC, CFB, OFB, CTR

All these other modes chain blocks together by taking some part of the current block and providing it as an input to the next block

For these Block Chaining Modes, it can be seen from the diagrams in [[1]](http://en.wikipedia.org/wiki/Block_cipher_mode_of_operation) that the ciphertext is XOR'd with the plaintext of current block or next block together

Flipping (inverting) a bit in the ciphertext leads to one or more bits being flipped somewhere in the ciphertext (this can be seen from the diagrams or from the Error Propagation characteristics of the mode [SP 800-38A](http://csrc.nist.gov/publications/PubsSPs.html#800-38A "http://csrc.nist.gov/publications/PubsSPs.html#800-38A") "Appendix D: Error Properties".) e.g.

1.  CTR mode: If 1 bit is flipped in ciphertext (after the encryption) then 1 bit in the plaintext is flipped at same position in the decrypted result (and no other blocks are affected)
2.  CBC mode: If 1 bit is flipped in ciphertext then 1 bit in the next plaintext block at same position is flipped (and the plaintext in current block is changed randomly i.e. changed ciphertext for current block will decrypt to something completely different)

If some of the plaintext is known e.g. values occuring at a fixed location in the message – in the information itself or the padding, then this allows the plaintext to be manipulated independent of the cryptography i.e. **without knowing or caring about the underlying cipher, the Key or IV**.

This is fine when the plaintext is secret/unknown but can be catastrophic when some information about the plaintext is known or can be guessed easily e.g.

1. due to padding the value may be known or easily guessed (If the system returns an error for an incorrect decryption (because of invalid padding values) it allows an attacker to create an xor-mask as above to systematically deduce the plaintext)
2. If the plaintext follows a known format with values in known locations e.g. a transaction with a value amount where the flip of a bit can change a small transaction amount to a large transaction amount.

**Just because the data is encrypted does not mean it can't be manipulated knowingly by an attacker – and this is why checks to see if the data changed or not should also be done.**

In other words, these **[Confidentiality Modes](http://csrc.nist.gov/publications/PubsSPs.html#800-38A "http://csrc.nist.gov/publications/PubsSPs.html#800-38A") do what they are designed to do i.e. give Confidentiality only i.e. not Integrity or Authenticity; use Authenticated Encryption modes instead where possible!**




##### XTS-AES

[A Confidentiality Mode Designed For Storage Devices](http://csrc.nist.gov/publications/PubsSPs.html#800-38E "http://csrc.nist.gov/publications/PubsSPs.html#800-38E") XTS-AES is approved by NIST. It was originally standardized in [IEEE P1619 Standard for Cryptographic Protection of Data on Block-Oriented Storage Devices](http://en.wikipedia.org/wiki/IEEE_P1619 "http://en.wikipedia.org/wiki/IEEE_P1619").

[XTS-AES mode](http://csrc.nist.gov/publications/nistpubs/800-38E/nist-sp-800-38E.pdf "http://csrc.nist.gov/publications/nistpubs/800-38E/nist-sp-800-38E.pdf") is optimized for Disk encryption; it provides confidentiality and some protection against data manipulation (more than the [Five Confidentiality Modes](http://csrc.nist.gov/publications/PubsSPs.html#800-38A "http://csrc.nist.gov/publications/PubsSPs.html#800-38A") but not as much as the [AE](http://en.wikipedia.org/wiki/Authenticated_encryption "http://en.wikipedia.org/wiki/Authenticated_encryption") [NIST approved modes](http://csrc.nist.gov/groups/ST/toolkit/BCM/current_modes.html "http://csrc.nist.gov/groups/ST/toolkit/BCM/current_modes.html")). Specifically, it is designed to prevent an attacker from manipulating the data in a controlled way – not to detect if data was changed.

It uses [Ciphertext Stealing](http://en.wikipedia.org/wiki/Disk_encryption_theory#XEX-based_tweaked-codebook_mode_with_ciphertext_stealing_.28XTS.29 "http://en.wikipedia.org/wiki/Disk_encryption_theory#XEX-based_tweaked-codebook_mode_with_ciphertext_stealing_.28XTS.29") to avoid padding of data and to to support storage media sectors with size not divisible by block size.

#### Authenticated Encryption

Authenticated Encryption (AE) is any block cipher mode that provides confidentiality, data integrity, and authenticity of the data. Specifically AE ensures the authenticity of the ciphertext (or more generally, the IV and ciphertext) in a manner that can guarantee that the IV and/or ciphertext has not been tampered with. This is important as it prevents chosen ciphertext attacks such as padding oracle attacks.

In general, one should prefer authenticated encryption modes.

Two Authenticated Encryption (AE) Modes are approved by NIST (and are not encumbered by patents):

1.  Counter with CBC-MAC (CCM) [Third Part: An Authenticated Encryption Mode](http://csrc.nist.gov/publications/PubsSPs.html#800-38C "http://csrc.nist.gov/publications/PubsSPs.html#800-38C")
2.  Galois/Counter Mode (GCM): [Fourth Part: A High-Throughput Authenticated Encryption Mode](http://csrc.nist.gov/publications/PubsSPs.html#800-38D "http://csrc.nist.gov/publications/PubsSPs.html#800-38D")

CCM is the simpler of the two and easier to get right as a user.

[Note to Java developers: Oracle's JDK 7 now supports both CCM and GCM in the SunJCE. If you are using an earlier JDK release, you can use Bouncy Castle as your JCE provider. In lieu of using an AE cipher mode, you can "wrap" an HMAC around the IV and ciphertext and check its validity before decrypting. (The so-called "encrypt-then-MAC" approach. [6]) This is the approach that OWASP ESAPI 2.x (Java) has taken when an AE cipher mode is not available; in fact, it is ESAPI 2.x's default mode for symmetric encryption. There is no standard supported AE mode in Microsoft's .NET Framework, however some members of the .NET security team have made a .NET assembly supporting both CCM and GCM modes available [here](http://blogs.msdn.com/b/shawnfa/archive/2009/03/17/authenticated-symmetric-encryption-in-net.aspx "http://blogs.msdn.com/b/shawnfa/archive/2009/03/17/authenticated-symmetric-encryption-in-net.aspx").

ISO/IEC 19772 (2009) "Information technology — Security techniques — Authenticated encryption" specifies the following Authenticated Encryption Modes:

1.  OCB 2.0 (gives one pass Authenticated Encryption). See [Patents](http://en.wikipedia.org/wiki/OCB_mode#Patents "http://en.wikipedia.org/wiki/OCB_mode#Patents") for patents and exemptions.
2.  Key Wrap
3.  **CCM**
4.  EAX – no patents per EAX [Patent status](http://en.wikipedia.org/wiki/EAX_mode#Patent_status "http://en.wikipedia.org/wiki/EAX_mode#Patent_status")
5.  Encrypt-then-MAC (this is a generic description – not an exact specification of encrypting then MAC'ing)
6.  **GCM**


##### Encrypt-then-MAC

**Only if it is not possible to use a NIST approved AE mode** (e.g. not supported in your implementation) then you can use

1.  [EAX](http://en.wikipedia.org/wiki/EAX_mode "http://en.wikipedia.org/wiki/EAX_mode")
2.  [AEAD AES 128 CBC HMAC SHA 256](http://tools.ietf.org/html/draft-mcgrew-aead-aes-cbc-hmac-sha2-04 "http://tools.ietf.org/html/draft-mcgrew-aead-aes-cbc-hmac-sha2-04") is an encrypt-then-MAC approach with two separate block ciphers (AES-128 CBC, HMAC-SHA-256)

###### Why encrypt and then MAC?

There are three possible approaches to applying a MAC to ensure the authenticity of ciphertext.

1.  MAC-and-encrypt, which the sender computes a MAC of the plaintext, encrypts the plaintext, and then appends the MAC to the IV and ciphertext.
2.  MAC-then-encrypt, where the sender computes a MAC of the plaintext, then encrypts both the plaintext (and generally, the IV) and the MAC.
3.  encrypt-then-MAC approach where the sender encrypts the plaintext, then appends a MAC of the IV plus ciphertext.

Of these three mechanisms, only the encrypt-then-MAC has proven to resist known cryptographic attacks (when implemented correctly).

#### MACs

When used to provide data integrity, cryptographic functions come in two flavors, keyed hashes (called "message authentication codes") and unkeyed hashes (called "message integrity codes").

Hash Function Based MACs are typically faster than Block Cipher Based MACs.

[Evaluation of Some Blockcipher Modes of Operation](http://web.cs.ucdavis.edu/~rogaway/papers/modes.pdf "http://web.cs.ucdavis.edu/~rogaway/papers/modes.pdf") is a comprehensive analysis of these modes.

#### Block Cipher Based MACs

[An Authentication Mode](http://csrc.nist.gov/publications/PubsSPs.html#800-38B "http://csrc.nist.gov/publications/PubsSPs.html#800-38B"): CMAC is approved by NIST.

#### Hash Function Based MACs

[HMAC](http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-198--1 "http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-198--1") is approved by NIST.

### Asymmetric Key

#### Public Key Encryption

##### RSA

RSA Primitives should not be used directly. Instead an RSA “padding scheme” should be used that addresses the security issues of using the RSA primitive directly.

A good survey of cryptographic attacks is given in [Twenty Years of Attacks on the RSA Cryptosystem](http://crypto.stanford.edu/~dabo/papers/RSA-survey.pdf "http://crypto.stanford.edu/~dabo/papers/RSA-survey.pdf").

ANSI X9.44, "Key Establishment Using Integer Factorization Cryptography" (which NIST [SP.800-56B Rev 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Br1.pdf "http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Br1.pdf") is based on) defines schemes for RSA encryption and signing.

###### RSA encryption:

1.  RSAES-PKCS1-v1\_5 ([PKCS \#1 v2.](http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf "http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf")[2](http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf "http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf"), [FIPS 186-](http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-186--4 "http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-186--4")[4](http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-186--4 "http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-186--4")): the original encryption scheme. Vulnerable to chosen ciphertext attack (CCA) Do not use. Deprecated in 
2.   1.3. The maximum length of any message that can be encrypted is k-11 where k is the RSA modulus length e.g. 384 bytes for RSA 3072.
2.  [RSAES-OAEP](http://en.wikipedia.org/wiki/Optimal_asymmetric_encryption_padding "http://en.wikipedia.org/wiki/Optimal_asymmetric_encryption_padding") (([PKCS \#1 v2.](http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf "http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf")[2](http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf "http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf"), NIST [SP.800-56B Rev 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Br1.pdf "http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Br1.pdf") ): RSA with Optimal Asymmetric Encryption Padding improves on RSAES-PKCS1-v1\_5 security
3.  RSAES-KEM-KWS: most recent but least used. Avoids the need for padding by using a symmetric keywrapping algorithm. This has the advantage that the length of the data that can be encrypted is not limited.

###### [RSAES-OAEP](http://en.wikipedia.org/wiki/Optimal_asymmetric_encryption_padding "http://en.wikipedia.org/wiki/Optimal_asymmetric_encryption_padding")

ANSI X9.44 says the MGF1 should be “X9-approved hash function with at least the target security level” i.e. for 128 bit security strength, SHA256 should be used (see Cryptography Strength section).

Not all cryptographic libraries support RSAES-OAEP With **Sha256**AndMgf1 (SHA1 is used). Reference code is available online on how to add Sha256 support to common cryptographic libraries.

The maximum length of any message that can be encrypted is:

k - (2 \* hLen) – 2 where k is the RSA modulus length e.g. 384 bytes for RSA 3072

and hLen is the \# of octets in the chosen hash function. e.g. 32 bytes for SHA356

e.g. for RSA 3072 the maximum length of any message that can be encrypted 318 bytes = 384 - (2 \* 32) – 2

###### ECDH

[Suite B Implementer’s Guide to NIST SP 800-56A](https://www.nsa.gov/ia/_files/SuiteB_Implementer_G-113808.pdf "https://www.nsa.gov/ia/_files/SuiteB_Implementer_G-113808.pdf")

TODO ECC and DH enc

##### Hybrid cryptosystems

Asymmetric ciphers are several orders of magnitude slower than symmetric ciphers. Because of that, they are used frequently in hybrid cryptosystems, which combine asymmetric and symmetric ciphers. In such hybrid cryptosystems, a random symmetric "session" key (i.e., a key only used for the duration of the encrypted communication) is generated. This random session key is then encrypted using an asymmetric cipher and the recipient's public key. The plaintext data itself is encrypted with the session key. Then the entire bundle (encrypted session key and encrypted message) is all sent together.

Both TLS and S/MIME are common cryptosystems using hybrid cryptography.

#### Public Key Signatures

Digital signatures are a cryptographically unique data string that is used to ensure data integrity and prove the authenticity of some digital message. and that associates some input message with an originating entity. A digital signature generation algorithm is a cryptographically strong algorithm that is used to generate a digital signature.

[FIPS 186-4 Digital Signature Standard (DSS)](http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-186--4 "http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-186--4") defines 3 signature schemes based on RSA, DSA, ECDSA.

##### RSA

###### RSA signature

1.  RSASSA-PKCS1-v1\_5 ([PKCS \#1 v2.](http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf "http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf")[2](http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf "http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf"), ): the original signature scheme
    1.  OK to use but [RSA-PSS considered more secure](http://www.emc.com/emc-plus/rsa-labs/historical/raising-standard-rsa-signatures-rsa-pss.htm "http://www.emc.com/emc-plus/rsa-labs/historical/raising-standard-rsa-signatures-rsa-pss.htm")

2.  RSASSA-PSS ([PKCS \#1 v2.](http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf "http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf")[2](http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf "http://www.emc.com/collateral/white-papers/h11300-pkcs-1v2-2-rsa-cryptography-standard-wp.pdf"), [FIPS 186-4 Digital Signature Standard (DSS)](http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-186--4 "http://csrc.nist.gov/publications/PubsFIPS.html#FIPS-186--4")): improved probabilistic signature scheme with appendix
    1.  more recent and secure but less used

###### DSA

DSA is specified in “X9.30 Public Key Cryptography Using Irreversible Algorithms - Part 1: The Digital Signature Algorithm (DSA)”

###### ECDSA

The Elliptic Curve Digital Signature Algorithm (ECDSA) is specified in ANS X9.62 [Public Key Cryptography for the Financial Services Industry, The Elliptic Curve Digital Signature Algorithm (ECDSA](http://webstore.ansi.org/RecordDetail.aspx?sku=ANSI+X9.62%3A2005 "http://webstore.ansi.org/RecordDetail.aspx?sku=ANSI+X9.62%3A2005"))

[Suite B Implementer’s Guide to FIPS 186-3 (ECDSA)](https://www.nsa.gov/ia/_files/ecdsa.pdf "https://www.nsa.gov/ia/_files/ecdsa.pdf") defines requirements for obtaining the assurances necessary for valid digital signatures e.g. like only using the key pair for signatures and not other purpose per the recommendations in this guide.

### Random Number Generation

Random Number Generation output is used for various purposes, such as the generation of keys, IV’s, MAC tags, nonces and authentication challenges, random file names, random GUIDs, and random strings

![RNG](images/RNG.png?raw=true)

- A: random output is based on some function of current state
- B: Internal state is updated based on some function of previous state
- Non-deterministic events are e.g. system time, user interaction e.g. via keyboard or mouse interrupts, etc...) are used to influence internal state for Hybrid PRNG


The seed is used when the RNG starts only to seed or “get things going”. The seed should be random. When the RNG starts, the issue arises of where to get the randomness for the seed. Catch-22.

-   The RNG output should be used to update the seed periodically so the next time the RNG starts, a new random seed is input.
-   The very first time the RNG starts the very first seed should have randomness – **from multiple independent sources**:
    -   e.g. from another RNG on another device. Could be another PC or could be a TRNG built into the PC.
    -   e.g. from a once-off RNG setup step where several non-deterministic events provide the randomness (entropy).
    -   e.g. From a hardware or TRNG built into the PC (when use with other sources) “[Relying solely on the hardware random number generator which is using an implementation sealed inside a chip which is impossible to audit is a BAD idea](http://en.wikipedia.org/wiki/RdRand "http://en.wikipedia.org/wiki/RdRand")[[1]](http://en.wikipedia.org/wiki/RdRand)“

-   Then the RNG can be invoked to get a large sample of data that is then deleted.
-   The “Recommendations for algorithms” apply equally to RNGs especially **“Use a conservative minimum trusted set of primitives and schemes”. Vulnerabilities in underlying RNGs can render your cryptographic primitives/schemes/protocols broken!** e.g. SW [Dual\_EC\_DRBG](http://en.wikipedia.org/wiki/Dual_EC_DRBG "http://en.wikipedia.org/wiki/Dual_EC_DRBG"), e.g. [HW RNG RdRand](http://en.wikipedia.org/wiki/RdRand "http://en.wikipedia.org/wiki/RdRand") See also [Random number generator attack](http://en.wikipedia.org/wiki/Random_number_generator_attack "http://en.wikipedia.org/wiki/Random_number_generator_attack").

   
#### Characteristics of a good RNG and associated recommendations
The following recommendations apply specifically to RNGs based on the characteristics of a good RNG 

1.  The output should pass statistical tests for randomness
	1.  Use RNG [NIST SP800-22 A Statistical Test Suite for Random and](http://csrc.nist.gov/publications/PubsSPs.html#800-22 "http://csrc.nist.gov/publications/PubsSPs.html#800-22")[Pseudorandom Number Generators for Cryptographic Applications](http://csrc.nist.gov/publications/PubsSPs.html#800-22 "http://csrc.nist.gov/publications/PubsSPs.html#800-22") (as used in PCI PTS Derived Test Requirements) that runs various statistical tests to assess the output.
        1.  It involves taking, e.g. 128MB of, RNG output and then passing it as input to the provided assessment tool. This is typically performed **before the product is deployed**- not at runtime.
        2.  In some cases, one of the statistical tests in the suite can be borderline fail. The tool should be run again several times with a new set of random data from the RNG to see if this is a consistent failure.
    2.  It is also worth performing **runtime** sanity checks on the RNG to ensure it is operating correctly.
1.  It should not be possible to predict the next output (even if all previous output and the algorithm used is known)
	1.  The seed should not be re-used and should be updated periodically so that the next time the RNG starts and is seeded, a different value is used.
    2.  The Confidentiality and Integrity of the seed is critical to ensure this. The updated seed value is typically stored in a file (so it is preserved across power off). Access to this file should be restricted.
    3.  The very first time the RNG is used in a live environment, some once-off setup should be used to ensure initial seed is random.
1.  The output sequence should not repeat
	1.  The period of a DRNG is defined by the algorithm that implements it and so can be determined.
    2.  This can be assessed against the amount of random output required by the application.


#### RNG Types

The broad types of Random Number Generator (aka Random Bit Generators(RBG)) are:

1.  Deterministic (aka Pseudo Random Number Generator (PRNG))
    1.  The output is completely determined by the seed and future output depends only on current internal state
2.  Non-Determinstic (aka True Random Number Generator (TRNG))
    1.  Physical
        1.  use non-deterministic events of electronic circuits e.g. thermal noise.
    2.  Non-Physical
        1.  exploit non-deterministic events (e.g. system time, user interaction e.g. via keyboard or mouse interrupts, etc...)

There are hybrid versions of all these that combine elements from the other types e.g. Determinstic RNG that accepts additional input based on non-deterministic events.

RNGs used on computers are typically either
1.  PRNG
2.  Hybrid PRNG

TRNG's can be used to create a seed for a PRNG but other non-deterministic events should be used also in this case (either to affect the seed or internal state or both); and the PRNG creates the random output.

See also [Randomness Requirements for Security](http://tools.ietf.org/html/rfc4086 "http://tools.ietf.org/html/rfc4086").


## Key Management


![KeyMgmt](images/KeyMgmt.png?raw=true)

[Oasis Cryptographic Key Management](http://xml.coverpages.org/keyManagement.html "http://xml.coverpages.org/keyManagement.html") provides a comprehensive list of bodies and standards for Key Management inclduding NIST SP 800-130 [A Framework for DesigningCryptographic Key ManagementSystems](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-130.pdf "http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-130.pdf")

For the Financial Services industry the main standards and references are

1.  ANSI X9.24 Retail Financial Services Symmetric Key Management Part 1: Using Symmetric Techniques for the Distribution of Symmetric Keys
2.  ANSI X9 X9.24-2-2006 Retail Financial Services Symmetric Key Management Part 2: Using Asymmetric Techniques for the Distribution of Symmetric Keys
3.  [PCI PIN Security Requirements v2](https://www.pcisecuritystandards.org/documents/PCI_PIN_Security_Requirements_v2.pdf "https://www.pcisecuritystandards.org/documents/PCI_PIN_Security_Requirements_v2.pdf")

### Key Derivation

A [key derivation function](http://en.wikipedia.org/wiki/Key_derivation_function "http://en.wikipedia.org/wiki/Key_derivation_function") (KDF) is a deterministic algorithm to derive a key of a given size from some secret value. If two parties use the same shared secret value and the same KDF, they should always derive exactly the same key.

[PBKDFs](http://en.wikipedia.org/wiki/PBKDF2 "http://en.wikipedia.org/wiki/PBKDF2") (Password Based Key Derivation Functions) are designed to encrypt data, typically keys, based on a password. The password is mixed with a salt (e.g. random 8 bytes) to form an intermediate key (Key Encryption Key) and this is used to encrypt the data/key.

Passwords have a relatively small keyspace (limited by typeable characters on a keyboard and passwords that people can remember) compared to randomly generated data of the same length.Therefore, a salt is added to prevent dictionary attacks. The process is repeated many times (based on a count e.g. 1000) to deter brute force attacks (key stretching).

[NIST SP 800-108 Recommendation for Key Derivation Using Pseudorandom Functions](http://csrc.nist.gov/publications/nistpubs/800-108/sp800-108.pdf "http://csrc.nist.gov/publications/nistpubs/800-108/sp800-108.pdf")and [NIST 800-56C Recommendation for Key Derivation through Extraction-then-Expansion](http://csrc.nist.gov/publications/nistpubs/800-56C/SP-800-56C.pdf "http://csrc.nist.gov/publications/nistpubs/800-56C/SP-800-56C.pdf") are NIST approved KDFs.

[SP 800-135 Rev 1 Recommendation for Existing Application-Specific Key Derivation Functions](http://csrc.nist.gov/publications/nistpubs/800-135-rev1/sp800-135-rev1.pdf "http://csrc.nist.gov/publications/nistpubs/800-135-rev1/sp800-135-rev1.pdf") lists security requirements for other KDFs e.g. HKDF, IKE-v1-KDF and IKE-v2-KDF, X9.63-KDF.

### Key Wrapping

TODO

### Key Exchange

Key exchange algorithms (also referred to as key establishment algorithms) are protocols that are used to exchange secret cryptographic keys between a sender and receiver in a manner that meets certain security constraints. Key exchange algorithms attempt to address the problem of securely sharing a common secret key with two parties over an insecure communication channel in a manner that no other party can gain access to a copy of the secret key. Traditionally this has relied on two humans somehow securely exchanging keys out-of-band; e.g., via a direct face-to-face meeting or mailing an attachment as an encrypted zip file that is encrypted with a previously shared passphrase, etc. However, the traditional methods do not allow two unknown parties who have never met to exchange a secret key with each other. In fact, proof of (or at least, high confidence in) identity is a major unsolved problem in such cases.

Key Agreement protocols are protocols whereby N parties (usually two) can agree on a common key with all parties contribute to the key value. When designed and implemented properly, key agreement protocols prevent adversaries from learning the key or forcing their own key choice on the participating parties.

The most familiar key exchange algorithm is Diffie-Hellman Key Exchange. There are also password authenticated key exchange algorithms. RSA key exchange using PKI or webs-of-trust or trusted key servers are also commonly used.

Key Transport protocols are where one party generates the key and sends it securely to the recipient(s).

The selection of schemes specified in [NIST Special Publication 800-56A](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Ar2.pdf "http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Ar2.pdf")[Revision 2](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Ar2.pdf "http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Ar2.pdf")[Recommendation for Pair-Wise Key Establishment Schemes Using Discrete Logarithm Cryptography](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Ar2.pdf "http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-56Ar2.pdf")based on standards for key-establishment

Key Exchange protocols based on different primitives are available:

1.  X9.42 Public Key Cryptography for the Financial Services Industry: Agreement of Symmetric Keys Using Discrete Logarithm Cryptography:
    1.  “This standard, partially adapted from ISO 11770-3 (see [13]), specifies schemes for the agreement of symmetric keys using Diffie-Hellman and MQV algorithms. It covers methods of domain parameter generation, domain parameter validation, key pair generation, public key validation, shared secret value calculation, key derivation, and test message authentication code computation for discrete logarithm problem based key agreement schemes”
1.  X9.44 Key Establishment Using Integer Factorization Cryptography. 
	1.  Key transport based on the RSA algorithm.
2.  X9.63 Public Key Cryptography for the Financial Services Industry: Key Agreement and Key Transport Using Elliptic Curve Cryptography

Key Transport protocols used in the financial industry:

1.  ASC X9 TR-31-2005 - “Interoperable Secure Key Exchange Key Block Specification for Symmetric Algorithms” specified a scheme for transporting a key based on a pre-existing shared key.
2.  ASC X9 TR-34 “Interoperable Method for Distribution of Symmetric Keys using Asymmetric Techniques: Part 1 - Using Factoring-Based Public Key Cryptography Unilateral Key Transport” is similar to X9 TR-31 but uses asymmetric ciphers (to avoid having to have a pre-existing symmetric key). It uses CMS EnvelopedData (X9.44 OAEP), and SignedData types (X9.44 RSASSA-PKCS-v1\_5).

  
### Key Lifecycle

##### Generation

[NIST SP 800-133 Recommendation for Cryptographic Key Generation](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-133.pdf "http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-133.pdf") discusses the generation of keys to be used with the approved cryptographic algorithms.

ANSI X9.24 Part 1 provides details on what forms keys can exist outside the Secure Cryptographic Device (SCD) e.g. Hardware Security Module (HSM) that they were generated in.

###### Symmetric Keys

For symmetric keys (e.g. AES, DES), the highest level key is generated randomly e.g. 16 bytes from an RNG for an AES-128 key.

If there is no prior trust with the receiving entity then the highest level symmetric key is generally split into multiple plaintext components for distribution to the other party via out-of-band manual means.

Key operations that involve people generally require at least dual control split knowledge to ensure no one person has all the key material e.g. 2 parties have a key or password component that is only effective when combined with the other part.

Further keys may be derived from this highest level key e.g. using a KDF with device identifier or serial number as input.

In general a “tag-and-bag” scheme is used for these keys:

1. tag: since the key is just random bytes the end user needs to know information about the key when they receive it e.g. what the key should be used for, the algorithm to use e.g. DES or AES , etc... This information is represented by additional information that is distributed with the key and is called a Key Block Header (KBH)
2. bag: cryptographic schemes are applied to the key such that Confidentiality-Integrity-Authenticity is assured.

Examples include:

1. ANSI **X9 TR-31 2**010 Interoperable Secure Key Exchange Key Block Specification for Symmetric Algorithm
2. [Key Management Interoperability Protocol Specification Version 1.1](http://docs.oasis-open.org/kmip/spec/v1.1/os/kmip-spec-v1.1-os.html "http://docs.oasis-open.org/kmip/spec/v1.1/os/kmip-spec-v1.1-os.html")
3. CMS NamedKeyEncryptedData type (with additional authentication added via MAC or signature)



###### Asymmetric Keys

Asymmetric keys are generated based on the mathematical problem they are based on e.g. prime generation. This gives a public and private key pair.

In general, the key pair is certified (the public key is signed) by a Certificate Authority to bind the key pair to some entity and convey that it is trustworthy.

##### Distribution

Key are distributed to their install locations.

For asymmetric keys, it may be either the private key ( Confidentiality-Integrity-Authenticity required) or the public key (Integrity-Authenticity) that is being distributed.

##### Usage

Keys are now live and should be used per the Recommendations section above. See “Data in Use” section.

##### Rotation

Working key (those they encrypt the actual payload) usage should be limited.

Rotation can be done automatically as part of the protocol (or done separately):

1.  For symmetric keys, in the Financial industry, [Derived Unique Key Per Transaction (DUKPT)](http://en.wikipedia.org/wiki/Derived_unique_key_per_transaction "http://en.wikipedia.org/wiki/Derived_unique_key_per_transaction") is a k[ey management](http://en.wikipedia.org/wiki/Key_management "http://en.wikipedia.org/wiki/Key_management") scheme in which a new key is derived for every transaction. However, there's a limitation of 1 million transactions per device, so a new key (IPEK) must be installed then.
2.  For Asymmetric keys, [Ephemeral](http://en.wikipedia.org/wiki/Ephemeral_key "http://en.wikipedia.org/wiki/Ephemeral_key")modes where the asymmetric keys are changed per use; e.g. for TLS TLS\_DHE and TLS\_ECDHE.

##### Backup and Recovery

The highest level keys in a system should be backed up to allow for recovery in a Business Continuity or Disaster Recovery event.

##### Revocation and Destruction

Symmetric Keys are generally used by 2 parties only – so the revocation is generally done by changing to a new random key.

A Public key Certificates could be used by many so each user needs to be informed of the revoked status. Public key Certificates can be revoked using Certification Revocation Lists or [Online Certificate Status Protocol](http://en.wikipedia.org/wiki/Online_Certificate_Status_Protocol "http://en.wikipedia.org/wiki/Online_Certificate_Status_Protocol") or can be permanently removed manually depending on the environment. This prevents another entity using this public key for encryption or authentication as the certificate is revoked.

##### Archive

Keys are no longer in active service but are retained for validation or until it is ensure the key is no longer needed.


## Using Cryptography to Solve Practical Problems


![DataStates](images/DataStates.png?raw=true)

Data can be in 3 states:

1.  [Data in Use](http://en.wikipedia.org/wiki/Data_in_Use "http://en.wikipedia.org/wiki/Data_in_Use") – data is being processed by the application
2.  Data in Transit – data travelling from one processing entity to another
3.  [Data at Rest](http://en.wikipedia.org/wiki/Data_at_Rest "http://en.wikipedia.org/wiki/Data_at_Rest") – data on storage media

### Securing Data in Use

Manipulation or processing of data requires that it exists in plaintext. ([Homomorphic Encryption](http://en.wikipedia.org/wiki/Homomorphic_encryption#Fully_homomorphic_encryption "http://en.wikipedia.org/wiki/Homomorphic_encryption#Fully_homomorphic_encryption") allows manipulation of data while it is encrypted, but is not sufficiently mature).

In general, it is good security practice isolate this plaintext data and the code that touches this plaintext data to a separate domain. This can be achieved at various layers:

1.  physically separate hardware e.g. HSM
2.  logically separate hardware – available in some CPUs
  1.  [ARM TrustZone](http://infocenter.arm.com/help/topic/com.arm.doc.prd29-genc-009492c/PRD29-GENC-009492C_trustzone_security_whitepaper.pdf "http://infocenter.arm.com/help/topic/com.arm.doc.prd29-genc-009492c/PRD29-GENC-009492C_trustzone_security_whitepaper.pdf") as used in embedded devices
  2.  [Intel Software Guard Extensions (SGX)](https://software.intel.com/en-us/blogs/2013/09/26/protecting-application-secrets-with-intel-sgx "https://software.intel.com/en-us/blogs/2013/09/26/protecting-application-secrets-with-intel-sgx")
  3.  AMD [file:///D:/owasp/Platform%20security%20processor Secure Execution Environment] (adds an ARM CPU to give ARM Trustzone)
1.  virtual machines running separate OSs
2.  separate process running on OS protected by MAC and/or DAC access control.

###### Example: TLS server with isolated private key in HSM

![TLS_HSM](images/TLS_HSM.png?raw=true)

For TLS, it is common for the TLS server private key to be on a HSM, while the working session symmetric keys are on the server (for TLS, the client authenticates the server by encrypting a value with the server public key certificate – that only the corresponding private key (on the server hsm) can decrypt. 

The Server TLS Private key is located in a HSM isolated from the server application or TLS protocol software. In this case the TLS private key only ever exists on the HSM – never on the server. If the server is compromised, then the attacker does not have direct access to the key (but may have the ability to exercise it to perform actions as the legitimate application would).

HSMs vendors generally supply interfaces to common cryptographic libaries e.g. openssl, so that applications can, with minimal change/effort, call the same cryptograpic library in the same way they would if the keys were local. E.g. for openssl, an application would use the [openssl engine](https://www.openssl.org/docs/crypto/engine.html "https://www.openssl.org/docs/crypto/engine.html") or may already support a [PKCS \#11](http://en.wikipedia.org/wiki/PKCS_11 "http://en.wikipedia.org/wiki/PKCS_11") interface.




### Securing Data at Rest

#### Introduction

When it comes to stored data-at-rest so that it is encrypted in an SQL database, there are three commonly practiced approaches:

-   The SQL database engine itself handles the encryption and decryption. Examples of this are Oracle Database "Transparent Data Encryption" and Microsoft SQL Server "Transparent Data Encryption" . (We will refer to these as Oracle TDE and SQL Server TDE respectively, and just refer to the technology as TDE in general.)
-   The application code completely handles the encryption and decryption of the sensitive data before it is stored in and after it is retrieved from said database, as well as ensuring its authenticity.
-   An appropriate proxy (for example, MIT's CryptDB or a custom web service that clients start using to access the data rather than accessing it directly) between the application and the database handles all the encryption / decryption.

Each of these approaches have their own advantages and disadvantages of securing data-at-rest stored in a database. Exploring all of these pros and cons is beyond the current scope of this wiki page, although this may be provided in the future should the need warrant. The present purpose of this document is to provide some background for understanding why the pros and cons of each approach and to understand the threat models that each of these approaches address.

#### General Approaches

##### Database Engine Transparent Data Encryption (TDE)

###### How It Works (General Description)

In this technology, the DB engine itself (e.g., Oracle Database, Microsoft SQL Server Database) handle the encryption and decryption and usually can be configured to handle the key management issues as well.

TDE usually offers encryption at the column, table, and tablespace levels. TDE only supports limited encryption algorithms (most typically, AES and 3DES) and assorted key lengths. There usually are (at least) 2 keys involved. One, is the DB "master" key. This master key is usually secured with a pass phrase / password which ideally is controlled by an application team who is considered the data custodian for the to-be-encrypted data. This master key is then used to derive other specific DB key encryption keys that encrypt specific columns, tables, or tablespaces.

Most often, the DB engine uses the CBC cipher mode and something like PKCS7 padding (which Java refers to as PKCS5Padding) to handle the encryption. Also, with TDE, there are usually two modes of operation...deterministic encryption and non-deterministic encryption. This translates into whether or not each individual item being encrypted (generally, a record, when encrypting a column) uses unique Initialization Vector (IV) [sometimes referred to as 'salt' by the DB vendors] or not. Deterministic encryption uses the same IV for all records; non-deterministic encryption uses a unique IV for each record that is encryption and this IV is maintained in a manner that is transparent to the DB access. Deterministic and non-deterministic encryption will be discussed later in more detail in the Advantages and Disadvantages subsection to follow.

Key management normally consists of distributing a file containing the password-encrypted DB master key along with making the password or passphrase known to whomever needs to decrypt this master key in order to provide it to the database engine. If this master key file and password are placed within the database itself (which is the easiest to implement), then the database engine will automatically decrypt its encrypted data. However, this scenario does not protect the sensitive encrypted data from a rogue DBA or system administrator (see the "General Threat Model" subsection, below), so frequently it is recommended that the application team or some other independent data custodian becomes responsible for managing this password-encrypted master key. (Note: Some TDE implementations use a separate private key contained in a keystore file to decrypt the master secret key, but the ideas as the same. In such cases, this private key ideally should be password protected when stored in the keystore file.) Further discussion of key management for SQL Encryption purposes is beyond the scope of this document.

###### General Threat Model

Like encryption used for any purpose--be it authentication, confidentiality, data integrity, etc.--one needs to ask "what is your threat model?". In other words, what particular threat agents are you trying to prevent which particular assets via what particular attack vectors? For the case of TDE, the vendors generally do not explicitly document a threat model. Instead, they vaguely hand wave and point to something like section 3.4 of the PCI Data Security Standard and state "we satisfy those requirements". However, when one looks closely at these PCI DSS requirements as well as the vendor-specific TDE behavior, it usually becomes clear that the general threat model these vendors have in mind is someone like a rogue DBA or other rogue operations person doing a "smash and grab" of a hard drive where the encrypted database resides or attempting to steal confidential encrypted data from some offline backup of the database.

From the perspective of a security engineer, that is a very narrow threat model is it does nothing to reduce attacks to an online encrypted database (which presumably is the usual, or at least preferred, state of one's DB). And indeed, this particular niche attack vector can only be effectively mitigated if one does proper key management as alluded to above. If the file (or as Oracle prefers to call it, the "wallet") containing the password-encrypted DB master key is made available to the DBA, this mitigation is no longer available. (In terms of Oracle TDE, we would restate this if is arranged that the Oracle wallet is auto-opened when the database comes up, then the encryption that Oracle TDE provides you does not even sufficiently protect you against this particular niche attack vector.)

###### Advantages

Given that the threat model for DB Engine TDE is so narrow, why use a TDE solution at all? Indeed, that is the $64,000 question.

In a nutshell, it's because the solution is cheap. It is almost 100% transparent (at least when using deterministic encryption) to the applications accessing the encrypted data stored in the database and because of that, it is a very inexpensive solution to deploy. When one adds to that the fact that it can satisfy the letter of the law of regulatory policies (such as section 3.4.x of PCI DSSv2), often that's all that it takes. Such companies often take a security-by-checklist approach because they are more concerned with fines failing to meet regulatory compliance issues than they are in reduce losses from potential security breaches.

At other times, while it is recommended as a very poor solution, it may be the only feasible solution, especially for legacy databases. For example, if your company has 20 or so applications accessing some database where very sensitive data such as (say) full-credit card numbers are stored and those applications are a combination of third-party applications, Cobol applications, C/C++ applications, Java applications, and .NET applications, it is often very difficult or prohibitively expensive to design a common, secure solution that will work for all 20+ applications. (The "Encryption By Proxy" approach can approach this, but it has some significant performance issues and still is not ready for production-deployment.) And when faced with impending large fines from PCI or other regulatory bodies for not being in compliance for securing data-at-rest, the TDE approach starts looking like the ideal candidate to those in upper management.

###### Disadvantages

The disadvantages of the DB Engine TDE approach are great. The major ones are:

-   Because the DB engine itself decrypts all the data transparently to clients, once the DB is provided the decrypted master key, any client having query access to the encrypted columns will have access to the decrypted data. If this is not the desired state, in order to keep the data secure, the database access model often needs to be significantly revamped to construct separate DB views for each different use case actor with legitimate access to at least portions of the database.
-   Deterministic encryption is usually the preferred solution by both database administrators and application developers, but unfortunately it has numerous short-comings. With deterministic encryption, the same plaintext will always encrypt to the same ciphertext (at least until a key change operation is done to generate new DB key encryption keys). However, for the same reasons that we do generally require unique IVs (even for CBC mode; in any other mode, it is a major disaster in the making), deterministic encryption is not considered secure. The details of these cryptographic attacks are beyond the scope of this document. However, using non-deterministic encryption with a unique IV (or "salt") per record results in stronger encryption but does not allow the DB engine to do indexed searching on that specific column. For cases where the sensitive plaintext data is something where all possible plaintext values are easily enumerated (for example, with Social Security Numbers), this allows someone who would have access to the ciphertext stored in the database who also has insert or update access to create records with all possibilities. Those ciphertext values can then be compared to the other identical ciphertext values in the database and that can be used to determine the plaintext by the attacker simply keeping a mapping of plaintext to ciphertext. This is an attack that could be done by a rogue DBA even though that DBA does not know the DB TDE encryption key. Had non-deterministic encryption been chosen instead, such a simple enumeration attack would not be possible.
-   When backup copies of an open / online database are made, certain types of these backups make copies of the decrypted data so that anyone having access to the backup copies has access to the sensitive plaintext data that had been encrypted. Examples for Oracle include backups made via the "Data Pump export utility (expdp)" or "explicit captures" made via Oracle streams. (See the section "Using Data Pump with TDE" for the former and "How Oracle Streams Works with Other Database Components" for details of the latter.) Similar issues are expected with Microsoft SQL Server backups but have not been verified. Therefore, this may require changes to the database backup procedures.
-   Because the sensitive data sent to the database is plaintext, passive network sniffing attacks are a major concern. Consequently, the database connection should be established over TLS, IPSec, or some other secure communication channel.

##### Application Level Encryption

###### How It Works (General Description)

Application level encryption refers to encryption that is considered part of the application itself; it implies nothing about where in the application code the encryption is actually done. In a typical 3-tier web application, the encryption most often is done in the application server before being sent to the database. Thus--in this design--the database is only sent ciphertext, not the sensitive plaintext (compare that to the TDE case, above).

An alternate approach is to do all the encryption / decryption as stored SQL procedures, possibly invoked via DB triggers. This design is very similar to the DB TDE approach discussed above with the biggest difference is that it as all the disadvantages and none of the advantages (such as minimal development costs). Because of this, for the rest of this section we assume encryption / decryption is handled in the application server and not done within the DB via stored procedures.

###### General Threat Model

It goes without saying (but we will say it otherwise), that for this approach the application developers are trusted in some sense. While they may not (and indeed, should not) be trusted with the encryption keys, the must be trusted to produce secure code to handle the encryption. (Contrast this to the implied threat model for TDE where the DB vendor is trusted to produce secure code and DBAs are considered trusted. While application developers also trusted not to leak sensitive information--either intentionally or unintentionally--they do not have to be trusted with writing the encryption code in the case of TDE.)

###### Advantages

-   Like the TDE approach, a smash and grab of an offline copy of the database will contain only ciphertext. Unlike the TDE approach, the same is true of a direct DB dump of an online database. Given that the ideal state of one's production database is that it is online, this is an important distinction.
-   An advantage of handling the encryption outside of the database is that--if done correctly--one need not be overly concerned about the contents of the database being stolen. In the face of SQL injections where an external attacker can sometimes dump database table contents remotely, this can be an important advantage. Compare this to the TDE solution, where the database would transparently decrypt the data when a SQL injection occurs. This does not mean that this is approach is completely immune to data leakage via SQL injection attacks, but it does lower the likelihood.
-   Because the application controls the entire encryption / decryption process, one can also provide for data integrity across the entire record. This can be used to prev

###### Disadvantages

-   In terms of initial layout and ongoing software support costs, this is likely to be the most costly of the three solutions.
-   The application developers need to understand cryptography w
-   ell enough to develop secure cryptographic solutions. Given that this is a relatively rare skill for application developers, its importance should not be overlooked.
-   In addition to the actual encryption / decryption solution, the application must also handle the ancillary functions of secure key management which is anything but trivial. This includes, but is not limited to key distribution and key change operations.

##### Encryption By Proxy

TODO

###### How It Works (General Description)

TODO

###### General Threat Model

TODO

###### Advantages

TODO

###### Disadvantages

TODO - These sections to be covered later, should the need arise.

#### Encrypting Sensitive Data with An Asymmetric Cipher

With all asymmetric primitives, [Chosen Plaintext Attacks](http://en.wikipedia.org/wiki/Chosen-plaintext_attack "http://en.wikipedia.org/wiki/Chosen-plaintext_attack") are always a concern (see also [CPA](http://cs.wellesley.edu/~cs310/lectures/CPA_slides_handouts.pdf "http://cs.wellesley.edu/~cs310/lectures/CPA_slides_handouts.pdf")). Because the public key is always considered as known to potential adversaries, attackers can always encrypt any arbitrary plaintext and observe the resulting ciphertext. Ordinarily, this is not a cause for concern because the plaintext that is to be encrypted with an asymmetric cipher is highly unpredictable (e.g., encrypting session keys or cryptographic hash values). However, chosen plaintext attacks become an issue when using public-key crypto to encrypt highly structured / regular plaintext, especially when that plaintext has a limited length to make encrypting of all possible plaintexts practical.

Consider the scenario where an application is using RSA encryption to encrypt plaintext social security numbers or bank account numbers and then storing the resulting ciphertext into the application's database. An inside attacker who has access to the database (but not the RSA private key) could use the RSA public key (which we assume is available) and use it to encrypt all possible SSNs, keeping a map of SSN to ciphertext. The attacker could then try to use the resulting ciphertexts to determine which plaintext SSN corresponds to which DB record by searching by the ciphertext SSN in the database.

RSA OEAP scheme could be used as it adds randomization to the output.

A hybrid encryption scheme e.g. RSA KEM would address this issue as it adds randomization to the output.

Per the recommendations, asymmetric primitives like RSA should not be used directly because it would result in the same ciphertext each time the SSN is encrypted.

Per the recommendations, RSAES PKCS v1.5 scheme should not be used. RSAES PKCS v1.5 has different padding options: “For block type 00, the octets shall have value 00; for block type 01, they shall have value FF; and for block type 02, they shall be pseudorandomly generated and nonzero”

    

##### Worked example


Encrypting data with RSA PKCS#1 v1.5 and PKCS#1 OAEP padding
    
    $ openssl genrsa -out privkey.pem 2048 #generate an RSA 2048 key pair
    Generating RSA private key, 2048 bit long modulus
    
    .......................+++
    
    .+++
    
    e is 65537 (0x10001)
    
    $ echo -n 1234567890 > SSN.txt #SSN.txt file contains 1234567890
    
    $ openssl rsautl -pkcs -encrypt -in SSN.txt -inkey privkey.pem -out ENCpkcs_SSN.bin #uses type 2 padding. Results in different output ciphertext each time it is called because type 2 random padding.
    
    $ openssl rsautl -oaep -encrypt -in SSN.txt -inkey privkey.pem -out ENCoaep_SSN.bin #Results in different output ciphertext each time it is called because of the OAEP randomisation 




##### Cryptographic Message Syntax

[Cryptographic Message Syntax](http://en.wikipedia.org/wiki/Cryptographic_Message_Syntax "http://en.wikipedia.org/wiki/Cryptographic_Message_Syntax") defines a syntax to digitally sign, digest, authenticate, or encrypt arbitrary message content.

1.  SignedData: data is signed by sender private key(s)
2.  EnvelopedData: data is encrypted with a symmetic key which is in turn encrypted with recipient(s) public key(s).
3.  AuthenticatedData: Data is MAC'd or HMAC'd and authentication keys are encrypted with recipient(s) public key(s)
4.  DigestedData: data is hashed
5.  EncryptedData: data is encrypted but keys are managed out of band
6.  NamedKeyEncryptedData: Data is encrypted along with an identifier of the encryption algorithm used and the type of content encrypted. This is used by the application to identify the data properties e.g. the data could be a key used for PIN encryption.

Through these data types, CMS supports data confidentiality, data integrity, data origin authentication, and non-repudiation services

[CMS](http://tools.ietf.org/html/rfc5652 "http://tools.ietf.org/html/rfc5652") is extensible in design; it supports several cryptographic schemes e.g.:

1.  [Use of the RSAES-OAEP Key Transport Algorithm in the Cryptographic Message Syntax (CMS)](http://tools.ietf.org/html/rfc3560 "http://tools.ietf.org/html/rfc3560")
2.  [Use of the RSA-KEM Key Transport Algorithm in the Cryptographic Message Syntax (CMS)](http://tools.ietf.org/html/5990 "http://tools.ietf.org/html/5990")
3.  [Using the Boneh-Franklin and Boneh-Boyen Identity-Based Encryption Algorithms with the Cryptographic Message Syntax (CMS)](https://tools.ietf.org/html/rfc5409 "https://tools.ietf.org/html/rfc5409")

This allows the application to support newer cryptographic schemes as they are approved over time – with minimal change in the application.

[CMS](http://en.wikipedia.org/wiki/Cryptographic_Message_Syntax "http://en.wikipedia.org/wiki/Cryptographic_Message_Syntax") is based on the syntax of [PKCS 7](https://tools.ietf.org/html/rfc2315 "https://tools.ietf.org/html/rfc2315")[](https://tools.ietf.org/html/rfc2315 "https://tools.ietf.org/html/rfc2315").
It was originally defined and used for [S/MIME](http://en.wikipedia.org/wiki/S/MIME "http://en.wikipedia.org/wiki/S/MIME") email but it can be used for any application that needs to use or share cryptographically protected data.

CMS is supported in most crypographic libraries e.g. [openssl](https://www.openssl.org/docs/apps/cms.html "https://www.openssl.org/docs/apps/cms.html").

###### Signature Stripping Attack

![SigEnvData](images/SigEnvData.png?raw=true)

It is possible to combine CMS data types as follows:

1.  Encrypt data with recipient's public key to get EnvelopedData type (Confidentiality)
2.  Sign the EnvelopedData type, with the sender's private key (Integrity, Authenticity)



However, a malicious sender that the recipient trusts can remove the signature i.e. remove the SignedData type from the message and replace it with their own signature (SignedData). The recipient would think the encrypted message was created by the malicious sender.

One simple solution is for the signer to include some value that identifies them that the recipient can validate (e.g. their public key certificate distinguished name) with the data that is to be encrypted in EnvelopedData type.

Then when the recipient receives the data they can check who signed the data (based on data in SignedData) and compare it to the value in the EnvelopedData type.

Other data types can be combined e.g. a sign-then-encrypt message can be formed by first creating a SignedData message, then encrypting that result in a CMS NamedKeyEncryptedData message

##### Disk Encryption

[Disk encryption](http://en.wikipedia.org/wiki/Disk_encryption_theory "http://en.wikipedia.org/wiki/Disk_encryption_theory") is a special case of [data at rest](http://en.wikipedia.org/wiki/Data_at_Rest "http://en.wikipedia.org/wiki/Data_at_Rest") e.g. Encrypted File System on a Hard Disk Drive.

XTS-AES as previously discussed is commonly used in disk encryption applications.


### Securing Data in Transit

#### Prudent Engineering Practice for Cryptographic Protocols

[Abadi and](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.225.1311 "http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.225.1311")[Needham](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.225.1311 "http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.225.1311")[defined guiding principles for protocol designers](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.225.1311 "http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.225.1311")based on their analysis of common errors in published protocols:

1. Explicit communication: Every message should say it means: the interpretation of the message should depend only on its content. It should be possible to write down a straightforward English sentence describing the content—though if there is suitable formalism available. 
2. Appropriate Action: The conditions for a message to be acted upon should be clearly set out so that someone reviewing a design may see whether they are acceptable or not. 
3. Naming: If the identity of a principal is essential to the meaning of a message, it is prudent to mention the principal’s name explicitly in the message. 
4. Encryption: Be clear about why encryption is being done. Encryption is not wholly cheap, and not asking precisely why it is being done can lead to redundancy. Encryption is not synonymous with security, and its improper use can lead to errors. 
5. Signing encrypted data: When a principal signs material that has already been encrypted, it should not be inferred that the principal know the content of the message. On the other hand, it is proper to infer that the principal that signs a message and then encrypts it for privacy knows the content of the message. 
6. Timeliness: Be clear what properties you are assuming about nonces. What may do for ensuring temporal succession may not do for ensuring association—and perhaps association is best established by other means. 
7. Timeliness: The use of a predictable quantity (such as the value of counter) can serve in guaranteeing newness, though a challenge-response exchange. But if a predictable quantity is to be effective, it should be protected so that an intruder cannot simulate a challenge and later replay a response. 
8. Timeliness: If timestamps are used as freshness guarantees by reference to absolute time, then the difference between local clocks at various machines must be much less than the allowable age of a message deemed to be valid. Furthermore, the time maintenance mechanism everywhere becomes part of the trusted computing base. 
9. A key may have been used recently, for example to encrypt a nonce, yet be quite old, and possibly compromised. Recent use does not make the key look any better than it would otherwise. 
9. Recognizing messages and encodings: If an encoding is used to present the meaning of a message, then it should be possible to tell which encoding is being used. In the common case where the encoding is protocol dependent, it should be possible to deduce that the message belongs to this protocol, and in fact to a particular run of the protocol, and to know its number in the protocol. 
10. Trust: The protocol designer should know which trust relations his protocol depends on, and why the dependence is necessary. The reasons for particular trust relations being acceptable should be explicit though they will be founded on judgement and policy rather than on logic.

#### Protocol Attacks

Attacks on cryptographic protocols can be classified as follows:



##### Example Protocol Interaction attack

The original [Needham–Schroeder](http://en.wikipedia.org/wiki/Needham–Schroeder_protocol#Fixing_the_man-in-the-middle_attack "http://en.wikipedia.org/wiki/Needham–Schroeder_protocol#Fixing_the_man-in-the-middle_attack") protocol had a man-In-the-middle vulnerability where a Protocol Interaction attack allows an attacker to impersonate another party.

This was fixed by by adding the name of the sender to the message for the recipient to verify per principle 3 “the identity of a principal is essential to the meaning of a message, it is prudent to mention the principal’s name explicitly in the message.”

##### Example Replay attack

The original [Needham–Schroeder](http://en.wikipedia.org/wiki/Needham–Schroeder_protocol#An_attack_on_the_protocol "http://en.wikipedia.org/wiki/Needham–Schroeder_protocol#An_attack_on_the_protocol") protocol has a vulnerability where a Replay attack allowed an attacker old an protocol message to authenticate themselves. This was fixed by adding a timestamp i..e. applying the Timeliness principles.

#### TLS

Refer to [OWASP Transport Layer Protection Cheat Sheet](https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet "https://www.owasp.org/index.php/Transport_Layer_Protection_Cheat_Sheet") which references NIST [Guidelines for the Selection, Configuration, and Use of Transport Layer Security (TLS) Implementations](http://csrc.nist.gov/publications/PubsSPs.html#800-52 "http://csrc.nist.gov/publications/PubsSPs.html#800-52")

TLS provides Entity Authentication, Data Integrity, Data origin authentication, Data freshness, Data Confidentiality. It does not provide Non-repudiation because symmetric keys are used for message exchange and both sender and reciever have the symmetric key (so one party can deny they sent a message – blaming the other party).

TLS prevents replay attacks by using a monotonically increasing sequence number that is MAC'd and there's a separate sequence number for messages to and from the server.

TLS1.2

1.  uses SHA-256 or higher
2.  uses AES-128 or higher

Taking OpenSSL as an example, the following are equivalent (give the same cipher-suites):

1.  openssl ciphers -v 'ALL:-SHA:-MD5:-RC2:-aNULL:-eNULL*\#everything except those that use SHA1, MD5, RC2*
2.  openssl ciphers -v 'ALL:-SSLv3:-SSLv2:-aNULL:-eNULL' \#TLS v1.2 only

[TLS 1.3 (draft)](http://en.wikipedia.org/wiki/Transport_Layer_Security#TLS_1.3_.28draft.29 "http://en.wikipedia.org/wiki/Transport_Layer_Security#TLS_1.3_.28draft.29") mandates only Authenticated Encryption ciphers are used (AEAD)

#### IPSEC

[IPSEC](http://en.wikipedia.org/wiki/IPsec "http://en.wikipedia.org/wiki/IPsec") defines protocols at the IP layer (i.e. network layer, whereas TLS operates at the application layer)

1.  Authenticaton Header (AH)
2.  Encapsulating Security Payload (ESP)
3.  Security Assocations (SA) that provides the parameters for AH and ESP operations; Internet Key Exchange (IKE and IKEv2) is one of the protocols that can be used to provide the keying material.

Authentication Header provides integrity and authentication of IP packets based on a HMAC. Encapsulating Security Payload (ESP) provides confidentiality of message data and (traffic flow to a limited degree). It can also optionally provide AH services.

IPSEC provides Data Integrity, Data origin authentication, Data Confidentiality, Limited Data Flow Confidentiality, Replay prevention, Non-repudiation.

### Cryptography for Authentication

We use cryptography for authentication in two different ways. First, cryptographic protocols are used to securely authenticate entities over an insecure communication channel. Some of these more widely known communication protocols include Kerberos, RADIUS, and MS-CHAPv2. If, as a developer, you have need of authentication protocol, you are advised to either use a standard one known to be secure or work with a reputable professional cryptographer to develop one to suit your needs. History is replete with examples from broken authentication protocols even when they are developed by experts. A prime example is the original Needham-Schroeder protocol. Hire a professional cryptographer as this use of cryptography is much harder than it seems.

The second way that cryptography is used for authentication is for storing a user's password. Unless the user's password must be later be replayed in a separate context to make the plaintext password available to some other downstream system (possibly when the user is no longer even authenticated to the present system), the recommended way to do this is to use a strong, one-way secure cryptographic hash along with "salting" (adding a nonce of sufficient length).

Non-repudiation is useful for financial, e-commerce, and contractual exchanges. Non-repudiation is accomplished by having the sender and/or recipient to digitally sign some unique transactional record.



## References


-   Alfred Menezes, Paul van Oorschot, Scott Vanstone, *Handbook of Applied Cryptography*, 1997, CRC Press, [ISBN 0-8493-8523-7](http://www.amazon.com/exec/obidos/ASIN/0849385237 "http://www.amazon.com/exec/obidos/ASIN/0849385237"). (Online: [[http://ca](http://ca "http://ca")
-   cr.uwaterloo.ca/hac/]([[2]](http://cacr.uwaterloo.ca/hac/)))
-   Neils Ferguson, Bruce Schneier, Tadayoshi Kohno, *Cryptography Engineering: Design Principles and Practical Applications*, Wiley Publishing, [ISBN 978-0-470-47424-2](http://www.amazon.com/exec/obidos/ASIN/9780470474242 "http://www.amazon.com/exec/obidos/ASIN/9780470474242").
-   NIST Special Publications 800-57, Recommendation for Key Management – NIST Recommendations for Key Management [SP 800-57](http://csrc.nist.gov/publications/PubsSPs.html#800-57pt1 "http://csrc.nist.gov/publications/PubsSPs.html#800-57pt1")[Part 1](http://csrc.nist.gov/publications/PubsSPs.html#800-57pt1 "http://csrc.nist.gov/publications/PubsSPs.html#800-57pt1") to [SP 800-57](http://csrc.nist.gov/publications/PubsSPs.html#800-57pt3 "http://csrc.nist.gov/publications/PubsSPs.html#800-57pt3")[Part 3](http://csrc.nist.gov/publications/PubsSPs.html#800-57pt3 "http://csrc.nist.gov/publications/PubsSPs.html#800-57pt3") 
ENISA (editor: Nigel P. Smart), Algorithms, Key Sizes, and Parameters Report: 2013 Recommendations, (Online: [[3]](http://www.enisa.europa.eu/activities/identity-and-trust/library/deliverables/algorithms-key-sizes-and-parameters-report))
-   Neils Ferguson, Bruce Schneier, Tadayoshi Kohno, *Cryptography Engineering: Design Principles and Practical Applications*, 2010, Wiley Publishing Inc, [ISBN 978-0](http://www.amazon.com/exec/obidos/ASIN/9780 "http://www.amazon.com/exec/obidos/ASIN/9780")=470-47424-2.
-   [http://www.cryptopp.com/wiki/Authenticated_Encryption](http://www.cryptopp.com/wiki/Authenticated_Encryption)
-   [https://cryptocoding.net/index.php/Coding_rules](https://cryptocoding.net/index.php/Coding_rules)

## Reviewers


Candidates:

-   Tor Erling Bjørstad [tor@mnemonic.no](mailto:tor@mnemonic.no "mailto:tor@mnemonic.no") (offered via [cryptography@randombits.net](mailto:cryptography@randombits.net "mailto:cryptography@randombits.net") mailing list)
-   Jeff Walton – probable; need to ask
-   Michael Howard? (ask; previous author)
-   Chris Tidball (volunteered)
-   Kevin Kenan? (ask)
-   Anthony J. Stiebler? (Wells Fargo, ask)

## Endnotes

[2] In Java, if you use DESede and do not specify a key size, you will end up with 2-key triple DES rather than 3-key triple DES. Note also to use 3-key triple DES in Java, you must have the Java JCE Unlimited Strength Jurisdiction Policy Files installed; otherwise, you will get an exception when you try to generate or use a 168-bit (i.e., 3-key) encryption key.

[5] In fact, according to Cryptix co-author, David Hopwood (see [[6]](http://www.users.zetnet.co.uk/hopwood/crypto/scan/ca.html)) suggests that other cipher modes may not even make sense for asymmetric ciphers. Hopwood states:

Where an asymmetric cipher requires an encoding method in order to be specified completely, the naming convention is "encryption-primitive/encryption-encoding". Some existing JCE providers will accept the use of a block cipher mode and padding with an asymmetric cipher (e.g. "RSA/CBC/PKCS\#7"); this is not recommended, and new providers MUST reject this usage. An encryption primitive name on its own (e.g. "RSA", as opposed to a complete encryption scheme such as "DLIES-ISO(...)") SHOULD also be rejected.
