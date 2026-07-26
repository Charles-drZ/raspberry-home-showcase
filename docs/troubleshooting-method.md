[← Raspberry Home case study](../README.md)

# Troubleshooting method

## Start from the observable symptom

Describe what a person sees, what was expected, which client or service is affected, and when the issue appears. Avoid deciding the cause before checking the boundary.

## Check from simple to specific

1. Confirm that the relevant service and user-facing surface are available.
2. Confirm that the accepted configuration and runtime checks pass.
3. Determine whether the problem appears on one client or across clients.
4. Compare the same state and action across the affected environments.
5. Inspect the smallest relevant source or runtime boundary.
6. Change one controlled variable.
7. Repeat the machine checks and the original user flow.
8. Record the finding, correction, evidence, and remaining risk.

## Project example: desktop accepted, iOS visually inconsistent

### Symptom

The dashboard matched the intended presentation in a desktop browser, while several surfaces appeared differently in the iOS Companion App.

### Boundary review

- the service and dashboard remained available;
- configuration validation passed;
- controls remained functional;
- the discrepancy was limited to client presentation.

This separated a visual client-specific defect from a general runtime or dashboard-load failure.

### Finding

The clients did not request the visual mode identically, which allowed a fallback presentation to appear on iOS.

### Correction and re-test

The visual definitions were made consistent across the supported client modes. The reviewed change followed the same controlled rollout, runtime checks, and desktop/iOS acceptance cycle.

The exact theme values, configuration structure, deployment steps, and private evidence remain outside this public case study.

### Lesson

A successful server-side check does not prove cross-client presentation. Functional, transport, and visual boundaries need separate evidence, including validation on the actual client category.

## A useful troubleshooting record

**Symptom**  
The user-visible problem.

**Expected behaviour**  
What should happen instead.

**Scope**  
Which clients, services, or actions are affected.

**Checks performed**  
Evidence collected in a deliberate order.

**Finding**  
The most supported cause or narrowed boundary.

**Resolution**  
The controlled corrective action, recorded privately when operational detail is sensitive.

**Re-test**  
What confirmed the result.

**Remaining risk**  
Anything that still requires follow-up.

This method transfers well to software support and systems investigation: reproduce carefully, narrow the boundary, collect evidence, and document the outcome without publishing the private implementation.

---

[← Return to Raspberry Home case study](../README.md)
