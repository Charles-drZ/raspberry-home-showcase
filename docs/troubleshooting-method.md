# Troubleshooting method

## Start from the observable symptom

Describe what a person sees, what was expected, which device or service is affected and when the issue appears. Avoid deciding the cause before checking the boundary.

## Check from simple to specific

1. Confirm the service is running and reachable.
2. Confirm configuration validation succeeds.
3. Check whether the problem appears on one client or all clients.
4. Compare the same view, state and action across environments.
5. Inspect the smallest relevant source or runtime boundary.
6. Change one controlled variable.
7. Re-run machine checks and the original user flow.
8. Record the cause, correction, evidence and remaining risk.

## Real project example: desktop dark, iOS controls white

### Symptom

The Home Assistant dashboard looked correct in a desktop browser, but several controls used white surfaces in the iOS Companion App.

### Initial boundaries

- Home Assistant was running.
- The dashboard route returned HTTP `200`.
- Configuration validation passed.
- Controls were functional.
- The visual difference was client-specific.

This ruled out a general dashboard-load or runtime failure.

### Finding

The theme's critical dark values were primarily defined for dark mode. The iOS client could request a different theme mode and use light-mode fallback surfaces.

### Correction

Critical background, card, text, header and sidebar values were defined:

- at the theme root;
- under `modes.light`;
- under `modes.dark`.

### Re-test

- theme deployed through the same backup and config-check workflow;
- Home Assistant restarted successfully;
- configuration validation passed;
- iOS app was fully restarted;
- the dashboard rendered consistently and received user acceptance.

### Lesson

A successful server-side check does not prove cross-client presentation. Separate functional, transport and visual boundaries, then validate on the actual device category.

## A useful troubleshooting record

| Field | Purpose |
|---|---|
| Symptom | The user-visible problem. |
| Expected behaviour | What should happen instead. |
| Scope | Which clients, services or actions are affected. |
| Checks performed | Evidence collected in order. |
| Finding | The most supported cause or boundary. |
| Resolution | The controlled corrective action. |
| Re-test | What confirmed the result. |
| Remaining risk | Anything that still needs follow-up. |

This method transfers well to software support and systems investigation: reproduce carefully, narrow the boundary, collect evidence and document the outcome.