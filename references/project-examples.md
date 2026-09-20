# Project examples

## UBC ASIC Montréal

Reviewed: 2026-09-20.

Repository: [ubc-asic/montreal](https://github.com/ubc-asic/montreal)

Montréal is an RV32E Tiny Tapeout project, so its processor architecture and SkyWater-specific setup are not directly reusable here. Its team practices are useful.

### Adopted

- One canonical `AGENTS.md`, with `CLAUDE.md` acting as a pointer.
- An `.editorconfig` and explicit line-ending policy.
- A root Makefile exposing memorable project commands.
- Clear contribution rules for focused changes and pre-commit checks.
- Separate homes for implementation, design verification, formal work, and documentation as those areas grow.
- Small tool-facing metadata files rather than one oversized project-context document.

### Deferred

- A central source `filelist.f`, until the RTL contains enough files to justify it.
- Separate `dv/tb`, `dv/formal`, and `dv/uvm` trees, until those environments exist.
- Dedicated lint configuration, until the HDL choice and lint tool are accepted.
- A setup script, until the IHP toolchain has been reproduced on the development platforms.

### Not copied

- The RISC-V architecture and instruction documentation.
- SkyWater-specific PDK setup.
- UVM infrastructure before simpler verification layers exist.
- Montréal's licensing and DCO policy; this project should choose those deliberately.

The Tiny Tapeout CMOS5L template remains authoritative for required paths such as `src/`, `test/`, `docs/info.md`, and `info.yaml`.
