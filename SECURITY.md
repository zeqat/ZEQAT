# Security Policy

## ZEQAT Security

Security and privacy are core considerations of the ZEQAT project.

ZEQAT is designed with a security-oriented architecture covering identity,
authentication, protected storage, communication, file sharing, and
privacy-related controls.

However, no software or infrastructure can be guaranteed to be completely
free of vulnerabilities.

Security researchers and users are encouraged to report suspected
vulnerabilities responsibly.

---

## Supported Versions

Security support depends on the specific component and release.

| Version / Component | Security Support |
|---|---|
| Current public release | Supported |
| Older releases | May not be supported |
| Private production components | Not publicly distributed |

Security fixes may be applied to the current supported version before
being disclosed publicly.

---

## Reporting a Vulnerability

If you discover a potential security vulnerability in ZEQAT, please report
it privately rather than publicly disclosing the vulnerability.

A security report should include as much of the following information as
possible:

- Description of the vulnerability
- Affected component
- Affected version or commit
- Steps required to reproduce the issue
- Proof of concept, when safe to provide
- Potential security impact
- Any suggested mitigation or fix

Do not include passwords, private keys, recovery phrases, authentication
tokens, personal information, or other sensitive data in a security report.

---

## Responsible Disclosure

Please allow reasonable time for the issue to be investigated and, when
appropriate, corrected before publicly disclosing technical details.

ZEQAT may acknowledge security researchers who responsibly report
vulnerabilities, subject to the researcher's preference and applicable
circumstances.

---

## Security Testing

Security testing should be performed only against systems and environments
for which you have explicit authorization.

Researchers must not:

- Access accounts belonging to other users
- Access or extract private user data
- Obtain passwords, recovery phrases, or authentication credentials
- Modify or delete user data
- Disrupt or degrade ZEQAT services
- Conduct denial-of-service attacks
- Deploy malware or malicious payloads
- Attempt to compromise systems outside the authorized testing scope
- Publicly disclose sensitive vulnerability details before reasonable
  coordination

Testing against the ZEQAT production environment should only be performed
with explicit authorization.

---

## Scope

Security reports may concern publicly released ZEQAT repository components,
documentation, specifications, and other components explicitly identified
as part of the public project.

Private production infrastructure, server configurations, credentials,
secrets, internal systems, and unreleased source code are not automatically
part of the public repository or security-testing scope.

---

## Sensitive Information

Never commit or publicly disclose:

- Passwords
- API keys
- Private keys
- Recovery phrases
- Authentication tokens
- Database credentials
- Production configuration secrets
- User personal information
- Private server information
- Other confidential security information

If sensitive information is accidentally committed, remove it from the
repository and rotate or revoke the affected credential as appropriate.

Removing a secret from the latest commit does not necessarily remove it
from Git history. Historical exposure should be treated as a potential
credential compromise.

---

## Security Advisories

Confirmed vulnerabilities may be documented through the project's security
advisory process when appropriate.

Security advisories may include:

- Affected component
- Affected versions
- Severity information
- Description of the issue
- Mitigation
- Fixed versions or commits
- Disclosure information

Security details may be withheld or limited when publishing them could
increase risk to users.

See [`SECURITY_ADVISORIES.md`](SECURITY_ADVISORIES.md) for additional
security-advisory information.

---

## Authentication Security

ZEQAT includes security concepts such as:

- Private ZQ-Username authentication
- Password protection
- Recovery mechanisms
- QR-based desktop authentication
- Trusted devices
- Optional PIN protection
- Account locking
- Session and device controls

These mechanisms are part of the project's security architecture and should
not be interpreted as a guarantee of absolute security.

---

## Cryptography

Cryptographic mechanisms used by ZEQAT should be reviewed according to the
specific implementation and component.

See [`CRYPTOGRAPHY.md`](CRYPTOGRAPHY.md) for the project's cryptography
documentation.

Do not assume that a feature is cryptographically secure solely because
the project documentation describes it as secure.

---

## Security Architecture

Additional technical security documentation is available in:

- [`SECURITY_ARCHITECTURE.md`](SECURITY_ARCHITECTURE.md)
- [`THREAT_MODEL.md`](THREAT_MODEL.md)
- [`SECURITY_TESTING.md`](SECURITY_TESTING.md)
- [`CRYPTOGRAPHY.md`](CRYPTOGRAPHY.md)
- [`AUTHENTICATION_SPECIFICATION.md`](AUTHENTICATION_SPECIFICATION.md)
- [`ENCRYPTED_STORAGE.md`](ENCRYPTED_STORAGE.md)

---

## No Guarantee of Absolute Security

ZEQAT is developed with security and privacy as important design goals.

Nevertheless, security is an ongoing process. Vulnerabilities can exist in
software, dependencies, operating systems, servers, configurations, network
infrastructure, or user environments.

No statement in this repository should be interpreted as a guarantee that
ZEQAT is impossible to compromise or completely free from vulnerabilities.

---

## Responsible Security Research

ZEQAT supports responsible security research intended to identify,
understand, and help resolve security vulnerabilities.

Researchers are encouraged to provide sufficient technical information to
allow issues to be reproduced and investigated while avoiding unnecessary
exposure of sensitive information.

Thank you to everyone who helps improve the security of ZEQAT.