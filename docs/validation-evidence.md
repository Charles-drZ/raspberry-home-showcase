# Sanitized validation evidence

## Scope

This document records the verified outcome of the Home Assistant dashboard release without exposing the private household configuration.

## Tested implementation

- Raspberry Pi 5 host
- Docker-based Home Assistant
- Home Assistant 2026.6.3 at the time of validation
- separate YAML-mode dashboard
- native Home Assistant cards
- custom cross-client dark theme
- exact file deployment and guarded dashboard bootstrap

## Validation sequence

1. Repository safety and shell syntax checks.
2. Synthetic CI plan/apply/rollback tests.
3. Read-only plan against the real Home Assistant runtime.
4. Human review of exact source, target, hashes and configuration diff.
5. Timestamped backups.
6. Theme and dashboard deployment.
7. Guarded dashboard registration in `configuration.yaml`.
8. Post-write configuration validation.
9. Explicit Home Assistant restart.
10. HTTP, log, desktop and iOS smoke tests.

## Results

| Check | Result |
|---|---|
| Repository secret/safety scan | Passed |
| Shell syntax | Passed |
| Dashboard source structure | Passed |
| Synthetic apply and rollback | Passed |
| Real-runtime read-only plan | Passed |
| Source-to-target SHA-256 match | Passed |
| Pre-change config check | Passed |
| Post-write config check | Passed |
| Post-restart config check | Passed |
| Home Assistant root HTTP | `200` |
| New dashboard HTTP | `200` |
| Relevant startup error scan | No finding |
| Desktop browser acceptance | Passed |
| iOS Companion App acceptance | Passed after theme correction |
| Existing default Overview | Preserved |
| Rollback material | Created and verified available |

## Restart observation

Home Assistant became reachable within approximately six seconds during the recorded production smoke. This is an observation from one validated restart, not a performance guarantee.

## Mobile issue discovered during validation

The first iOS smoke showed white control surfaces despite a correct dark appearance in the desktop browser.

### Cause

The clients were not necessarily requesting the same theme mode. Critical dark values existed only under the dark-mode branch, allowing light-mode fallback values to appear in the app.

### Fix

Critical theme values were defined:

- at the top level;
- under `modes.light`;
- under `modes.dark`.

The theme was redeployed through the same backup and config-check workflow, Home Assistant was restarted, and iOS acceptance then passed.

## Evidence handling

Raw terminal reports, production backup names, real entity IDs and household screenshots remain private.

The public evidence consists of:

- this result matrix;
- sanitized configuration examples;
- architecture and workflow diagrams;
- an accurate description of the observed mobile issue and fix.

## Residual risks

- Visual regression testing is manual.
- Native Home Assistant card rendering may evolve in future frontend releases.
- Production entity renames can require dashboard maintenance.
- A public screenshot still requires a separate sanitization review.

## Portfolio claim

This evidence supports claims of:

- Raspberry Pi and Docker operations;
- Home Assistant dashboard engineering;
- YAML and Bash implementation;
- GitHub Actions validation;
- guarded deployment and rollback design;
- desktop and real-device iOS testing;
- privacy-aware technical documentation.

It does not claim a custom HTML frontend, a custom JavaScript component or card-mod-based styling.