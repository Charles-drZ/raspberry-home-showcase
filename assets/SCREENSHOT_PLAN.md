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

- [ ] The dashboard/theme state is stable and already accepted on the relevant client.
- [ ] The visual proves a specific claim already supported by the written case study.
- [ ] All labels and state values are synthetic, generalized, or explicitly approved for publication.
- [ ] No entity, device, network, account, household, location, schedule, presence, diagnostic, or access detail is visible.
- [ ] The image does not reveal reusable dashboard configuration or operational mechanics.
- [ ] Desktop and mobile crops are readable in GitHub's narrow and wide layouts.
- [ ] Browser chrome, notifications, status details, and unrelated application content are absent.
- [ ] Image metadata has been removed and the exported file has been reviewed separately.
- [ ] The README caption accurately describes the evidence and the private boundary.
- [ ] Final publication approval has been given by the repository owner.

---

[← Return to Raspberry Home case study](../README.md)
