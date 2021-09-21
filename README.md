# Vocab Talao
 
 
## IdentityPass
  
It is a credential issued by a company or an organization. It can be used to authenticate with company services (access badge, information system) or with third parties who offer services for company employees (collective restaurant in an industrial zone, delivery to distributors for group purchases ...). The data contained on this credential is identical to that of a traditional identity card. This credential can be accepted by the company's partners with the same legitimacy as an identity card. 

An IdentityPass can be revoked.

### Use cases

Company pass, Student Card, Access badge

### Displayed attributes

* vc.name,
* vc.description,
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
* vc.credentialSubject.issuedBy.logo,
* vc.expirationDate.


All attributes are optional except vc.credentialSubject.givenName and vc.credentialSubject.familyName. 


### Schema
  
``` javascript



```


## CertificateOfEmployment

### Description

This is the legal certificate of employment issued by a company at employee request.

### Displayed attributes

* vc.name,
* vc.description,
* vc.credentialSubject.familyName,
* vc.credentialSubject.givenName,
* vc.credentialSubject.jobTitle,
* vc.credentialSubject.employmentType,
* vc.credentialSubject.baseSalary,
* vc.credentialSubject.workFor.name,
* vc.credentialSubject.workFor.address,
* vc.credentialSubject.workFor.logo
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.logo,
* vc.issuanceDate.

All attributes are optional except vc.credentialSubject.givenName and vc.credentialSubject.familyName.


### Schema

```javascript



```
## EmailPass

### Description

This credential is used only for authentication by email. It is an email proof.

### Displayed attributes

* vc.name,
* vc.description,
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.logo,
* vc.credentialSubject.email
* vc.expirationDate.


### Schema

``` javascript


```

`
## PhonePass

### Description

This credential is used only for authentication by phone number. It is a telephone proof.


### Displayed attributes

* vc.name,
* vc.description,
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.logo,
* vc.credentialSubject.telephone,
* vc.expirationDate.



### Schema

``` javascript



```

## ProfessionalExperienceAssessment

### Description

It is a credential issued by a company to its employees, service providers or freelancers. This certificate is produced at the request of a Talent to prove the know-how implemented during a project or a mission. It is generally produced after review and validation by the manager of the company. This certificate is most often offered in the form of a draft by the Talent then it is then completed by the company which adds an assessment on 4 particular themes which are communication, quality, respect for deadlines and a recommendation. .

vc.signatureLines is only used for paper or online publishing.

### Displayed attributes

* vc.name,
* vc.description,
* vc.credentialSubject.startDate,
* vc.credentialSubject.endDate,
* vc.credentialSubject.title,
* vc.credentialSubject.description,
* vc.credentialSubject.skills.description,
* vc.credentialSubject.review.name,
* vc.credentialSubject.review.reviewBody,
* vc.credentialSubject.review.reviewRating.bestRating,
* vc.credentialSubject.review.reviewRating.worstRating,
* vc.credentialSubject.review.reviewRating.ratingValue,
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.logo
* vc.credentialSubject.givenName,
* vc.credentialSubject.familyName,
* vc.issuanceDate.

### Schema

```javascript

```
## ProfessionalSkillAssessment

### Description

It is a credential issued by a company to its employees, service providers or freelancers. This certificate is produced at the request of a Talent to prove the skills implemented during a project or a mission. It is generally produced after review and validation by the manager of the company. This certificate is most often offered in the form of a draft by the Talent then it is then validated by the company.

vc.signatureLines is only used for paper or online publishing.

* vc.name,
* vc.description,
* vc.credentialSubject.startDate,
* vc.credentialSubject.endDate,
* vc.credentialSubject.title,
* vc.credentialSubject.description,
* vc.credentialSubject.skills.description,
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.logo
* vc.credentialSubject.givenName,
* vc.credentialSubject.familyName,
* vc.issuanceDate.

### Schema

```javascript

```

## LoyaltyCard

### Description

A loyalty card (often called a store card) is a marketing tool that helps build customer loyalty. Materialized in the form of a nominative card, it makes it possible to identify the most loyal customers and to grant them advantages in the form of services, gifts or discounts.

A LoyaltyCard can be revoked.

### Displayed attributes

* vc.name,
* vc.description,
* vc.credentialSubject.givenName,
* vc.credentialSubject.familyName,
* vc.credentialSubject.telephone,
* vc.credentialSubject.email,
* vc.credentialSubject.address,
* vc.credentialSubject.birthDate,
* vc.credentialSubject.programName,
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.logo,
* vc.expirationDate.

All attributes are optional except vc.credentialSubject.givenName and vc.credentialSubject.familyName. 


### Schema

```javascript


```

### AffiliationCard

### Description

Materialized in the form of a nominative card, it makes it possible to identify the members of an assoiation and to grant them advantages in the form of services, gifts or discounts.

An AffiliationCard can be revoked.

###  Use case

Membership's card, Club card, ... 

### Displayed attributes

* vc.name,
* vc.description,
* vc.credentialSubject.givenName,
* vc.credentialSubject.familyName,
* vc.credentialSubject.telephone,
* vc.credentialSubject.email,
* vc.credentialSubject.address,
* vc.credentialSubject.birthDate,
* vc.credentialSubject.memberOf.name,
* vc.credentialSubject.memberOf.address,
* vc.credentialSubject.memberOf.logo,
* vc.credentialSubject.membershipNumber,
* vc.credentialSubject.programName,
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.logo,
* vc.expirationDate.

All attributes are optional except vc.credentialSubject.givenName and vc.credentialSubject.familyName. 


## LearningAchievement

### Description

Learning achivement is an academic achievement or an academic performance which is the extent to which a student, teacher or institution has attained their short or long-term educational goals. Completion of educational benchmarks such as secondary school diplomas and bachelor's degrees represent academic achievement.

A LearningAchievement can be revoked.

### Use cases

Diploma, Micro credentials, Certificates

### Displayed attributes

* vc.name,
* vc.description,
* vc.credentialSubject.givenName,
* vc.credentialSubject.familyName,
* vc.credentialSubject.email,
* vc.credentialSubject.birthDate,
* vc.credentialSubject.hasCredential.title,
* vc.credentialSubject.hasCredential.description,
* vc.credentialSubject.issuedby.name,
* vc.credentialSubject.issuedBy.logo,
* vc.issuanceDate.
* vc.evidence


