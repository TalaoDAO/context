 # Vocab Talao
 
 
  ## IdentityPass
  
  This a Pass delivered by a company, it can be used for authentication.
  
  ### Example
  
  ```javascript
  "@context" : [......],
  "id": "",
        "type": ["VerifiableCredential", "IdentityPass"],
        "issuer": "did:web:talao.co",
        "issuanceDate": "......",
        "credentialSubject" : {
            "id": "urn:.....",
            "type" : "IdentityPass",
            "recipient" : {
                // email is required
                "email" : "",
                // image is required,
                "image" : "https://mypicture.png",
                // telephone is optional
                "telephone" : "",
                // familyName is required
                "familyName" : "",
                // address is optional
                "address" : "",
                // bitthDate is optional
                "birthDate" : "",
                // givenName is required
                "givenName" : "",
                // gender is optional
                "gender" :  "",
                // JobTitle is required
                "jobTitle" : ""
                },
            // expires is optional
            "expires" : "",
            "author" : {
                // name is required
                "name" : "Talao",
                // logo is required
                "logo" : "https://talao.co/logo.jpg"
                  }
        }
}
```


 ## CertificateOfEmployment
 
 ## ProfessionbalExperienceAssessment
