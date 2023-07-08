# Host Security

## Trusted Operating System

Create a trusted operating system disk image that can be deployed confidently to all machines
1) Initial baseline configuration - Deploy trusted environment
2) Integrity measurements for baseline deviation - Check deployed environments for deviation from initial baseline image
3) Remediation - fix differences between deployed system and initial baseline image

## Safe Patching

When patching it is important not to inflict unanticipated problems

Tools
- Sandboxing - environment to test new patches before they go live
- Ticketing - traceability and scrutiny of new patches before they go live
- Staging rollout

## Firmware Security

#### Tools

- UEFI - contains booting instruction 
- TPM (Trusted Platform Module) - on-board chip used to store cryptographic keys and hashes, grants security to boot and firmware
- HSM (Hardware Security Module) - addon security device, grants security to boot and firmware

#### Concepts

- Remote Attestation - separate system used to grant security to boot and firmware
- Hardware Root of Trust



## Mobile Device Security

Deployment Models
- Corporate Owned
- Corporate Owned, Personally Enabled
- Bring Your Own Device
- Choose Your Own Device
- Virtual Desktop Infrastructure

#### Mobile Device Management (MDM)

- Application management
- Device encryption
- Storage sementation
- Content management
- Containerization
- Remote Wipe
- Geolocation and Geofencing
