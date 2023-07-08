# Access Management

## Identification, Authentication, Authorization, and Accounting

Identification: a unique identifier, allows activity to be attributed to a sole individual

Authentication: proving,confirming, verification of the identity of an individual (confirmed by an authoritive entity)

Authorization: defining the capabilities and rights of an individual

Accounting: traceability on the activities of an individual

> Authentication is crucial to utilize authorization and accounting configuration

### Authentication Factors

- Something you know: password, PIN
- Something you have: smart card, USB token, CAC (common access card), PIV (personal identity verification)
- Something you are: biometrics, like fingerprint
- Somewhere you are: geolocation information
- Something you do: gestures

> To have multi-factor, you need methods from at least 2 separate factors (PIN + password is not multifactor, PIN + fingerprint is multifactor)

#### Password Policies

Password rules can be set globaly with things like Group Policy Objects

#### Hardware and Software Tokens

A hard token is synced with the server upon deployment

A soft token uses an algorithm te generate codes
- HMAC: hash based message authentication code
- HOTP: HMAC based one-time password - uses secret key and incrementing counter and HMAC hashes the result **(does not expire)**
- TOTP: HMAC based one-time password - uses secret key and timestamp and HMAC hashes the result **(expires)**

#### Biometric Benefits and Limitations

Pros: Very difficult to falsify
Cons: Requires high tech sensors to be accurate

- FAR: False Acceptance Rate
- FRR: False Rejection Rate
- CER: Crossover Error Rate - low CER is indicative of both low FAR and low FRR and indicative of a good biometric sensor

#### Geolocation

Also very difficult to falsify

#### Authentication Services

- Kerberos - uses a system of issued tickets as proof of authentication
- LDAP - uses the X.500 standard to query directories for assests (users, computers, other objects)
- SSO - Single Sign-On - ability to log on or access multiple systems after a single authentication event
  - Good for limiting the number of credentials needed to know
  - Different than Same sign-on, witch uses the same credentials for each system, but requies authentication for each system
  - Transitive Trusts: If system A and System B trust each other, and System B and System C trust each other, then System A and System C will trust each other
- SAML - Security Assertion Markup Language - Based on XML, SSO Ffor web browsers
  - Shibboleth -  a federated SSO system often used on the internet

### Authorization Framework

Least Privilege - grant authorization for only the work that is needed and no more

Need to Know - grant authorization to access only data that is needed to know

#### Account Types

- End Users - most common, regular users
- Privileged Accounts - admin or other elevated authorization
- Guest Accounts - limited, often anonymous accounts, **lacks granular identification**
- Service Accounts - accounts used by services and applications

#### Principles in Account Management

- administrators use standard user accounts for daily activity, only use privileged accounts for special actions
- follow defined naming conventions
- prohibit shared and generic accounts
- disable inactive accounts

#### Access Control Models

- Role-BAC - Role-based access control: based work load type, often using groups as a mechanism (hierarchy, job-based)
- Rule-BAC - Rule-based access control: based on scenario rules, like firewalls, or event-triggered scenarios
- DAC - Discretionary access control: every object has an owner, and the owner can establish accessw for the object
  - based on SIDs (user and group IDs) 
  - using DACL (discretionary access control list)
- MAC - Mandatory access control: uses security classifications + compartments to limit access
  - compartments exists separatly and own a security level
  - security classifications rank the level of security allowed
  - a user needs both the security level and the compartment to gain access
- ABAC - Attribute-based access control: grants access based on attributes
  - Subject: users with certain attributes
  - Object: object to interact with
  - Action: allowable action to object by subject
  - Environment: other attributes to consider
