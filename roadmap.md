# Roadmap

Dates are intentionally omitted until the project start date and team capacity are known. Order and exit criteria matter more than nominal week counts.

| Stage | Work | Exit criterion |
|---|---|---|
| 0. Repositories | Create remotes, import template, establish CI | Inert 6x4 skeleton completes simulation and physical flow |
| 1. Workloads | Write protocol traces and candidate firmware by hand | UART, SPI, and I2C needs exist as executable tests or precise pseudocode |
| 2. Architecture | Compare execution models and ISA encodings | One architecture and minimal ISA are accepted through decision records |
| 3. Vertical slice | Implement assembler, model, and RTL for a minimal path | Firmware-driven UART transmit matches the reference model |
| 4. Feasibility | Synthesize and place-and-route realistic blocks | Area and timing meet documented targets with margin |
| 5. Baseline protocols | Complete UART, SPI, and I2C firmware | Protocol conformance tests pass for required modes and failures |
| 6. Verification depth | Add random, differential, formal, and mutation testing | Coverage goals and formal results are published with limitations |
| 7. Hardware validation | Run on FPGA and prepare board interaction | The same firmware works against real peripherals |
| 8. Submission | Freeze interfaces, docs, and reproducible build | Tiny Tapeout precheck and final submission checklist pass |

## Scope-cut order

If physical results do not fit, cut in this order unless measurements justify another choice:

1. Unimplemented stretch features.
2. Optional accelerators.
3. Program/data capacity above demonstrated needs.
4. Additional engines beyond the minimum useful bridge.

Do not weaken required verification or baseline protocol correctness to preserve speculative features.
