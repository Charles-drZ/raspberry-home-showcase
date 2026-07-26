# Architecture

## System roles

The private environment uses a Raspberry Pi 5 as a small always-on platform for selected household services. This public repository describes roles and boundaries rather than copying the live topology.

```mermaid
flowchart TB
    CLIENTS[Desktop browser and iOS app]
    NETWORK[Home network and controlled remote access]
    PI[Raspberry Pi 5]
    DOCKER[Docker runtime]
    HA[Home Assistant]
    SUPPORT[Supporting local services]
    GIT[Private versioned source]
    CI[GitHub Actions]
    DOCS[Reviewed operational memory]
    PUBLIC[Sanitized public showcase]

    CLIENTS --> NETWORK
    NETWORK --> PI
    PI --> DOCKER
    DOCKER --> HA
    DOCKER --> SUPPORT
    GIT --> CI
    CI --> PLAN[Read-only plan and human approval]
    PLAN --> HA
    HA --> EVIDENCE[Runtime validation evidence]
    EVIDENCE --> DOCS
    DOCS --> PUBLIC
```

## Responsibilities

### Raspberry Pi and Docker

- provide an always-on ARM64 runtime;
- isolate Home Assistant and supporting services;
- keep persistent Home Assistant data outside the container image;
- make restart state and service ownership observable.

### Home Assistant

- integrate household devices;
- expose the existing default Overview;
- load a separate versioned YAML dashboard;
- load a versioned theme;
- validate configuration before restart.

### Private repository

- store reviewed source files, not the entire runtime;
- track work through GitHub Issues;
- use pull requests as implementation evidence;
- store durable Markdown decisions and sanitized runtime evidence;
- reject credentials, databases, `.storage`, backups and raw runtime exports.

### Public showcase

- explain the architecture and engineering decisions;
- publish generic configuration examples;
- document verified outcomes;
- omit real addressing, entity IDs, hostnames, locations and access details.

## Configuration flow

```mermaid
sequenceDiagram
    participant Dev as Reviewed branch
    participant CI as GitHub Actions
    participant Plan as Read-only plan
    participant Runtime as Home Assistant runtime
    participant Evidence as Durable evidence

    Dev->>CI: syntax, safety and synthetic rollback checks
    CI-->>Dev: pass
    Dev->>Plan: exact deployment ID
    Plan->>Runtime: config check and target inspection
    Runtime-->>Plan: state and hashes
    Plan-->>Dev: exact proposed change
    Dev->>Runtime: approved backup and atomic apply
    Runtime->>Runtime: post-write config check
    Runtime->>Runtime: explicit restart
    Runtime-->>Evidence: HTTP, log, desktop and mobile smoke
```

## Design principles

- One primary owner for routing and address assignment.
- Local operation is validated before remote-maintenance concerns.
- Runtime truth is not inferred from an old document.
- Repository content is an allowlisted source set, not a live filesystem mirror.
- Every production change has a baseline, backup, validation and rollback path.
- Public material explains the engineering without exposing the environment.

The real device inventory, network plan and configuration values remain private.