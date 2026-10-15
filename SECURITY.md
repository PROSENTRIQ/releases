# Security policy

## Reporting a vulnerability

Please report suspected vulnerabilities in Prosentriq, its sensors, SDK, charts
or installer privately, in either of these ways:

- Email **security@prosentriq.com**
- On GitHub, open the affected repository's **Security** tab and choose
  **Report a vulnerability** (private vulnerability reporting)

Please don't open a public issue, pull request or discussion for a security
problem.

A useful report says what is affected (component and version, or the hosted
console), how to reproduce it, and what an attacker could achieve. We'll confirm
that we received it and keep you informed until it is resolved.

Our disclosure policy and acknowledgements are at
<https://prosentriq.com/security>. The machine-readable contact is at
<https://prosentriq.com/.well-known/security.txt>.

## Verifying what you install

Release artifacts and container images are signed with Sigstore (keyless, from
our release workflow). See
[PROSENTRIQ/releases](https://github.com/PROSENTRIQ/releases) for how to
verify them before you install.
