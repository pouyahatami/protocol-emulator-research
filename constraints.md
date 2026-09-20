# Constraints and planning assumptions

Last reviewed: 2026-09-20.

## Confirmed by the competition announcement

| Item | Constraint |
|---|---|
| Process | IHP 130 nm CMOS5L through Tiny Tapeout |
| Allocation | 6x4 tiles |
| Nominal area | Approximately 0.7 mm² for 24 tiles |
| Capacity guidance | Roughly 1,000 logic cells per tile; an estimate, not a guarantee |
| License | Open source |
| Baseline demonstrations | UART, SPI, and I2C |
| Submission deadline | 2027-01-18 |
| Target shuttle | March 2027 CMOS5L shuttle, subject to foundry schedule |

Source: [Jane Street competition announcement](https://blog.janestreet.com/protocol-emulator-asic-competition/).

## Template-controlled constraints

The checked-out Tiny Tapeout template is authoritative for:

- the top-level module interface;
- legal `info.yaml` fields and values;
- required source, test, and documentation paths;
- CI and physical-design flow details.

When needed for analysis, link to the exact template revision instead of copying details that can drift.

## Planning assumptions to validate

| Assumption | Why it matters | Validation |
|---|---|---|
| 50 MHz is a useful design target | Sets protocol cycle budgets | Close timing after place-and-route and test on target hardware |
| A programmable pin sequencer is the best execution model | Drives the architecture | Compare firmware size, throughput, and synthesized cost against alternatives |
| Two engines are sufficient for a useful first system | Enables protocol bridging | Write representative bridge workloads and measure resource needs |
| Dedicated memory beats flip-flop instruction storage | Affects floorplan and program capacity | Synthesize both options and verify available CMOS5L macros |
| Eight-bit shift paths are sufficient | Could save sequential area | Write complete baseline and stretch-protocol firmware sketches |

These assumptions are not requirements. Promote them only through evidence-backed decision records.

## I/O observation

The standard Tiny Tapeout interface exposes eight dedicated inputs, eight dedicated outputs, and eight bidirectional pins. Only the bidirectional group has an output-enable path, so protocols requiring release/readback behavior compete for those pins. Confirm the exact interface in the imported template before freezing a pin map.
