[← Developer profile](https://github.com/Charles-drZ)

# Raspberry Home

**A Raspberry Pi 5 / Docker / Home Assistant platform treated as a production engineering system.**

Raspberry Home began as a real household Home Assistant environment and evolved into two connected engineering tracks:

1. a responsive, state-aware product surface used from desktop and iOS;
2. a guarded operations model for changing a live Docker-based system with explicit trust, validation, rollback, and recovery boundaries.

The private repository contains the operational implementation. This public case study shows privacy-reviewed outcomes and engineering decisions without publishing deployable household configuration, access details, or privileged controls.

## At a glance

**Runtime:** Raspberry Pi 5, Docker, Home Assistant  
**Clients:** Desktop browser and iOS Companion App  
**Product work:** Responsive dashboards, visual state systems, cross-client acceptance  
**Operations work:** Backup, rollback, guarded updates, transactional recovery, trust validation, fail-closed behavior  
**Quality controls:** Repository safety checks, focused regression suites, runtime smoke, explicit user acceptance  
**Public boundary:** Architecture, verified outcomes, and sanitized visuals; no reusable production configuration

## Product surface

The Home Assistant interface is organized around user intent rather than integrations or vendors. It provides environmental context, climate and lighting control, room-level state, energy feedback, maintenance information, and clear unavailable/off/active distinctions.

Two visual systems — **Midnight** and **Graphite** — were developed and validated against the real environment. The work includes responsive behavior, mobile label pressure, state hierarchy, active-versus-idle presentation, and real iOS Companion App rendering rather than desktop-only screenshots.

A client-specific defect where an idle climate state appeared visually active was treated as a product defect: the visual contract was corrected, redeployed through the controlled change path, and revalidated on the real clients.

## Verified production outcome

The dashboard/theme delivery path has been exercised on the real Raspberry Pi-hosted environment with:

- pre-change and post-change configuration validation;
- reviewed source-to-runtime matching;
- protected recovery points before mutation;
- approved Home Assistant restarts;
- HTTP/application availability checks;
- desktop browser acceptance;
- iOS Companion App acceptance;
- rollback to the previous reviewed state;
- exact reapply of the accepted final state;
- durable operator evidence linking the deployed result to its reviewed source.

The later Graphite rollout repeated the same discipline instead of assuming the earlier successful deployment made future visual changes safe automatically.

## Operations engineering

The private Raspberry Home repository now goes substantially beyond the original dashboard case study.

A **closed-catalog guarded updater** has been implemented for carefully approved Docker Compose targets. The design intentionally avoids becoming a generic remote shell or arbitrary service updater.

Current repository-validated behavior includes:

- fail-closed target eligibility;
- immutable local image identity as the authoritative apply/rollback reference;
- separation of discovery metadata from runtime authority;
- bounded readiness-aware validation after service recreation;
- explicit unsafe-state latches;
- reboot-safe reconciliation of narrowly defined failed-run states;
- transactional installed upgrades;
- verified recovery material before live replacement begins;
- durable transaction-state boundaries around mutation;
- complete rollback verification after replacement failure;
- refusal of symlinked, writable, ownership-invalid, or otherwise untrusted privileged sources;
- fixed privileged bootstrap entrypoints rather than caller-selected commands;
- a fixed zero-argument privileged read-only discovery path;
- repository safety and focused regression suites containing hundreds of tests.

**Important boundary:** this newer updater work is repository-validated engineering. This public case study does not claim that every guarded-updater revision has already been deployed to production. Production access and mutation are separate acceptance gates.

That distinction is deliberate: a well-tested deployment mechanism is not presented as production-proven until the real runtime has actually exercised it.

## Safety model

```text
Reviewed scope
    ↓
Repository / trust validation
    ↓
Read-only discovery and planning
    ↓
Explicit authorization
    ↓
Verified recovery point
    ↓
Bounded mutation
    ↓
Configuration + runtime validation
   ↙                         ↘
rollback                    acceptance
   ↓                         ↓
verified recovery      durable evidence
```

The system favors fixed entrypoints and narrow authority over convenient generic privilege. Operations that have not earned a safe contract remain unavailable rather than being forced into the updater.

## Why this project matters

Raspberry Home demonstrates several engineering concerns in one real environment:

- product/UI work that must survive different client renderers;
- Linux and Docker operations;
- production-safe change planning;
- state-machine thinking around partial failure;
- rollback and recovery as first-class paths;
- privileged-boundary design;
- fail-closed handling of uncertain state;
- high-volume regression testing around operational invariants;
- strict separation between repository proof and production proof.

It is intentionally much closer to operating a small production platform than to keeping an unversioned collection of homelab configuration files.

## Visual evidence

The following images are privacy-reviewed production captures or presentation composites derived from accepted production captures. They contain no IP addresses, hostnames, account names, entity identifiers, credentials, device identifiers, private notification content, access paths, or precise location data.

### Graphite — desktop production dashboard

<p align="center">
  <img src="https://github.com/user-attachments/assets/b9d7588d-861e-44e3-96d7-e98b8dd70150" width="900" alt="Raspberry Home Graphite production dashboard in a desktop browser." />
</p>

### Graphite — iOS hierarchy and state model

<p align="center">
  <img src="https://github.com/user-attachments/assets/9ebc141c-5fd3-476c-b776-2af739d3e18d" width="390" alt="Raspberry Home Graphite theme in the iOS Companion App." />
  <img src="https://github.com/user-attachments/assets/eb76f236-6c02-4b9a-b825-1108748affd1" width="390" alt="Raspberry Home Graphite state-aware bedroom composition in iOS." />
</p>

### Midnight — cross-device presentation

<p align="center">
  <img src="assets/visuals/raspberry-home-midnight-across-devices.webp" width="700" alt="Raspberry Home Midnight showcase across desktop and iPhone layouts." />
</p>

See the [visual publication plan](assets/SCREENSHOT_PLAN.md) for capture roles and privacy rules.

## Technology

Raspberry Pi 5 · Linux · Docker · Docker Compose · Home Assistant · Python · Bash · YAML · Git · GitHub pull requests · GitHub Actions · automated regression testing · Markdown-based operational documentation

## Public boundary

The project is split deliberately:

- the private operational repository contains the real environment knowledge, implementation, tests, privileged tooling, deployment logic, runtime evidence, and recovery procedures;
- this public repository contains independently written explanation, non-deployable architecture, privacy-reviewed visuals, and bounded verified outcomes.

No real IP addresses, locations, hostnames, entity identifiers, device IDs, credentials, remote-access details, private keys, backups, raw logs, copied topology, deploy mappings, privileged scripts, reusable production configuration, or reusable configuration examples are published here.

**This is a portfolio case study, not a deployment package.**

## Explore the case study

- [Home Assistant UI and UX decisions](docs/home-assistant-ui-architecture.md)
- [Controlled change and recovery model](docs/safe-change-workflow.md)
- [Sanitized validation evidence](docs/validation-evidence.md)
- [Architecture and responsibility boundaries](docs/architecture.md)
- [Security and privacy principles](docs/security-principles.md)
- [Troubleshooting method](docs/troubleshooting-method.md)
- [Visual publication plan](assets/SCREENSHOT_PLAN.md)
- [Changelog](CHANGELOG.md)

## Related work

- [Developer profile](https://github.com/Charles-drZ)
- [GlassBox](https://github.com/Charles-drZ/glassbox-showcase)
- [NodeMedic](https://github.com/Charles-drZ/nodemedic-showcase)
- [Development workflow](https://github.com/Charles-drZ/glassbox-development-workflow)
- [Automation workflow](https://github.com/Charles-drZ/automation-workflow-showcase)
