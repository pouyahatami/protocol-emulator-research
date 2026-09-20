# CLAUDE.md

Guidance for work in this research repository.

## Purpose

Use this repository for research, calculations, experiments, alternatives, decision records, risks, and planning for the programmable protocol-emulator ASIC.

Do not place synthesizable RTL or required Tiny Tapeout submission files here. Those belong in `pouyahatami/protocol-emulator-asic`.

## Evidence rules

- Label important statements as confirmed, measured, estimated, or proposed.
- Prefer primary sources and link them near the claim.
- Give measurements a date, tool version, command, configuration, and source commit.
- Keep assumptions visible.
- If a source may have changed, verify it before relying on it.
- Do not turn a proposal into a requirement without an accepted decision record.

## Decision workflow

1. State the problem and decision drivers.
2. Compare credible options using representative workloads.
3. Link calculations, firmware sketches, synthesis reports, or tests.
4. Record the decision in `decisions/`.
5. When accepted, update the corresponding implementation specification in the ASIC repository.

## Editing rules

- Keep one topic per file.
- Link instead of copying long sections.
- Mark old conclusions superseded; preserve their historical context.
- Put exact implementation behavior in the ASIC repository, not here.
- Never describe bounded formal checks, estimates, or pre-layout synthesis as stronger evidence than they are.
