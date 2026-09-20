# Architecture decision records

Use one file per decision. Name files sequentially, for example `001-execution-model.md`.

## Lifecycle

`Proposed` → `Accepted` → optionally `Superseded`.

A decision can also be `Rejected` when retaining the evaluated alternative is useful. Do not mark a decision accepted merely because it appeared in an early draft.

## Acceptance bar

An accepted decision identifies:

- the problem and constraints;
- alternatives considered;
- evidence, including measurements where available;
- the selected option and why;
- consequences and follow-up work;
- who or what process accepted it, and when.

Copy [000-template.md](000-template.md) when starting a decision.

## Initial decisions to write

- Execution model: pin sequencer, compact CPU, or hybrid.
- Number of engines.
- Instruction width and encoding.
- Shift-register and FIFO organization.
- Program-memory implementation and depth.
- Host-loading and configuration interface.
- Protocol-pin mapping and ownership.
- CRC/LFSR support.
