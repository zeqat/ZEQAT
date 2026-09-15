# ZQID Specification

## 1. Overview

ZQID is ZEQAT's privacy-oriented digital identity system.

The ZQID model is designed to reduce dependence on ordinary public identifiers such as phone numbers while providing a unique identity reference for secure communication, authentication, device authorization, and protected ZEQAT services.

ZQID works together with ZQ-Username, authentication credentials, recovery mechanisms, QR authentication, device authorization, and ZEQAT security controls.

---

## 2. ZQID Identity Model

Each ZEQAT account is associated with a unique ZQID.

The ZQID acts as a primary identity reference inside the ZEQAT ecosystem.

The identity model separates:

- Public-facing account information
- ZQ-Username
- Unique ZQID
- Authentication credentials
- Recovery credentials
- Device authorization
- Cryptographic identity components

This separation is intended to reduce unnecessary exposure of personal information.

---

## 3. Unique ZQID

A ZQID is unique to its associated ZEQAT account.

The ZQID can be used as an identity reference when users connect, communicate, authenticate devices, or interact with ZEQAT services.

The ZQID architecture is designed so that users do not need to rely on a phone number as their primary ZEQAT identity.

---

## 4. ZQ-Username

ZEQAT uses a dedicated ZQ-Username as part of its identity architecture.

The ZQ-Username provides an additional identity layer separate from the user's ZQID.

This separation can help prevent the public-facing username from being treated as the complete authentication identity.

The ZQ-Username is intended for use within ZEQAT services while the underlying ZQID remains the unique account identity reference.

---

## 5. Identity Separation

ZEQAT separates identity information from authentication information.

Conceptually:

ZQ-Username
      |
      v
     ZQID
      |
      +---- Authentication
      |
      +---- Recovery
      |
      +---- Device Authorization
      |
      +---- Communication
      |
      +---- Protected Files
      |
      +---- Private Rooms

A username alone should not represent the complete security boundary of an account.

---

## 6. Authentication

ZQID operates together with ZEQAT authentication controls.

Authentication credentials are used to prove that a user is authorized to access an account.

The ZQID itself should not be treated as a password or secret.

Security-sensitive authentication material must remain protected and must not be exposed as ordinary public profile information.

---

## 7. 24-Phrase Recovery

ZEQAT provides a 24-phrase recovery mechanism for account recovery.

The recovery phrases are security-sensitive credentials and must be protected by the user.

They are not intended to function as a public identity.

The recovery mechanism is designed to provide a secure recovery path while maintaining separation between the user's public identity and recovery credentials.

Users must never publish, share, or transmit their recovery phrases to untrusted parties.

---

## 8. QR Authentication

ZEQAT supports QR-based authentication and verification.

QR authentication can be used to establish an authorized connection between devices or users without requiring the user to expose a traditional phone-number identity.

QR data must be treated as security-sensitive when it contains authentication or authorization information.

Applications implementing QR authentication should protect against:

- QR replacement
- Unauthorized scanning
- Replay
- Session hijacking
- Phishing
- Unauthorized device authorization

---

## 9. Device Authorization

ZEQAT supports device authorization as part of its account security model.

Authorized devices represent trusted access points to a user's ZEQAT account.

Device authorization should be independently validated by the server before sensitive operations are permitted.

A compromised or unauthorized device must not automatically receive the same trust level as an authorized device.

---

## 10. PC and Desktop Authentication

ZEQAT supports authentication across mobile and desktop environments.

The desktop authentication architecture can use device authorization and QR-based authentication to establish a trusted connection between the user's devices.

The security objective is to avoid relying solely on a conventional desktop username/password login flow.

Authentication decisions must be validated by the ZEQAT security layer before access is granted.

---

## 11. Identity and Communication

ZQID is integrated into ZEQAT communication features.

Users can use their ZEQAT identity to establish communication with other users without making a phone number the primary identity reference.

Communication authorization remains separate from simply knowing another user's ZQID.

Additional access controls can determine whether a communication request or connection is permitted.

---

## 12. Identity and File Sharing

ZQID can be associated with protected file and folder operations.

Identity information can be used to determine who is authorized to access shared resources.

Protected file-sharing operations may include:

- Access authorization
- Token-based sharing
- Password protection
- Download restrictions
- Expiration controls
- User-specific permissions

The ZQID identifies the account participating in the operation; it does not replace the access-control mechanism.

---

## 13. Identity and Private Rooms

ZQID can be used as an identity reference for private communication rooms.

Room authorization should determine which accounts are permitted to enter or interact with a protected room.

Knowing a ZQID alone should not automatically grant access to a private room.

---

## 14. Privacy Properties

The ZQID model is designed around identity minimization.

Key privacy objectives include:

- Reducing dependence on phone-number identity
- Separating ZQ-Username from the underlying unique identity
- Limiting unnecessary exposure of personal information
- Keeping authentication credentials separate from public identity
- Protecting recovery credentials
- Supporting QR-based device authorization
- Applying access controls to protected resources

ZEQAT should avoid exposing more identity information than is required for a specific operation.

---

## 15. ZQID Security Boundaries

ZQID is an identity reference, not a replacement for every security control.

The security boundary also includes:

- Authentication
- Authorization
- Session management
- Device authorization
- Cryptographic protections
- Database protections
- Input validation
- File access controls
- Rate limiting
- Security monitoring
- Recovery controls

Compromise of one identity component should not automatically imply unrestricted access to every ZEQAT resource.

---

## 16. Enumeration Protection

Systems using ZQID should consider protection against identity enumeration.

Security controls should prevent unauthorized users from using repeated requests to discover account information beyond what the application intentionally exposes.

Potential controls include:

- Rate limiting
- Access controls
- Generic error responses
- Request monitoring
- Abuse detection
- Permission checks

The exact implementation is defined by the production application.

---

## 17. Account Recovery Security

Account recovery is a security-sensitive operation.

Recovery mechanisms must verify that the person attempting recovery possesses the required recovery credentials.

Recovery should not weaken the security requirements applied during normal authentication.

Recovery credentials must never be stored or displayed in an unnecessarily exposed form.

---

## 18. ZQID and Cryptographic Identity

ZQID can operate together with ZEQAT's cryptographic identity components.

Cryptographic identity may be used to establish trust between accounts, devices, or protected operations.

The exact cryptographic algorithms, key formats, derivation methods, and signing mechanisms must be defined by the production implementation rather than inferred from the identity identifier itself.

ZQID should therefore be treated as an identity reference while cryptographic keys provide the underlying cryptographic security functions.

---

## 19. Blockchain Integration

ZEQAT's blockchain technology can be integrated with identity-related security operations.

Potential blockchain responsibilities include recording verifiable identity-related state or security events where appropriate.

Blockchain records should not contain unnecessary private information.

Sensitive personal data, passwords, recovery phrases, private keys, or plaintext confidential files should not be placed on a public or broadly accessible blockchain.

The exact blockchain data model is defined by the ZEQAT implementation.

---

## 20. ZQID and Proof of Agreement

ZQID can participate in ZEQAT's Proof of Agreement architecture.

For example, a security agreement can associate:

- Researcher ZQID
- Company identity
- Agreement state
- Vulnerability reference
- Reward conditions
- Participant approvals
- Agreement history

The purpose is to provide a verifiable identity reference for participants in security-related agreements.

Sensitive vulnerability details should remain protected rather than being exposed directly through public identity records.

---

## 21. Security Principles

The ZQID architecture follows these principles:

1. **Identity minimization**  
   Expose only the identity information required for an operation.

2. **Separation of identity and authentication**  
   Knowing an identity reference must not automatically provide account access.

3. **Least privilege**  
   Identity should only receive the permissions required for the requested operation.

4. **Defense in depth**  
   ZQID is one component of a larger security architecture.

5. **Credential protection**  
   Passwords, recovery phrases, private keys, tokens, and other secrets must remain protected.

6. **Device trust**  
   Device authorization must be explicitly controlled.

7. **Privacy by design**  
   Personal information should not be unnecessarily exposed.

8. **Auditable security**  
   Security-sensitive operations should be designed so they can be reviewed and tested.

---

## 22. Implementation Status

The following ZEQAT identity components are implemented as part of the current platform architecture:

- ZQID identity system
- ZQ-Username
- Password-based authentication
- 24-phrase recovery mechanism
- QR authentication
- Device authorization
- PC/mobile authentication architecture
- Cryptographic identity components
- Identity integration with ZEQAT services

Exact implementation details should always be verified against the current production source code.

---

## 23. Security Disclosure

Security vulnerabilities affecting ZQID or related authentication mechanisms should be reported responsibly through the security reporting process described in:

`SECURITY.md`

Security researchers should not attempt to access another user's account, private files, messages, recovery credentials, or other protected information.

---

## 24. Disclaimer

This document describes the ZQID security architecture and intended security properties of ZEQAT.

Documentation alone does not constitute proof of security.

Security claims should be supported by implementation review, testing, code analysis, penetration testing, and independent security assessment where applicable.

The ZQID specification may evolve as ZEQAT's implementation and security architecture develop.

---

## 25. Related Documentation

- `README.md`
- `SECURITY.md`
- `SECURITY_ARCHITECTURE.md`
- `THREAT_MODEL.md`
- `CRYPTOGRAPHY.md`

---

**ZEQAT — Be Clear. Private. Secure. Global.**