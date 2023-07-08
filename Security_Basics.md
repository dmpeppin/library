# Security Basics

## CIA Triad

- Confidentiality
- Integrity
- Availability

### Confidentiality

Means to ensure that data is only available and viewable by intended authorized users.

Encryption - Encryption can be used to make information unreadable by unathorized personnel while authorized personnel can decrypt and recover access

Access Controls - Ensure only authorized personnel can access data

1) Identification - unique identifyer code (username, email, ID card) to establish individuality
2) Authentication - proof of identity with something known (password) and/or something held (key card)
3) Authorization - rules that state what information is or is not accessible to a user or group

Obfuscation - hidding or obscuring data (steganography is one particular method to accomplish objuscation)

> Encryption is the best means to ensure confidentiality. Access controls can restric access on controled systems. Obfuscationcan hide information "in plane sight"

### Integrity

Means to ensure that data has not been modified, tampered with, or corrupted

Hashing - a code based on the original information that, when consistent, ensures that the original information has not been modified

Digital Signatures, Certificates, Non-repudiation - Ensure that the information is from the true, intended source and not some imposter

- Digital Signatures (Certificates) - ensure that the source of information is in fact legitimate
- Non-repudiation - ensure that the source of information can not deny being the source

> Hashing can determine if information has been changed since created. Signatures can ensure that the information was created by a trusted source.

### Availability

Redundancy and Fault Tolerance - removing single point of failure SPOF

Patching for software stability

## Risk Concepts

### Risk Assessment

- Risk: possibility or likelihood of a threat expoloiting a vulnerability resulting in a loss
- Threat: a circumstance or event or actor that has the potential to compromise security
- Vulnerability: a weakness in a protected system
- Security Incendent: an sdverse event or series of events that compromise security 

> There is a risk that a threat can exploit a vulnerability leading to a security incident

Risk Mitigation: reduce chances that a threat will exploit a vulnerability, OR reduce the impact of a threat exploiting a vulnerability

### Security Controls

Types (Implemnations)
- Technical: uses technology tools
- Administrative: administrative or management methods
- Physical: controls that you can physically touch

Scopes (Goals)
- Preventative: prevents incidents from occuring
- Detective: detects incidents that are occuring or have occured
- Corrective: reverse the impact of an incident
- Deterrent: discourage threats from causing an incident
- Compensating: backup controls when primary control is not feasible

#### Technical Controls

- Encryption
- Antivirus software
- IDS, IPS
- Firewalls
- Password Rules
- Least Privilege

#### Administrative Controls

- Risk assessments - shows a calculus of valuable resources, systems protecting these resources, and cost benefit analysis for protection systems
- Vulnerability assessments - shows vulnerabilities of a system (but not what happens when they are compromised)
- Penetration Tests - a step beyond vulnerability assessment and show what can be done to a vulnerable system
- Management or Operational - training, change management, contingency planning

