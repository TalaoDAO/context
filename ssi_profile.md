ABF ssi profile v 0.0.1
Date 5/04/2023
# Draft


This document is not a specification, but a profile. It outlines existing specifications required for implementations to interoperate among each other. It also clarifies mandatory to implement features for the optionalities mentioned in the referenced specifications.




Profile examples  : 
         https://identity.foundation/jwt-vc-presentation-profile/
        https://api-pilot.ebsi.eu/docs




Editors / contributors
* Thierry Thevenet (Talao)
* ?
* ?
* ?
        


Specific SSI use cases / scope
* interop 
* Legal entity  vs natural person
* No need to list all standard use cases but  
* IOT ?
* web3 integration ?
* others ?




Decentralized identifiers (DID)
* for natural persons
   * did:key, did:ebsi(v2), did:jwk
   * others for ledgers public key as did:pkh, did:ethr, ??
   * did:ion ?
   * did:ala ? (Natural persons ?)
   * eidas certificates (x509 certificate CA)
   * Linked domains and other services 
   * ?


* for legal entities
   * interop ? 
   * did:web as a starter solution ?
   * register a new did method ? -> huge….
   * agreement with other ecosystems for legal entities onboarding ? 




* keys
- signature schemes
- NIST keys (rsa, p-256, etc)
- “Modern” EC  curves (secp256k1, ed25519 ) ??
- json-ld signature schemes vs  JOSE (depends on VC format)










Verifiable credentials 
* interop ARF/EBSI/ALASTRIA/GAIAX ??
* Format serialization : JWT vs JSON-LD or both
* CBOR for mDL or IOT ?
* other formats as anon-cred,  ?
* Holder binding ?
* selective disclosure ?
* Localization ?
* zkp ?
* @context  type  vs schemaId ?






Protocols
* to present verifiable credentials (and user authentication)  
   * SIOPv2
   * others ?
* * to exchange verifiable credentials/presentations 
   * OIDC4VP ?
   * others ?


* to issue credentials
   * OIDC4VCI
   * others ?


Wallet 
* key management (generate?, export ?)
* data management (export ?)
* mobile wallet onboarding (instance, certificate, API check ?…) 
* user binding requirement ?




Verifiable data registries
* did registry ? not needed if no did:abf method ???
* revocation list  VC  ?
* trusted issuer/verifier registry
* governance and accreditation  for registry updates ? 
* ?


Process 
* legal entity onboarding
* user onboarding
* conformance (wallet, issuer, verifier) ?
* ?




APIs
* for registries 
* storage ? (out of scope ?)
* timestamping, is it needed or out of scope  ?
* ledger  implementation
   * ethereum vs tezos ? 
   * do we need several implementations ?


Implementations and libs
* list of available libs
   * https://github.com/decentralized-identity
   * ?


 
Privacy considerations
* minimization of schema/data model
* anonymization of VCs -> correlation, etc 





References :


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