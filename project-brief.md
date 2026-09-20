# Project brief

## Objective

Design an open-source, general-purpose protocol-emulator ASIC: a small programmable engine whose instruction set supports deterministic pin reads, pin writes, direction changes, and cycle counting.

UART, SPI, and I2C are initial demonstrations, not three hard-wired peripherals. The design should be able to implement additional protocols after fabrication when their timing and I/O needs fit the hardware.

## Evaluation emphasis

The competition announcement emphasizes:

1. Novel functionality.
2. Novel design and verification methodology.

The project should therefore produce two equally credible artifacts: a useful programmable architecture and strong evidence that its behavior is correct.

## Success criteria

- The project skeleton completes the Tiny Tapeout CI and physical flow.
- UART, SPI, and I2C are implemented as firmware and verified against reference behavior.
- Instruction timing is specified precisely and checked automatically.
- Area, timing, and routability fit the 6x4 allocation with documented margin.
- The submission explains successful results and known limitations.

## Scope guardrails

- Prioritize deterministic pin control over general-purpose compute.
- Do not add a feature without a protocol use case and an estimated hardware cost.
- Do not claim a stretch protocol until a complete firmware sketch and cycle budget exist.
- Treat low-speed USB and 10 Mbit Ethernet as stretch goals, not baseline requirements.
