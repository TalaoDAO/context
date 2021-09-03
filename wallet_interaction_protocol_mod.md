# Interaction between the wallet and an Issuer / Verifier

## Prerequisite
This is the interaction protocol between the wallet and an Issuer or Verifier. This protocol is described by Spruce: https://github.com/spruceid/credible#supported-protocols .

Talao lightly modified this protocol to adapt it to its own use cases (business logic, EU/EBSI/ESSIF requirements,...).

## Verification of the identity of Issuer / Verifier 

### Motivation
The protocol of interaction between the wallet and an Issuer or a Verifier currently used by Credible is light, simple and quick to implement, However it does not allow the user of the wallet to ensure the identity of the other party but only the domain name specified in the URL encoded in the QR Code. On the other hand, a simple solution based on access to a public register of Issuers / Verifier (EBSI framework for instance...) makes it possible to obtain more precise information for the user and therefore better control without considerably increasing the complexity of the protocol. 

## Issuer / Verifier implementation
The Issuer (or Verifier) DID is passed as an argument in the QRcode callback URL examaple : https://talao.co/..../?issuer=did:ethr:0xee09654eedaa79429f8d216fa51a129db0f72250).

### Issuer Registry implementation
It is necessary to create a registry (centralized or on a blockchain) to store information about the Issuer and to define an API allowing access with a DID on behalf of the Issuer and its callback URL. We will start with 2 registries ans same API for both :


Talao Issuer Registry 
GET https://talao.co/trusted-issuers-registry/v1/issuers/did:ethr:0xee09654eedaa79429f8d216fa51a129db0f72250 

EBSI Trusted Issuer Registry
GET https://ebsi.....eu/trusted-issuers-registry/v1/issuers/did:ethr:0xee09654eedaa79429f8d216fa51a129db0f72250 

JSON response:
```javascript
{
    "issuer": {
        "preferredName": "Talao",
        "did": [did:ethr:0xee09654eedaa79429f8d216fa51a129db0f72250, "did:ebsi:00005555"],
        "eidasCertificatePem": [{}],
        "serviceEndpoints": [{}, {}],
        "organizationInfo": {
            "id": "BE55555j",
            "legalName": "Talao SAS",
            "currentAddress": "Talao, 16 rue de Wattignies, 75012 Paris, France",
            "vatNumber": "BE05555555XX",
            "domainName": "https://talao.co"
        }
    }
}
```

### Wallet implementation
An option in the settings menu allows user to opt for one of the 2 specific Issuer Registry (mentionned above). In this case if this register is used successfully, the area to access the confirmation request message will be enriched by Issuer data (name,...). 

Wallet makes a call to the Registry API with the DID associated with the QRCode “issuer” argument to read the Issuer callback and its details (legalName,...) from the registry. The wallet checks that the callback domainName is identical to the QRCode domain if this is the case it adds the legalName of the Issuer (and possibly other issuer details)  to the access confirmation request message. If this is not the case or if there is no register available, it indicates that the name of the Issuer could not be obtained and verified.

# credentialOffer

## Motivation

For holders wishes to engage with Issuers to acquire credentials, there must exist a mechanism for assessing what inputs are required from an issuer to process a request for credential issuance. The Credential Manifest is a common data format for describing the inputs a Subject must provide to an Issuer and the way the VCs shopuild be presented. This draft has been inpired by the Credential Manfifest specification with a very limited implementations of 2 items :

- user inputs : For some VCs it is necessary to transfer the personal data of the user's profile to the Issuer. This information is accessible in the menu Profile of the wallet. These are: the user's last name, first name, telephone, address and email.
- display output descriptors.

## Issuer implementation
Currently when the wallet does a GET on the Issuer URL, a JSON is returned to the wallet (Issuer GET response):

```javascript
{
           "type": "CredentialOffer",
           "credentialPreview": {...},
           "expires" : 12/08/2021Z "
 })
```

after agreement from the user, the wallet makes a POST request with a JSON:

```javascript
{
           “Subject_id”, ”did:tz:tz1e5YakmACgZZprF7YWHMqnSvcWVXZ2TsPW”,
}
```

The modification consists in adding a “scope” attribute and a "display" attribute to the JSON returned by the Issuer (Issuer GET response).

The “scope” attribute is a list with at least the “subject_id” item and possibly other items from the following list: “givenName”, “familyName”, “telephone”, “email”, “address”.


example:

```javascript
{
           "type": "CredentialOffer",
           "credentialPreview": {...},
           "expires" : 12/08/2021Z ",
           "scope ": [“ subject_id ”,“ familyName ”,“ givenName ”]
}
```

The "display" attribute is a description of the Issuer expectations about the UI design of the VC.

example:

```javascript
{
           "type": "CredentialOffer",
           "credentialPreview": {...},
           "expires" : 12/08/2021Z ",
           "scope ": [“ subject_id ”,“ familyName ”,“ givenName ”],
           "display" : { "backgroundColor : "#efefef",
                        "icon" : "reference sur un icon flutter",
                        "nameFallback" : "Ceci est le nom du VC par defaut",
                        "descriptionFallback" : "Ceci est la description du VC par defaut"
                        }
                       
}
```

## Wallet implementation
If there are items other than“ subject_id ”, the actions of the wallet will be:
1. ask the user for consent to transfer their personal data (a “consent screen”)
2. add the attributes and their value saved in the wallet to the JSON (wallet POST request), in our example:

```javascript
{
           “Subject_id”, ”did: tz: tz1e5YakmACgZZprF7YWHMqnSvcWVXZ2TsPW”,
            “familyName”: “Doe”,
            “givenName”: “John”
}
```

In the event that an attribute is missing in the profile saved in the wallet it would be replaced by “”.

See https://talao.co/wallet/test/credentialOffer for testing.

# presentationRequest

## Motivation

When interacting with a Verifier it is likely that it wants to get a presentation made up of specific VCs. It is therefore necessary to be able to specify to the wallet the conditions to be applied to the choice of VCs. 

The following specifications are taken from a minimalist interpretation of the draft  https://w3c-ccg.github.io/vp-request-spec/#query-by-example 

## Verifier implementation

There are 2 possibilities to foresee for the value of query.type of the JSON of the GET response of the Verify (“DIDAuth” or “QueryByExample”):

```javascript
{
           "type": "VerifiablePresentationRequest",
           "query": [{
               "type": “DIDAuth”
               }],
           "challenge": "a random uri",
           "domain" : "talao.co"
}
```

or: 


```javascript
{
           "type": "VerifiablePresentationRequest",
           "query": [{
               "type": "QueryByExample",
               "credentialQuery": [
                   {
                    ……
                   }]
               }],
           "challenge": "a random uri",
           "domain" : "talao.co"
 }
```

## Wallet implementation

### DIDAuth

If Query.type = “DIDAuth” , then it is a basic authentication request that does not include a verifiable credential : there is no selection of credential to propose to the user in the wallet, call thefunction didkit.DIDAuth(did, “{“ challenge ”:“ .... ”,“ domain ”:“ ..... ”}”, key) which will create an empty presentation used only for authentication. The presentation passed with the POST request will look like this:

```javascript
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1"
  ],
  "type": "VerifiablePresentation",
  "proof": {
    "type": "EcdsaSecp256k1Signature2019",
    "created": "2021-08-28T16: 13: 23.740Z",
    “challenge”: “d602e96d-08cb-11ec-a6fa-8d5c53eaebfb",
    “domain”: “talao.co”
    "jws ":" eyJhbGciOiJFUzI1NksiLCJjcml0IjpbImI2NCJdLCJiNjQiOmZhbHNlfQ..PgpEElB1tvcY9tdzK6EDKLvysj3vcH-zg5EIiGpk_q4m0NrAmjA81B7QdVvKllSzzfKw-1oTJuu4b4ihCvMXRwA
  "},
  "holder": "did:ethr:0xee09654eedaa79429f8d216fa51a129db0f72250"
}
```

### QueryByExemple

If Query.type ="QueryByExample "then it will take the user selects credentials in a list constituted according to the criteria specified in "credentialQuery.example". Then it will be necessary to call the didkit.issuePresentation (...) function as what is currently done (there is no change in the function call).

If "credentialQuery": is an empty list, one keeps the current behavior of Credible. The user is asked to select credentials to send. Never mind the VCs.

If "credentialQuery.example" contains {"reason": [......]}
then the Verifier wishes to display an information message to the user (see languages to be taken into account). This message will be displayed on the wallet at the time of selection.


If "credentialQuery.example" contains {"type": ["some_type", ...]}
then the Verifier wishes to receive VCs conforming to the specified type (s) and the wallet presents a list of VCs consisting only of the specified type (s)


If " credentialQuery.example " contains { " credentialSchema " : [" un_schema ", ...]}
then the Verifier wishes to receive VCs whose schema conforms to the specified type (s) and the wallet presents a list consisting only of the specified schema (s)


If "credentialQueryexample" contains { "trustedIssuer" : ["un_issuer", “un_autre_issuer”, ...]}
then the Verifier wishes to receive VCs sent by the specified Issuers and the wallet presents a list consisting only of the specified type (s).

NB : 
- There is one credentialQuery.example for each type of VC requested
- By default the credential is required ("required" : "True")
- The reason attribute should be analysed as an array of different languages ("fr", "en", ...) 

### Examples

#### Example 1
The Verifier wishes to receive VCs that the Issuer DID  did:tz:tz2NQkPq3FFA3zGAyG8kLcWatGbeXpHMu7yk:

```javascript
{
    "type": "VerifiablePresentationRequest",
    "query": [
        {
            "type": "QueryByExample",
            "credentialQuery": [
                {
                    "example" : {
                        "trustedIssuer": [
                            {
                                "issuer" : "did:tz:tz2NQkPq3FFA3zGAyG8kLcWatGbeXpHMu7yk"
                            }
                        ]
                    }
                }
            ]
        }
    ],
    "challenge": "9d0927c1-08cb-11ec-a6fa-8d5c53eaebfb",
    "domain": "talao.co"
}
```


#### Example 2
The Verifier requests a ResidentCard:

```javascript
{
    "type": "VerifiablePresentationRequest",
    "query": [
        {
            "type": "QueryByExample",
            "credentialQuery": [
                {
                    "example" : {
                        "type" : "ResidentCard"
                    }
                }
            ]
        }
    ],
    "challenge": "9d0927c1-08cb-11ec-a6fa-8d5c53eaebfb",
    "domain": "talao.co"
}
```

#### Example 3
The Verifier requests a ResidentCard and a DriverLicense and attaches messages for user :

```javascript
{
    "type": "VerifiablePresentationRequest",
    "query": [
        {
            "type": "QueryByExample",
            "credentialQuery": [
                {
                    "reason": "Join a Residency certificate.",
                    "example" : {
                        "type" : "ResidentCard"
                    }
                },
                {
                    "reason": "Join a Driver License.",
                    "example" : {
                        "type" : "DriverLicense"
                    }
                }
            ]
        }
    ],
    "challenge": "9d0927c1-08cb-11ec-a6fa-8d5c53eaebfb",
    "domain": "talao.co"
}

```

See https://talao.co/wallet/test/presentationRequest for testing.
