# ABF SSI profile v 0.0.1
Date 18/04/2023

Status : Draft

This document is not a specification, but a profile. It outlines existing specifications required for implementations to interoperate among each other. It also clarifies mandatory to implement features for the optionalities mentioned in the referenced specifications.



## Editors and contributors
* Thierry Thevenet (Talao)
* ?
* ?
* ?
        

## Use cases

### legal entity use case(company consent, etc)
* To be done 
### IOT use case 
, To be done
### Web3 use case
A user of an ABF member goes to a service that offers the issuance of a loyalty card in the form of an NFT on the condition that this user is of French nationality and over 18 years old. The user presents the identity certificates he holds in his wallet which meet this requirement. Once identity checks are complete, the user will confirm that they are in control of a crypto account, then the company will issue a non-transferable, non-fungible token (NFT or SBT?) to the user's crypto account. The NFT does not contain any user identity data; instead, the NFT symbolizes that the user has gone through the company's identity verification process and has a loyalty card. The user can then prove that he holds a loyalty card for all on-chain services of the issuing company and partners.


## Decentralized identifiers (DID)

### `did:key`for aatural persons

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

   * did:key:public_key,
   * new did:ebsi -> did:key:(jwk)
   * anonymization & multi DID
   * 

### Legal entities
   * did:ebsi, did:ala
   * did:web as a starter solution ?
   * ??? public key -> eidas certificates (x509 certificate CA)


## keys
- NIST keys (rsa, p-256, etc)
- “Modern” EC  curves (secp256k1, ed25519 )


- services …




## Verifiable credentials/VP 
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
