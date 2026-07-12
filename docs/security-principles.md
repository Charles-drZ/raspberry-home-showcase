# Security principles

## Documentation is not a credential store

Technical notes can explain what a device does and how a maintainer should validate it. They should not contain passwords, private keys, access tokens, backup archives, or the combination of a public address and working access details.

## Practical rules

- Store credentials in an approved password manager, not in a repository.
- Record a password-manager reference only when necessary.
- Use controlled VPN-based access for approved remote maintenance.
- Give maintenance access a clear owner and revoke it when it is no longer needed.
- Keep customer details, device identifiers, and real network diagrams out of public documentation.
- Review screenshots and exported files for hidden metadata before sharing.

## Why this matters

Good documentation reduces troubleshooting time. Good security boundaries ensure that the same documentation does not become a path into a real environment.
