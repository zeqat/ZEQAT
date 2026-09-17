# ZEQAT

ZEQAT is a privacy-focused communication and identity platform designed around
privacy, user-controlled identity, secure communication, and protected data.

## About ZEQAT

ZEQAT uses a privacy-oriented identity model designed to reduce reliance on
traditional phone-number-based identification.

The platform uses:

- Public display usernames
- Private `zq-username`
- ZQID identifiers
- QR-based device authentication
- Secure account recovery
- Protected messaging
- Voice communication
- Trusted devices
- Account security controls
- Protected file and vault functionality

ZEQAT is designed with privacy and user control as core principles.

---

## Identity System

ZEQAT separates a user's public identity from their private login identity.

### Display Username

The display username is the identity that may be visible to other users.

### Private zq-username

The `zq-username` is intended to remain private to the account owner.

It is used as part of the account authentication and recovery system.

### ZQID

A ZQID is a numeric identifier associated with a ZEQAT account.

Users can use a known ZQID to connect with another ZEQAT user without requiring
the user's phone number to be publicly searchable.

---

## Security Architecture

ZEQAT is designed with multiple security mechanisms, including:

- Account authentication
- Password protection
- Recovery phrase protection
- Optional six-digit security PIN
- Account lock mechanisms
- Trusted-device controls
- QR-based PC authentication
- Session protection
- CSRF protection
- XSS protection
- SQL injection protection
- Brute-force protection
- Bot and suspicious-access detection
- Protected vault functionality
- Account logout and deletion controls

Security mechanisms may differ between versions and deployments.

Security features described here should not be interpreted as a guarantee that
ZEQAT is impossible to compromise.

No software can provide an absolute guarantee of security.

---

## PC Login

ZEQAT supports a PC/Desktop authentication workflow using a QR code generated
or displayed by the desktop login system.

The mobile application can be used to authenticate the desktop session.

This design reduces the need to enter account credentials directly into a
desktop browser.

---

## Communication

ZEQAT provides communication functionality intended for ZEQAT users.

Depending on the deployed version, functionality may include:

- Person-to-person messaging
- Voice communication
- Friend management
- QR-based connections
- ZQID-based connections
- Group communication
- Rooms for external-platform communication workflows

Availability of individual features depends on the current ZEQAT release.

---

## Groups

ZEQAT supports group communication.

Group limits may depend on the subscription level and the current deployment.

---

## Rooms

ZEQAT Rooms are separate from ordinary groups.

Rooms are designed for controlled communication workflows involving external
platforms and users.

Rooms may support additional authentication mechanisms such as:

- PINs
- Passwords
- Tokens

Room limits and functionality depend on the applicable ZEQAT plan.

---

## Secure Files and Vault

ZEQAT includes protected file-management functionality.

Depending on the deployment, users may have access to:

- Vault
- Images
- Documents
- Sharing
- Backup
- Archive

File-sharing workflows may use temporary sharing tokens and additional
authentication requirements.

---

## Privacy Principles

ZEQAT is designed around the following principles:

1. Minimize unnecessary identity exposure.
2. Separate public identity from private authentication information.
3. Give users control over account security.
4. Avoid unnecessary third-party identity dependencies.
5. Provide user-controlled account and data-management functionality.
6. Protect sensitive information through appropriate security mechanisms.

---

## Open Source

ZEQAT may contain open-source components and repositories released under the
Apache License 2.0.

The Apache License applies only to the source code and components that are
actually distributed under that license.

Unless explicitly stated otherwise, the following are NOT automatically
licensed under Apache-2.0 merely because they are associated with this
repository:

- Private production infrastructure
- Private server configuration
- Private databases
- Private credentials
- Deployment secrets
- Third-party services
- Third-party libraries under their own licenses
- Unpublished ZEQAT source code
- Proprietary assets
- Trademarks and logos

For the exact scope of the open-source release, see the files and directories
included in this repository.

---

## License

Unless otherwise stated in a specific file or directory, the source code
distributed in this repository is licensed under the Apache License, Version
2.0.

See:

`LICENSE`

for the complete license text.

---

## Third-Party Software

ZEQAT may use third-party libraries, frameworks, services, or other software.

Third-party software remains subject to its respective license.

Users and contributors are responsible for reviewing the applicable licenses
for third-party components.

Additional attribution information may be provided in:

`NOTICE`

---

## Security Vulnerabilities

If you discover a security vulnerability in the publicly released ZEQAT
source code, please report it responsibly.

Do not publicly disclose a vulnerability before the maintainers have had a
reasonable opportunity to investigate and address it.

See:

`SECURITY.md`

for security-reporting information.

---

## Contributions

Contributions are welcome for the parts of ZEQAT that are released under an
open-source license.

Before submitting a contribution, please read:

`CONTRIBUTING.md`

Contributors should ensure that submitted code does not contain:

- Passwords
- API keys
- Private tokens
- Database credentials
- Personal information
- Production secrets
- Private server configuration

---

## Development

Clone the repository:

```bash
git clone https://github.com/zeqat/REPOSITORY.git