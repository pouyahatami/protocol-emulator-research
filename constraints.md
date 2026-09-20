# Constraints and planning assumptions

Last reviewed: 2026-09-20.

## Confirmed by the competition announcement

| Item | Constraint |
|---|---|
| Process | IHP 130 nm CMOS5L through Tiny Tapeout |
| Allocation | 6x4 tiles |
| Nominal area | Approximately 0.7 mm² for 24 tiles |
| Capacity guidance | Roughly 1,000 logic cells per tile; an estimate, not a guarantee |
| Submission deadline | 2027-01-18 |

Source: [Jane Street competition announcement](https://blog.janestreet.com/protocol-emulator-asic-competition/).

## Template-controlled constraints

The checked-out Tiny Tapeout template is authoritative for:

- the top-level module interface;
- legal `info.yaml` fields and values;
- required source, test, and documentation paths;
- CI and physical-design flow details.

When needed for analysis, link to the exact template revision instead of copying details that can drift.

## I/O observation

The standard Tiny Tapeout interface exposes eight dedicated inputs, eight dedicated outputs, and eight bidirectional pins. Only the bidirectional group has an output-enable path, so protocols requiring release/readback behavior compete for those pins. Confirm the exact interface in the imported template before freezing a pin map.
