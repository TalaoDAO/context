# ABF SSI profile v 0.0.2
Date 18/04/2023

Status : Draft

This document is not a specification, but a profile. It outlines existing specifications required for implementations to interoperate among each other. It also clarifies mandatory to implement features for the optionalities mentioned in the referenced specifications.



## Editors and contributors
* Thierry Thevenet (Talao)
* ?
* ?
* ?
        
## Table of Contents

- [Use cases](#use-cases)
* IOT
* Legal entities
* Web3(#web3-use-case)
- [Open Standard Requirements](#open-standards-requirements)
- [Decentralized Identifiers](#decentralized-identifiers-did)
- [Verifiable Credentials](#verifiable-credentials)
- [Protocols](#protocols)
- [Wallet](#wallet)
- [Verifiable Data Registries](#verifiable-data-registries)



## Use cases

### legal entity use case(company consent, etc)
* To be done 
### IOT use case 
* To be done
### Web3 use case
A user of an ABF member goes to a service that offers the issuance of a loyalty card in the form of an NFT on the condition that this user is of French nationality and over 18 years old. The user presents the identity certificates he holds in his wallet which meet this requirement. Once identity checks are complete, the user will confirm that they are in control of a crypto account, then the company will issue a non-transferable, non-fungible token (NFT) to the user's crypto account. The NFT does not contain any user identity data; instead, the NFT symbolizes that the user has gone through the company's identity verification process and has a loyalty card. The user can then prove that he holds a loyalty card for all on-chain services of the issuing company and partners.

## Open Standards Requirements

VCs MUST adhere to the [VC Data Model v1.1](https://www.w3.org/TR/vc-data-model/) and be encoded as JSON and signed as JWT as defined in 6.3.1 of VC Data Model v1.1. VCs encoded as JSON-LD and signed using Linked Data Proofs are NOT supported.
    
For key management and authentication, Self-Issued OpenID Connect Provider v2, an extension to OpenID Connect, MUST be used as defined in [SIOPv2 ID1](https://openid.net/specs/openid-connect-self-issued-v2-1_0.html).

For transportation of VCs, First Implementer’s Draft of OpenID for Verifiable Presentations MUST be used as defined in [OpenID4VP](https://openid.net/specs/openid-4-verifiable-presentations-1_0.html).

As the query language, (Presentation Exchange v1.0.0)[https://identity.foundation/presentation-exchange/spec/v1.0.0/] MUST be used and conform to the syntax defined in OpenID4VP ID1.

Decentralized Identifiers (DIDs), as defined in [DID Core](https://identity.foundation/jwt-vc-presentation-profile/#term:did-core), MUST be used as identifiers of the entities.

DID Documents MUST use [JsonWebKey2020](https://www.w3.org/community/reports/credentials/CG-FINAL-lds-jws2020-20220721/#json-web-key-2020) as the type for Verification Material intended for use in the profile. (DID Core section 5.2.1)

Verification Material intended for use in the profile MUST use [publicKeyJwk](https://www.w3.org/TR/did-core/#dfn-publickeyjwk) (DID Core section 5.2.1). 

To bind an owner of a DID to a controller of a certain origin, a Well Known DID Configuration MUST be used as defined in [Well Known DID](https://identity.foundation/.well-known/resources/did-configuration/).

For Revocation of VCs, Status List 2021 as defined in [Status List 2021](https://w3c.github.io/vc-status-list-2021/) MUST be discovered using either DID Relative URLs stored in an Identity Hub as defined in Identity Hub (0.0.1 Predraft) or discovered using an HTTPS URL.


## Decentralized identifiers (DID)

### Natural person

Decentralized Identifiers (DIDs), as defined in [DID Core](https://identity.foundation/jwt-vc-presentation-profile/#term:did-core) , MUST be used as identifiers of natural person entities. Implementations MUST support 'did:key', and 'did:ebsi'  as mandatory DID methods.

#### `did:key`for natural persons

The `did:key` method is used to express public keys in a way that doesn't
require a DID Registry of any kind. Its general format is:

```
did:key:<multibase encoded, multicodec identified, public key>
```

So, for example, the following DID would be derived from a base-58 encoded
ed25519 public key:

```
did:key:z6MkpTHR8VNsBxYAAWHut2Geadd9jSwuBV8xRoAnwWsdvktH
```
A complete description of this method is available  [here](https://w3c-ccg.github.io/did-method-key/)

#### `did:key`for EBSI natural person

The 'did:key' method used by EBSI is based on a specific [multicodec](https://github.com/multiformats/multicodec/blob/master/table.csv#L514). A complete description of this method is available [here](https://api-pilot.ebsi.eu/docs/libraries/ebsi-did-resolver). 

### Legal entities
Decentralized Identifiers (DIDs), as defined in [DID Core](https://identity.foundation/jwt-vc-presentation-profile/#term:did-core) , MUST be used as identifiers of legal entities. Implementations MUST support 'did:ebsi', 'did:ala' and 'did:web'  as mandatory DID methods as defined in [did-web](https://w3c-ccg.github.io/did-method-web/),  [did-ala](https://github.com/alastria/alastria-identity/wiki/Alastria-DID-Method-Specification) and [did:ebsi]().

Expliquer comment resoudre ces DIDs

### keys
Supporeted digital signature :

ECDSA	
* P-256 ES256 	Required
* P-384 ES384	Optional
* P-521 ES512     Optional
* secp256k1 ES256K        Optional

EdDSA
* Ed25519d OKP     Optional

RSA	
* PKCS1-v1_5 RS256        Optional.

For interoperability, the implementation of the P-256 curve is required.

x509 certificate use ?



## Verifiable Credentials 



* Format serialization : JWT
* Atomic credentials or data minimization
* Localization UK
* holder binding ? 


## Protocols
 
 ### to present verifiable credentials (and user authentication)  
   * SIOPv2


### to exchange verifiable credentials/presentations 
   * OIDC4VP


### to issue credentials
   * OIDC4VCI




## Wallet 
* key management -> import/export
* data(VC) management -> import/export 
* No mobile wallet onboarding  
* user binding requirement -> authentication mode to be defined




## Verifiable data registries
* revocation VC  or issuer server ?
* trusted issuer/verifier registry (company details)
* accreditation  for registry updates -> gouvernance + paper 




## Process  
* legal entity onboarding -> verification status () 
* user onboarding -> “ABF” VC ??
* conformance -> wallet, issuer, verifier


## APIs
* for registries 
* vc attribute data on local ipfs node 
* timestamping -> yes
* ledger  implementation on ethereum 


## Implementations
* list of available libs
   * https://github.com/decentralized-identity
   * ?


 
## Privacy considerations
* minimization of schema/data model
* anonymization of VCs -> correlation, etc 





## References :


Profile examples  : 
         https://identity.foundation/jwt-vc-presentation-profile/
        https://api-pilot.ebsi.eu/docs
        https://github.com/alastria/alastria-identity 


EU ARF : https://github.com/eu-digital-identity-wallet 
W3C DID core : https://www.w3.org/TR/did-core/
W3C VC/VP : https://www.w3.org/TR/vc-data-model/
Presentation Exchange  https://identity.foundation/presentation-exchange/ 
Credential Manifest :
DID registries 
RFC JOSE https://www.rfc-editor.org/rfc/rfc7515 
RFC algo https://www.rfc-editor.org/rfc/rfc7518  
RFC JWK
Protocoles :  
https://openid.net/specs/openid-connect-4-verifiable-presentations-1_0-07.html,
https://openid.net/specs/openid-connect-self-issued-v2-1_0.html,
https://openid.net/specs/openid-4-verifiable-credential-issuance-1_0.html
