# Vocab Talao
 
 
## IdentityPass
  
It is a credential issued by a company or an organization. It can be used to authenticate with company services (access badge, information system) or with third parties who offer services for company employees (collective restaurant in an industrial zone, delivery to distributors for group purchases ...). The data contained on this credential is identical to that of a traditional identity card. This credential can be accepted by the company's partners with the same legitimacy as an identity card. 

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

This is the legal certificate of employment issued by a company at employee request.

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

This credential is used only for authentication by email. All properties are required.

### Example

``` javascript
{
    "@context": [
        "https://www.w3.org/2018/credentials/v1",...
       
    ],
    "id": "urn:uuid:2d9022d0-e0ae-11eb-898b-61ecf44705c2",
    "type": ["VerifiableCredential", "IdentityPass"],
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
```

## ProfessionalExperienceAssessment

### Description

It is a credential issued by a company to its employees, service providers or freelancers. This certificate is produced at the request of a Talent to prove the skills and know-how implemented during a project or a mission. It is generally produced after review and validation by the manager of the company. This certificate is most often offered in the form of a draft by the Talent then it is then completed by the company which adds an assessment on 4 particular themes which are communication, quality, respect for deadlines and a recommendation. .

fr : Attestation d'expérience professionnelle

en : Professional experience assessment

### Example

```javascript
{
    "@context": [
        "https://www.w3.org/2018/credentials/v1",...],
    
    "id": "data:28c9c084-d4cf-11eb-b332-02429c147bd7",
    "type": [
        "VerifiableCredential",
        "ProfessionalExperienceAssessment"
    ],
    "credentialSubject": {
        "id": "did:tz:tz2HXRc2HaBX7HEUMRn3CZNbgCpVYJJA752D",
        // skills are optional
        "skills": [
            {
                "@type": "DefinedTerm",
                "description": "JSON-LD"
            },
            {
                "@type": "DefinedTerm",
                "description": " Verifiable Credential"
            }
        ],
        "title": "Développement d'un contaxt JSON-LD",
        "endDate": "2021-06-22",
        "startDate": "2021-06-17",
        "author": {
            "logo": "QmNwbEEupT7jR2zmrA87FsN4hUS8eXnCxM8DsL9RXc25cu",
            "name": "Talao",
            "type": "Organization"
        },
        "recipient": {
            "name": "Thierry Thevenet",
            "type": "Person"
        },
        "review": [
            {
                "name": "reviewRecommendation",
                "reviewBody": "How likely are you to recommend this talent to others ?",
                "reviewRating": {
                    "bestRating": "5",
                    "ratingValue": "3",
                    "type": "Rating",
                    "worstRating": "1"
                },
                "type": "Review"
            },
            {
                "name": "reviewDelivery",
                "reviewBody": "How satisfied are you with the overall delivery ?",
                "reviewRating": {
                    "bestRating": "5",
                    "ratingValue": "3",
                    "type": "Rating",
                    "worstRating": "1"
                },
                "type": "Review"
            },
            {
                "name": "reviewSchedule",
                "reviewBody": "How would you rate his or her ability to deliver to schedule ?",
                "reviewRating": {
                    "bestRating": "5",
                    "ratingValue": "3",
                    "type": "Rating",
                    "worstRating": "1"
                },
                "type": "Review"
            },
            {
                "name": "reviewCommunication",
                "reviewBody": "How would you rate his or her overall communication skills ?",
                "reviewRating": {
                    "bestRating": "5",
                    "ratingValue": "3",
                    "type": "Rating",
                    "worstRating": "1"
                },
                "type": "Review"
            }
        ],
        "description": "Conception et test d'un verifiable credential pour les évaluations de projet. ",
        "signatureLines": {
            "image": "Qmac6K4suXyYaouFXxeBzDTr7XivTiq6cLWPh1puS6L7Kt",
            "jobTitle": "Director",
            "name": "",
            "type": "SignatureLine"
        }
    },
    "issuer": "did:web:talao.co",
    "issuanceDate": "2021-06-24T10:55:55Z",
    "proof": {
        "type": "EcdsaSecp256k1Signature2019",
        "proofPurpose": "assertionMethod",
        "verificationMethod": "did:web:talao.co#key-1",
        "created": "2021-06-24T10:55:55.327Z",
        "jws": "eyJhbGciOiJFUzI1NksiLCJjcml0IjpbImI2NCJdLCJiNjQiOmZhbHNlfQ..rTfDmiRP8K-IfrXmL8kaK-kgP9PkuCjbZzoUJbVrTQgcKJjrl_oXDaVd6vEQtGy5xfPIZrSp4-KAs_QTmP_T-w"
    }
}
```
