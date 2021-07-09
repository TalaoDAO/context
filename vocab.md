# Vocab Talao
 
 
## IdentityPass
  
 
This a pass delivered by a company, it can be used for authentication.
Specific person properties as givenName, familyName, email, jobTitle and image are required.
Author are companies or organizations, logo and name properties are required.

fr : Pass d'identité

en : Identity pass
 
### Example
  
``` javascript
{
        "@context" : [......],
        "id": "data:a59fbd98-d759-11eb-a013-6d473111f79f",
        "type": ["VerifiableCredential", "IdentityPass"],
        "issuer": "did:web:talao.co",
        "issuanceDate": "2021-06-27T15:09:40Z",
        "credentialSubject" : {
            "id": "did:tz:tz2HXRc2HaBX7HEUMRn3CZNbgCpVYJJA752D",
            "type" : "IdentityPass",
            "recipient" : {
                "email" : "john.doe@talao.co",
                "image" : "https://mypicture.png",
                // telephone is optional
                "telephone" : "+33608182594",
                "familyName" : "Doe",
                // address is optional
                "address" : "14 av de France, 75013 Paris",
                // bitthDate is optional
                "birthDate" : "13/09/1989",
                "givenName" : "John",
                // gender is optional
                "gender" :  "Male",
                "jobTitle" : "Director"
                },
            // expires is optional
            "expires" : "2025-06-27T15:09:40.230Z",
            "author" : {
                "name" : "Talao",
                "logo" : "https://talao.co/logo.jpg"
                  }
        },
        "proof": {
            "type": "EcdsaSecp256k1Signature2019",
            "proofPurpose": "assertionMethod",
            "verificationMethod": "did:web:talao.co#key-1",
            "created": "2021-06-27T15:09:40.230Z",
            "jws": "eyJhbGciOiJFUzI1NksiLCJjcml0IjpbImI2NCJdLCJiNjQiOmZhbHNlfQ..iUsZzBOc7ZVZosnJnhInpuJ4xVkTClmtSUGpkGSwn2wtGLpPN0vMhN_7-99W_7WQnawe0TyXS3N66b07h-b8yAE"
        }
}
```


## CertificateOfEmployment

### Description

fr : Attestation employeur

en : Certificate of employment

### Example

```javascript
{
    "@context": [ "https://www.w3.org/2018/credentials/v1",........],
    "id": "urn:uuid:2d9022d0-e0ae-11eb-898b-61ecf44705c0",
    "type": [
        "VerifiableCredential",
        "CertificateOfEmployment"
    ],
    "credentialSubject": {
        "id": "did:tz:tz2HXRc2HaBX7HEUMRn3CZNbgCpVYJJA752D",
        "type": "CertificateOfEmployment",
        "familyName": "Thevenet",
        "givenName": "Thierry",
        "startDate": "2021-07-15",
        "workFor": {
            "address": "16 rue de Wattignies, 75012 Paris, France",
            "logo": "https://gateway.pinata.cloud/ipfs/QmNwbEEupT7jR2zmrA87FsN4hUS8eXnCxM8DsL9RXc25cu",
            "name": "Talao"
        },
        "signatureLines": {
            "image": "https://gateway.pinata.cloud/ipfs/Qmac6K4suXyYaouFXxeBzDTr7XivTiq6cLWPh1puS6L7Kt"
        },
        // employmebType is optional
        "employmentType": "cdi",
        // jobTitle is optional
        "jobTitle" : "Concepteur",
        // baseSalary is optional
        "baseSalary" : "100000"
    },
    "issuer": "did:web:talao.co",
    "issuanceDate": "2021-07-09T12:07:24Z",
    "proof": {
        "type": "EcdsaSecp256k1Signature2019",
        "proofPurpose": "assertionMethod",
        "verificationMethod": "did:web:talao.co#key-1",
        "created": "2021-07-09T12:07:24.556Z",
        "jws": "eyJhbGciOiJFUzI1NksiLCJjcml0IjpbImI2NCJdLCJiNjQiOmZhbHNlfQ..A2GiN1w1X8ibsa3AcTgrgOPYuk0j5KUa7uZIpLnNSdBfzMPvtD1HtRAv2whZ96maQgqVgeAked3YtttDo0GktQE"
    }
}
```
## EmailPass

### Description

This VC is used only for authentication by email. All properties are required.

### Example

``javascript
{
    "@context": [
        "https://www.w3.org/2018/credentials/v1",
       
    ],
    "credentialSubject": {
        "id": "did:tz:tz1Yj23Pmn4bAxXe5vWDVEMocrgeWzWEMShE",
        "type": "EmailPass",
        "email": "thierry.thevenet@talao.io",
        "expires": "2022-07-09T14:55:19Z"
    },
    "issuer": "did:web:talao.co",
    "issuanceDate": "2021-07-09T14:55:19Z",
    "proof": {
        "type": "EcdsaSecp256k1Signature2019",
        "proofPurpose": "assertionMethod",
        "verificationMethod": "did:web:talao.co#key-1",
        "created": "2021-07-09T14:55:20.820Z",
        "jws": "eyJhbGciOiJFUzI1NksiLCJjcml0IjpbImI2NCJdLCJiNjQiOmZhbHNlfQ..0XsROuEk82AEM_rmYvv9Jq1rWgyDTTBRv_GhQCZHwtcsVhzBJvcC9GK-gpU1eKf56x16CSa4fZZzZ2_JCKUyBgA"
        }}}
``

## ProfessionbalExperienceAssessment
