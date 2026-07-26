# Security and privacy principles

## Documentation is not a credential store

Technical notes can explain what a device does, how a change is validated and how a maintainer can recover it. They must not contain passwords, private keys, access tokens, cookies, backup archives or a working combination of address and login details.

## Public/private separation

The project uses two deliberately different repositories:

- the private repository contains reviewed operational knowledge and selected real configuration sources;
- the public showcase contains only sanitized patterns, generic examples and verified outcomes.

Publishing is a transformation and review step, not a mirror or export.

## Repository rules

- Never commit credentials, tokens, private keys, `.env` files or raw authentication data.
- Never commit Home Assistant `.storage`, databases, logs, backup archives or the complete runtime directory.
- Keep real network addresses, hostnames, device IDs, entity IDs and locations private.
- Use explicit allowlists for versioned configuration and deployment targets.
- Run secret and forbidden-path checks in CI.
- Review generated files and screenshots for hidden identifiers and metadata.

## Runtime-change rules

- Read the live state before changing it.
- Record the reviewed source and target hashes.
- Create a timestamped backup before writing.
- Apply one exact file rather than copying a directory.
- Run Home Assistant configuration validation before and after the change.
- Automatically roll back a failed validation.
- Keep restart as an explicit action.
- Perform HTTP, log and user-interface smoke tests after restart.

## Screenshot boundary

A raw household dashboard screenshot can reveal more than expected: names, rooms, schedules, device states, locations, internal addresses or notifications.

Therefore:

- raw screenshots are private;
- a public image must be cropped, anonymized or synthetic;
- every public image requires manual review;
- an image is omitted when its portfolio value does not justify the privacy risk.

## Remote access

Remote maintenance should use a controlled private access layer. This public repository describes the principle only; it does not publish endpoints, routes, keys or setup values from the live environment.

## Why this matters

Good documentation shortens troubleshooting and handover. Strong publication boundaries prevent the same documentation from becoming a map of the system it is intended to protect.