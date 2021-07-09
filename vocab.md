 # Vocab Talao
 
 
  ## IdentityPass
  
  This a Pass delivered by a company, it can be used for authentication.
  Specific properties as givenName, familyName, email, jobTitel, image er required.
  Author are organizations, logo and name properties are required.
  
  ### Example
  
  ```javascript
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
                "address" : "14 av de FRance, 75013 Paris",
                // bitthDate is optional
                "birthDate" : "13/09/1989",
                "givenName" : "",
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
 
 ## ProfessionbalExperienceAssessment
