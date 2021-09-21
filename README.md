# Vocab Talao
 
 
## IdentityPass
  
It is a credential issued by a company or an organization. It can be used to authenticate with company services (access badge, information system) or with third parties who offer services for company employees (collective restaurant in an industrial zone, delivery to distributors for group purchases ...). The data contained on this credential is identical to that of a traditional identity card. This credential can be accepted by the company's partners with the same legitimacy as an identity card. 

An IdentityPass can be revoked.

### Use cases

Company pass, Student Card, Access badge

### Displayed attributes

* vc.credentialSubject.givenName,
* vc.credentialSubject.familyName,
* vc.credentialSubject.gender,
* vc.credentialSubject.telephone,
* vc.credentialSubject.email,
* vc.credentialSubject.address,
* vc.credentialSubject.birthDate,
* vc.credentialSubject.jobTitle,
* vc.credentialSubject.image,
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.address,
* vc.credentialSubject.issuedBy.logo

All attributes are optional except vc.credentialSubject.givenName and vc.credentialSubject.familyName. 

vc.expirationDate is displayed by default.

### Schema
  
``` javascript



```


## CertificateOfEmployment

### Description

This is the legal certificate of employment issued by a company at employee request.

### Displayed attributes

* vc.credentialSubject.familyName,
* vc.credentialSubject.givenName,
* vc.credentialSubject.jobTitle,
* vc.credentialSubject.employmentType,
* vc.credentialSubject.baseSalary,
* vc.credentialSubject.workFor.name,
* vc.credentialSubject.workFor.address,
* vc.credentialSubject.workFor.logo

All attributes are optional except vc.credentialSubject.givenName and vc.credentialSubject.familyName.

vc.issuanceDate is displayed by default.

### Schema

```javascript



```
## EmailPass

### Description

This credential is used only for authentication by email. All properties are required.

### Displayed attributes

* vc.credentialSubject.email

vc.issuanceDate is displayed by default.

### Schema

``` javascript



```

`
## PhonePass

### Description

This credential is used only for authentication by phone number. All properties are required.


### Displayed attributes

* vc.credentialSubject.telephone

vc.issuanceDate is displayed by default.


### Schema

``` javascript



```

## ProfessionalExperienceAssessment

### Description

It is a credential issued by a company to its employees, service providers or freelancers. This certificate is produced at the request of a Talent to prove the skills and know-how implemented during a project or a mission. It is generally produced after review and validation by the manager of the company. This certificate is most often offered in the form of a draft by the Talent then it is then completed by the company which adds an assessment on 4 particular themes which are communication, quality, respect for deadlines and a recommendation. .

### Name

* fr : Attestation d'expérience professionnelle
* en : Professional experience assessment
* de : 

### Schema

```javascript

```
## ProfessionalExperienceAssessment

### Description

### Name

* fr : Attestation de compétence professionnelle
* en : Professional skill assessment
* de : 

### Schema

```javascript

```

## LoyaltyCard

### Description

A loyalty card (often called a store card) is a marketing tool that helps build customer loyalty. Materialized in the form of a nominative card, it makes it possible to identify the most loyal customers and to grant them advantages in the form of services, gifts or discounts.

A LoyaltyCard can be revoked.

### Displayed attributes

* vc.credentialSubject.givenName,
* vc.credentialSubject.familyName,
* vc.credentialSubject.telephone,
* vc.credentialSubject.email,
* vc.credentialSubject.address,
* vc.credentialSubject.birthDate,
* vc.credentialSubject.programName,
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.address,
* vc.credentialSubject.issuedBy.logo

All attributes are optional except vc.credentialSubject.givenName and vc.credentialSubject.familyName. 

vc.expirationDate is displayed by default.

### Schema

```javascript


```
