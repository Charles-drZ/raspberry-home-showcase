[← Raspberry Home case study](../README.md)

# Visual publication plan

Visual evidence is added only after the relevant dashboard or theme is stable and the exported image has passed a separate household-privacy, metadata, and reconstructability review.

The goal is to show responsive Home Assistant UX, cross-client validation, and visual-system work. It is **not** to publish the private household configuration, device inventory, entity mapping, network design, or operational implementation.

## Planned visual set

1. **`visuals/01-desktop-dashboard-overview.png` — Desktop dashboard overview**  
   Show the primary information hierarchy and room-oriented interaction model using reviewed, non-identifying labels and safe state values.

2. **`visuals/02-ios-companion-view.png` — iOS Companion App view**  
   Show the same product hierarchy in its touch-friendly mobile layout. Crop status-bar and notification information unless explicitly reviewed as safe.

3. **`visuals/03-theme-variant.png` — Selected theme variant**  
   Show one stable visual direction without exposing the underlying theme values, YAML, entity configuration, or private dashboard structure.

4. **`visuals/04-cross-client-consistency.png` — Cross-client validation evidence**  
   Present a safe desktop/iOS comparison that demonstrates consistent rendering after correction. Use reviewed synthetic or anonymized content rather than raw household captures.

5. **`visuals/05-responsive-information-architecture.png` — Optional responsive overview**  
   Use a redrawn or synthetic composition to explain how the same information hierarchy adapts between desktop and mobile without reproducing the deployable dashboard.

## Published visual set

### 2026-07-30 — Graphite production desktop and iOS evidence

Three owner-approved production captures are published in the main README:

- full desktop dashboard overview;
- iOS overview and climate hierarchy;
- iOS bedroom state composition.

Publication decisions:

- the captures were taken after an exact commit-bound Graphite deployment, configuration validation, restart, HTTP smoke, and cross-client acceptance;
- the GitHub-rendered `user-attachments` assets are reused directly from the private rollout issue rather than copying operational material into the public repository;
- visible room labels and state values were explicitly approved by the repository owner for portfolio publication;
- no IP address, hostname, account name, entity ID, device ID, integration ID, credential, notification content, access path, precise location, command, file path, backup identifier, or deploy token is visible;
- the desktop image is `1858 × 847`, and both selected iOS images are `603 × 1311` in their rendered GitHub attachment form;
- the images demonstrate responsive layout, active/idle/off/warning/unavailable state separation, and consistent Graphite rendering without publishing configuration or entity mapping;
- alt text and captions disclose that these are production captures while preserving the private implementation boundary;
- final Graphite visual publication approval was given by the repository owner.

This publication moves the case study from a Midnight-only presentation to a production-validated multi-theme result while keeping the broader theme-switcher implementation private.

### 2026-07-29 — Midnight cross-device presentation composite

The owner-approved `visuals/raspberry-home-midnight-across-devices.webp` is published in the main README as the first desktop-and-iPhone flagship visual.

Publication decisions:

- the image is explicitly classified as a presentation composite based on privacy-reviewed production captures, not as a raw production screenshot;
- the desktop and iPhone layouts communicate an already validated responsive product hierarchy without publishing dashboard configuration or entity mapping;
- visible labels are generic, and the displayed values are static presentation content;
- no IP address, hostname, account name, entity ID, device ID, integration ID, credential, notification, access path, precise location, or operational detail is visible;
- the final repository export is a metadata-stripped WebP at `699 × 393`;
- the final file SHA256 is `4eb0eb009674d4c8e16898446161b4ee96af14862cf51b83087f2ebbcf61f614`;
- alt text and the README caption disclose the private implementation boundary and the image's presentation nature;
- final publication approval was given by the repository owner.

This publication completes the desktop/cross-client deliverable while preserving the real iOS captures as separate client-level evidence.

### 2026-07-28 — Midnight v2 iOS Companion App

Two reviewed iOS captures are published in the main README:

- climate hero and active control hierarchy;
- bedroom hero, action, sensor, power, and maintenance composition.

Publication decisions:

- the Home Assistant account drawer, profile, URLs, hostnames, IP addresses, notifications, and access details are absent;
- no entity ID, device ID, integration ID, credential, diagnostic output, configuration, or operational path is visible;
- room labels are generic product labels rather than identifying names;
- the displayed state values are static and were explicitly approved by the repository owner for portfolio use;
- the iOS status information contains no notification content or personal identifier and was explicitly reviewed as safe for this release;
- the source captures were rendered through GitHub image attachments before public embedding;
- alt text and technical captions describe the product claim without exposing implementation details.

This publication completes the first stable mobile visual deliverable. The separately reviewed cross-client presentation composite now completes the desktop/iPhone follow-up.

## Capture and redrawing guidance

- Prefer a dedicated safe dashboard state or redrawn presentation over a raw everyday household screenshot.
- Use generic room and control labels when a real label could identify the home, occupants, routines, or location.
- Use synthetic, plausible state values. Do not blur sensitive live values when they can be replaced before capture.
- Keep the same crop, device-frame treatment, spacing, and image dimensions across related captures.
- Remove browser tabs, bookmarks, addresses, Companion App account surfaces, notifications, and unrelated application content.
- Avoid camera feeds, maps, precise weather locations, calendar entries, alarm states, presence information, energy histories, or personally revealing routines.
- Export as PNG or WebP. Do not publish raw HEIC captures, animated GIFs, editable SVG exports, or HTML dashboard exports.
- Remove image metadata before publication and inspect the final exported file at full resolution.

## Never include

- real entity IDs, device IDs, integration IDs, hostnames, IP addresses, URLs, ports, access paths, or remote-access information;
- household names, occupant names, addresses, precise locations, schedules, presence, notification content, or account information;
- camera imagery, door or alarm state, security-system details, or sensitive device availability;
- real diagnostic data, logs, error messages, backup names, file paths, configuration paths, or service details;
- dashboard YAML, theme YAML, card configuration, entity mapping, scripts, commands, deploy mappings, or recovery material;
- credentials, tokens, cookies, private keys, QR codes, pairing codes, or authentication surfaces;
- browser profile information, local machine details, or image metadata;
- GlassBox source code, implementation evidence, or unrelated private project information.

## Pre-publication checklist

- [x] The dashboard/theme state is stable and already accepted on the relevant client.
- [x] The published mobile visuals prove claims already supported by the written case study.
- [x] All visible labels and state values are generalized or explicitly approved for publication.
- [x] No entity, device, network, account, household, location, schedule, presence, diagnostic, or access detail is visible.
- [x] The images do not reveal reusable dashboard configuration or operational mechanics.
- [x] The mobile captures are readable in GitHub's narrow and wide layouts.
- [x] No notification content or unrelated application surface is visible.
- [x] The rendered publication assets contain no source EXIF or device metadata surface.
- [x] README captions accurately describe the evidence and the private boundary.
- [x] Final mobile publication approval was given by the repository owner.

The cross-client presentation composite passed its own review:

- [x] It proves a desktop-and-iPhone consistency claim already supported by production acceptance.
- [x] It is disclosed as a presentation composite rather than a raw runtime screenshot.
- [x] Its labels and values are generic presentation content.
- [x] No household, account, network, entity, device, notification, location, diagnostic, or access detail is visible.
- [x] The repository export contains no source EXIF, XMP, ICC, or device metadata.
- [x] The final dimensions and SHA256 are recorded.
- [x] Final cross-client publication approval was given by the repository owner.

The Graphite production captures passed a separate review:

- [x] They prove claims already supported by the commit-bound production rollout and visual acceptance.
- [x] The selected set covers desktop overview, mobile hierarchy, and state composition without unnecessary duplication.
- [x] No operational transcript, path, commit, hash, backup, token, account, network, entity, device, notification, or location detail is visible.
- [x] The selected GitHub attachment renders contain no exposed source metadata surface.
- [x] Alt text and captions distinguish production evidence from deployable implementation.
- [x] Final Graphite publication approval was given by the repository owner.

---

[← Return to Raspberry Home case study](../README.md)
