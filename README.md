# Protocol Emulator ASIC research

This Markdown-only repository contains the evidence and reasoning behind the programmable protocol-emulator ASIC.

Nothing here is automatically an implementation requirement. A proposal becomes binding only when its decision record is accepted and the corresponding specification and tests are added to the [ASIC repository](https://github.com/pouyahatami/protocol-emulator-asic).

## Start here

- [Project brief](project-brief.md)
- [External constraints](constraints.md)
- [Architecture options](architecture/options.md)
- [Verification strategy](verification/strategy.md)
- [Roadmap](roadmap.md)
- [Decision process](decisions/README.md)
- [Official references](references/official-links.md)

## Writing conventions

- Distinguish **confirmed**, **measured**, **estimated**, and **proposed** claims.
- Link external rules and hardware facts to primary sources.
- Put a date and test setup beside measurements.
- Give important choices their own decision record.
- Mark superseded material instead of quietly rewriting history.
- Prefer one topic per file and links over duplicated text.

## Status vocabulary

| Label | Meaning |
|---|---|
| Confirmed | Directly supported by an authoritative source |
| Measured | Produced by a documented experiment or tool run |
| Estimated | A planning value with stated assumptions |
| Proposed | A design choice still open to challenge |
| Accepted | A decision approved for implementation |
| Superseded | Historical material replaced by a later decision |
