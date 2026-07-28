[← Developer profile](https://github.com/Charles-drZ)

# Raspberry Home — Versioned Home Assistant & Safe Operations Case Study

Raspberry Home is a privacy-aware homelab project showing how I turned a working Raspberry Pi 5 and Home Assistant environment into a versioned, reviewable, rollback-aware, and cross-client validated platform.

> **This case study demonstrates controlled technical delivery, runtime validation, and user-facing Home Assistant work without publishing the private configuration or a reusable deployment package.**

## At a glance

**Runtime:** Raspberry Pi 5 with Docker and Home Assistant  
**Product surface:** Separate responsive Home Assistant dashboard  
**Client validation:** Desktop browser and iOS Companion App  
**Operations:** Reviewed change, backup, validation, rollback, exact reapply, and explicit restart boundaries  
**Quality controls:** GitHub Actions, repository safety checks, runtime smoke, and user acceptance  
**Release state:** Production-validated Midnight Signature Skin v2; broader multi-theme presentation continues privately  
**Public material:** Engineering decisions, privacy-reviewed outcomes, and non-deployable diagrams

## What this proves

- I can inspect a real running system and separate runtime truth from outdated documentation.
- I can version selected configuration without turning Git into an unsafe copy of the live environment.
- I can design production changes around review, backup, validation, rollback, exact reapply, and explicit operational boundaries.
- I can build a responsive Home Assistant UI and verify it across desktop and iOS clients.
- I can diagnose client-specific and state-specific visual defects, correct them, and repeat the acceptance cycle.
- I can publish credible engineering evidence without exposing household, network, credential, device, or implementation details.

## What I built

- A separate, version-controlled Home Assistant dashboard that preserves the existing default Overview.
- A responsive room-oriented interface built from native Home Assistant components.
- A Midnight signature visual system with distinct action, status, sensor, control, hero, active, idle, off, warning, and unavailable states.
- A controlled delivery workflow with reviewed source boundaries, backup, configuration validation, rollback, exact reapply, and explicit restart decisions.
- GitHub Actions checks for repository safety and change quality.
- A reviewed documentation flow for decisions, runtime evidence, and future maintenance.

## Verified outcome

The Midnight v2 rollout was validated on the real Raspberry Pi-hosted Home Assistant environment:

- pre-change and post-change configuration checks passed;
- reviewed dashboard and theme sources matched the deployed state;
- Home Assistant returned to service successfully after the approved restart;
- application and dashboard availability checks passed;
- no relevant startup or configuration errors were found;
- desktop browser acceptance passed;
- iOS Companion App acceptance passed;
- an idle-versus-active hero-state problem was corrected and revalidated;
- rollback restored the previous reviewed runtime state exactly;
- reapply restored the final Midnight v2 runtime state exactly;
- unrelated theme variants remained unchanged through the final delivery cycle.

## Delivery model

```mermaid
flowchart TD
    SCOPE[Reviewed scope] --> CHECKS[Repository safety checks]
    CHECKS --> PLAN[Read-only change review]
    PLAN --> APPROVAL[Human approval]
    APPROVAL --> BACKUP[Protected recovery point]
    BACKUP --> CHANGE[Bounded runtime change]
    CHANGE --> VALIDATE[Configuration and runtime validation]
    VALIDATE -->|pass| ACCEPT[Desktop and iOS acceptance]
    VALIDATE -->|fail| RECOVER[Rollback]
    ACCEPT --> REAPPLY[Rollback and exact reapply evidence]
    REAPPLY --> MEMORY[Reviewed operational evidence]
```

The diagram communicates responsibility and evidence flow only. The live topology, configuration, paths, scripts, mappings, identifiers, and access details remain private.

## Dashboard and UX work

The interface is organised around everyday user intent rather than integrations or vendors. It provides environmental context, common lighting and climate controls, room-level state, touch-friendly actions, and maintenance information.

The layout uses the platform's responsive behaviour so the same information hierarchy works across a desktop browser and a mobile companion app. The existing Overview remains available as a fallback rather than being replaced.

Midnight v2 adds a recognisable but restrained visual character: deep surfaces, cool cyan focus, clear state rails, differentiated hero intensity, and readable mobile labels. Active controls are prominent, while idle, off, warning, and unavailable states remain visibly distinct without turning every card into neon.

## Cross-client lesson

Desktop validation alone was not enough. The iOS Companion App exposed differences in rendering and label pressure that were not obvious in a wide browser layout. Later acceptance also showed that a climate hero could look active while reporting an idle action state.

I treated both findings as product defects rather than cosmetic exceptions: the visual contract was corrected, the reviewed changes were redeployed through the controlled operations flow, and acceptance was repeated on the real clients.

This demonstrates the value of validating the actual client experience instead of treating a successful configuration check or browser view as complete proof.

## Technology

Raspberry Pi 5 · Docker · Home Assistant · YAML · Bash · Git · GitHub pull requests · GitHub Actions · GitHub Issues · Markdown-based operational documentation

The validated Midnight v2 keeps native Home Assistant cards as the product surface and uses a bounded theme-layer styling dependency rather than custom dashboard cards or a separate frontend. Implementation details and reusable configuration remain private.

## Visual evidence

The following iOS Companion App captures were reviewed for publication. They contain no IP address, hostname, account name, entity identifier, device identifier, credential, notification content, access path, or precise location. The generic room labels and static state values were explicitly approved for this portfolio case study.

### Midnight climate and control hierarchy

<p align="center">
  <img src="https://github.com/user-attachments/assets/857da78e-44d5-429c-b95a-809ab5db0fe2" width="390" alt="Raspberry Home Midnight theme on iOS showing an idle climate hero above an active climate control card." />
</p>

The climate hero remains readable and visually important while its idle state is quieter than the active control card below it. This is the final state after the idle-versus-active polish and mobile label review.

### State-aware bedroom composition

<p align="center">
  <img src="https://github.com/user-attachments/assets/2d67c4fb-818f-42d3-89ef-a799c7619906" width="390" alt="Raspberry Home Midnight theme on iOS showing a bedroom dehumidifier hero, fan control, sensors, power state, and maintenance status cards." />
</p>

This view demonstrates the same mobile information hierarchy across a hero control, action tiles, read-only sensors, energy feedback, and explicit maintenance status.

See the [visual publication plan](assets/SCREENSHOT_PLAN.md) for the capture roles, household-privacy rules, and pre-publication checklist.

## Public boundary

The project is deliberately split into two layers:

- a private operational repository containing the reviewed implementation, real environment knowledge, evidence, and recovery procedures;
- this public case study containing only independently written explanations, non-deployable diagrams, privacy-reviewed visuals, and verified outcomes.

This repository contains no real IP addresses, locations, hostnames, entity identifiers, device IDs, credentials, remote-access details, private keys, backup archives, raw logs, copied production topology, deploy mappings, executable operations scripts, or reusable configuration examples.

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

- [Developer profile](https://github.com/Charles-drZ/Charles-drZ)
- [GlassBox product case study](https://github.com/Charles-drZ/glassbox-showcase)
- [Development workflow case study](https://github.com/Charles-drZ/glassbox-development-workflow)
- [Automation workflow case study](https://github.com/Charles-drZ/automation-workflow-showcase)
