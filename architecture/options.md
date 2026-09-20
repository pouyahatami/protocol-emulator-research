# Architecture options

## Core problem

The architecture must balance:

- expressiveness for protocols not known at tapeout;
- throughput for fast pin transitions;
- silicon area within the Tiny Tapeout allocation.

This is an options document, not a specification.

## Execution-model candidates

### Programmable pin sequencer

A compact state machine with instructions for pin I/O, shifting, waiting, branching, and cycle delays. This resembles the RP2040 PIO design philosophy and is the current leading candidate.

Potential advantages:

- deterministic instruction timing;
- a small control path;
- protocol work can be offloaded to shift registers, side effects, and FIFOs.

Risks:

- limited arithmetic and state may make framing, CRCs, and error recovery awkward;
- code density may force a larger instruction memory;
- multiple engines duplicate state.

### Small general-purpose core

A compact CPU with memory-mapped pin and timing hardware.

Potential advantages:

- easier firmware development and richer control flow;
- existing assembler or compiler patterns may be reusable.

Risks:

- instruction overhead may miss fast protocol timing;
- the register file, ALU, and memory interface consume area needed by the pin datapath.

### Hybrid sequencer plus shared accelerator

One or more simple sequencers share expensive functions such as CRC, buffering, or serialization.

Potential advantages:

- keeps common protocol operations out of firmware loops;
- shared logic may be cheaper than duplicating features per engine.

Risks:

- arbitration can make timing data-dependent;
- shared blocks complicate verification and programming.

## Mechanisms worth evaluating

Each mechanism should earn its area through complete firmware examples and synthesis:

- per-engine clock division;
- an instruction delay field;
- side-set pin updates;
- automatic FIFO pull/push;
- first-class output-enable control;
- wait-for-pin instructions that support release and readback;
- configurable CRC/LFSR support;
- direct engine-to-engine data movement;
- modest arithmetic beyond decrement-and-branch.

## Required comparison artifacts

Before choosing an ISA or engine count, write representative firmware for:

- UART transmit and receive;
- SPI controller and peripheral modes;
- I2C controller behavior including ACK and clock stretching;
- a two-protocol bridge;
- one stretch workload that stresses framing or CRC.

For each candidate, record instruction count, cycles per bit, state requirements, memory footprint, and synthesized area of the necessary hardware.

## Early cycle-budget reference

At a proposed 50 MHz system clock, one cycle is 20 ns.

| Workload | Nominal bit time | System cycles per bit |
|---|---:|---:|
| UART at 115,200 baud | 8.68 µs | 434 |
| I2C fast mode at 400 kHz | 2.5 µs | 125 |
| CAN at 1 Mbit/s | 1 µs | 50 |
| USB low speed at 1.5 Mbit/s | 667 ns | 33.3 |
| SPI at 10 MHz | 100 ns | 5 |
| 10BASE-T half-bit | 50 ns | 2.5 |

These are arithmetic planning values, not proof that the pad path, physical design, firmware, or protocol implementation can operate at those rates.
