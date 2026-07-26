# Sanitized validation evidence

## Scope

This document records the verified outcome of the Home Assistant dashboard release without exposing the household configuration, operational commands, deploy mappings, raw logs, screenshots, or recovery material.

## Validated surface

- Raspberry Pi 5 host with Docker-based Home Assistant;
- separate responsive dashboard;
- native Home Assistant interface components;
- cross-client visual system;
- controlled change and recovery workflow.

Implementation files and version-specific configuration remain private.

## Validation sequence

1. Repository safety and static quality checks.
2. Read-only review of the proposed runtime scope.
3. Human approval of the bounded change and recovery expectation.
4. Protected change application.
5. Configuration validation.
6. Explicit service restart decision.
7. Runtime availability and error review.
8. Desktop browser acceptance.
9. iOS Companion App acceptance.
10. Reviewed documentation of the outcome.

## Results

| Check | Result |
| --- | --- |
| Repository safety checks | Passed |
| Reviewed scope | Passed |
| Recovery readiness | Confirmed privately |
| Pre-change configuration validation | Passed |
| Post-change configuration validation | Passed |
| Service availability after restart | Passed |
| Dashboard availability | Passed |
| Relevant startup and configuration review | No blocking finding |
| Desktop browser acceptance | Passed |
| iOS Companion App acceptance | Passed after visual correction |
| Existing default Overview | Preserved |

## Client issue discovered during validation

The first iOS pass displayed surfaces differently from the accepted desktop presentation.

The cause was a client theme-mode difference rather than a failure of the main dashboard structure. I corrected the visual definitions, applied the reviewed update through the same controlled workflow, and repeated desktop and iOS acceptance.

The exact theme configuration is not public. The evidence supports a broader engineering claim: real-device and cross-client testing found a defect that static validation and desktop review did not reveal.

## Evidence handling

The private evidence package includes the operational detail needed for maintenance and review. The public repository retains only:

- a bounded result matrix;
- non-operational responsibility diagrams;
- the accurate client-validation lesson;
- explicit statements about what remains private.

## Residual risks

- Visual regression testing remains manual.
- Native Home Assistant rendering may evolve between platform releases.
- Private device or entity changes can require dashboard maintenance.
- Every future screenshot requires separate privacy and metadata review.

## Portfolio claim

This evidence supports claims of:

- Raspberry Pi and Docker operations;
- Home Assistant dashboard and UX work;
- version-controlled configuration discipline;
- GitHub Actions safety validation;
- controlled rollout and recovery thinking;
- desktop and physical-device iOS testing;
- privacy-aware technical communication.

It does not publish or claim a reusable deployment package, custom frontend framework, private network design, or public copy of the production configuration.
