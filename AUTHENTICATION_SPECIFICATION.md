# Authentication Specification

## 1. Overview

ZEQAT uses a multi-layer authentication architecture designed to protect account access, device authorization, and security-sensitive operations.

Authentication is separated from the user's public identity.

The authentication architecture works together with:

- ZQID
- ZQ-Username
- Password authentication
- 24-phrase recovery
- QR authentication
- Device authorization
- Session security
- Access control
- Cryptographic identity components

---

## 2. Authentication Model

ZEQAT does not treat a username or ZQID as sufficient proof of account ownership.

The authentication process is designed to verify that the user or authorized device has the required credentials before access is granted.

Conceptually:

```text
Identity
   |
   v
Authentication
   |
   v
Device Authorization
   |
   v
Session Authorization
   |
   v
Protected ZEQAT Services
```

Each layer provides a separate security boundary.

---

## 3. Password Authentication

ZEQAT supports password-based authentication.

Passwords are authentication credentials and are separate from:

- ZQID
- ZQ-Username
- Public profile information
- Recovery phrases
- Private cryptographic keys

Passwords must be protected from plaintext exposure.

Authentication systems should also protect against:

- Brute-force attempts
- Credential stuffing
- Repeated failed authentication
- Session abuse
- Unauthorized login attempts

The exact password hashing and credential-storage implementation is defined by the production application.

---

## 4. ZQID and Authentication

ZQID identifies the ZEQAT account but is not itself a password.

Knowing a user's ZQID must not automatically provide access to the account.

Authentication credentials and authorization controls determine whether an operation is permitted.

This separation helps prevent an exposed identity identifier from becoming an account-access credential.

---

## 5. ZQ-Username and Authentication

ZQ-Username provides an additional identity layer.

The ZQ-Username can be used to identify or locate a ZEQAT account within supported application functions.

It should not be treated as a secret authentication credential.

Account authentication remains dependent on the required authentication controls.

---

## 6. 24-Phrase Recovery

ZEQAT provides a 24-phrase recovery mechanism.

The recovery phrases are security-sensitive credentials used to restore account access through the supported recovery process.

Recovery phrases must be protected by the user.

They should never be:

- Published
- Shared with other users
- Sent to support through ordinary messages
- Stored in publicly accessible locations
- Included in source code

A recovery process must verify possession of the required recovery credentials before allowing protected account recovery operations.

---

## 7. QR Authentication

ZEQAT supports QR-based authentication.

QR authentication can be used to establish an authorized connection between supported devices or authentication sessions.

A QR authentication process should verify:

- The intended authentication session
- The authorization request
- The participating device
- The validity of the authentication state

Security-sensitive QR data must be protected against unauthorized use.

Relevant threats include:

- QR replacement
- Replay
- Unauthorized scanning
- Session hijacking
- Phishing
- Unauthorized device authorization

---

## 8. Device Authorization

ZEQAT supports device authorization.

A device must be recognized as authorized before it can perform operations requiring device trust.

Device authorization provides an additional security layer beyond account identity.

Security-sensitive operations should verify the current authorization state before execution.

---

## 9. PC and Desktop Authentication

ZEQAT supports authentication across mobile and desktop environments.

The desktop authentication architecture can use QR-based authentication and device authorization to establish a trusted connection.

The purpose is to provide a controlled authentication process rather than relying exclusively on a conventional desktop login flow.

Desktop access must remain subject to server-side authentication and authorization checks.

---

## 10. Session Security

After successful authentication, ZEQAT establishes an authenticated session according to the application's session architecture.

Authenticated sessions should be protected against:

- Session theft
- Session fixation
- Session replay
- Unauthorized session reuse
- Cross-site attacks
- Improper session termination

Sensitive session information must not be unnecessarily exposed to client-side code or other users.

---

## 11. Failed Authentication

Failed authentication attempts should be handled in a way that limits abuse.

Security controls may include:

- Attempt limits
- Temporary restrictions
- Rate limiting
- Abuse detection
- Security logging
- Generic authentication errors

Authentication responses should avoid unnecessarily revealing whether sensitive account information is valid.

---

## 12. Authorization After Authentication

Successful authentication does not automatically grant unlimited access.

ZEQAT must separately determine whether the authenticated account or device has permission to perform the requested operation.

Conceptually:

```text
Authentication = Who is accessing?

Authorization = What is that identity allowed to do?
```

This separation is important for protected files, private rooms, account settings, administrative functions, and other sensitive resources.

---

## 13. Protected Operations

Security-sensitive operations should require appropriate authentication and authorization.

Examples include:

- Changing account security settings
- Managing authorized devices
- Accessing protected files
- Sharing protected resources
- Entering private rooms
- Managing recovery settings
- Performing sensitive account operations

The exact authentication requirements depend on the operation and production implementation.

---

## 14. Cryptographic Authentication

ZEQAT can use cryptographic identity components as part of authentication and device trust.

Cryptographic keys and authentication credentials serve different purposes from public identity identifiers such as ZQID.

Private cryptographic material must remain protected.

The exact cryptographic algorithms, key formats, and signing procedures are defined by the production implementation.

---

## 15. Authentication and Privacy

ZEQAT's authentication architecture is designed to reduce unnecessary exposure of personal identity information.

The system can authenticate users without requiring a phone number to function as the primary ZEQAT identity.

Authentication information should only be exposed to components that require it.

---

## 16. Authentication and Protected Communication

Authenticated accounts can participate in protected ZEQAT communication.

Authentication establishes account access and identity context.

Communication protection is handled by the separate cryptographic and secure-communication layers.

Authentication alone does not replace message encryption.

---

## 17. Authentication and File Security

Authentication and authorization controls protect access to files and folders.

A user may be required to authenticate before performing sensitive file operations.

Additional file controls may include:

- Access permissions
- Password protection
- Sharing tokens
- Download restrictions
- Expiration
- User-specific access

File encryption and authentication are separate security layers.

---

## 18. Authentication and Private Rooms

Private rooms use authentication and authorization to control access.

Knowing a room identifier or another user's ZQID should not automatically grant access to a protected room.

The application must validate the user's authorization before allowing entry or protected room operations.

---

## 19. Authentication Security Boundaries

The authentication architecture is part of a larger defense-in-depth model.

Relevant security boundaries include:

- Identity
- Authentication
- Authorization
- Device trust
- Session management
- Cryptography
- Database security
- Input validation
- File access controls
- Monitoring
- Recovery

A compromise of one component should not automatically provide unrestricted access to all ZEQAT resources.

---

## 20. Security Testing

Authentication should be tested against common attack scenarios, including:

- Brute-force authentication
- Credential stuffing
- Authentication bypass
- Session attacks
- QR replay
- Unauthorized device authorization
- Privilege escalation
- Account recovery abuse
- Enumeration
- Cross-site attacks
- Input manipulation

Testing should be performed against the actual production implementation.

---

## 21. Implementation Status

The following authentication components are implemented as part of the current ZEQAT platform architecture:

- Password-based authentication
- ZQID identity integration
- ZQ-Username integration
- 24-phrase recovery
- QR authentication
- Device authorization
- PC/mobile authentication architecture
- Authentication integration with protected ZEQAT services

Exact technical implementation details should be verified against the current production source code.

---

## 22. Security Disclosure

Authentication vulnerabilities should be reported responsibly according to:

`SECURITY.md`

Security researchers should not attempt to access accounts, private files, messages, recovery credentials, or other protected resources belonging to other users.

---

## 23. Disclaimer

This document describes the ZEQAT authentication architecture and intended security properties.

Documentation does not constitute proof that an implementation is secure.

Security properties should be validated through source-code review, testing, penetration testing, and independent security assessment where applicable.

This specification may evolve as ZEQAT's implementation and security architecture develop.

---

## 24. Related Documentation

- `README.md`
- `SECURITY.md`
- `SECURITY_ARCHITECTURE.md`
- `THREAT_MODEL.md`
- `CRYPTOGRAPHY.md`
- `ZQID_SPECIFICATION.md`

---

**ZEQAT — Be Clear. Private. Secure. Global.**