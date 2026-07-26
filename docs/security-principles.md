[← Raspberry Home case study](../README.md)

# Security and privacy principles

## Documentation is not a credential store

Technical notes can explain responsibility, validation, and recovery without containing passwords, private keys, access tokens, cookies, backup material, or a working combination of address and access details.

## Public/private separation

The project uses two deliberately different repositories:

- the private repository contains reviewed implementation, operational knowledge, evidence, and recovery procedures;
- the public showcase contains independently written engineering decisions and verified outcomes.

Publishing is a separate transformation and review step, not a mirror, export, or redaction pass over the private repository.

## Repository publication rules

- Never publish credentials, authentication data, private endpoints, runtime databases, logs, backups, or the complete configuration tree.
- Keep real network addresses, hostnames, device identifiers, entity identifiers, locations, and household routines private.
- Version only deliberately reviewed private source material.
- Run automated checks for high-confidence secrets, forbidden artefacts, internal identifiers, and private network details.
- Review generated files, screenshots, filenames, and metadata before publication.

## Operational safety principles

- Inspect the relevant live state before changing it.
- Keep the proposed change bounded and reviewable.
- Establish recovery readiness before applying a production change.
- Treat configuration validation, service restart, runtime availability, and user acceptance as separate evidence boundaries.
- Recover when validation or acceptance fails.
- Record the reviewed outcome and remaining risk.

The exact procedures, scripts, commands, file mappings, validation values, and recovery material remain private.

## Screenshot boundary

A raw household dashboard screenshot can reveal more than expected: names, rooms, schedules, device states, locations, internal addresses, diagnostics, or notifications.

Therefore:

- raw screenshots remain private;
- a public image must be cropped, anonymized, redrawn, or replaced when necessary;
- every public image requires manual privacy and metadata review;
- an image is omitted when its portfolio value does not justify the disclosure risk.

## Remote access

Remote maintenance uses a controlled private access layer. This public repository describes the principle only; it does not publish endpoints, routes, keys, device names, or setup values from the live environment.

## Why this matters

Good documentation shortens troubleshooting and handover. Strong publication boundaries prevent the same documentation from becoming a map or implementation guide for the system it is intended to protect.

---

[← Return to Raspberry Home case study](../README.md)
