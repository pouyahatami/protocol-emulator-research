# Contributing

This repository is for evidence and design reasoning. Implementation changes belong in the [ASIC repository](https://github.com/pouyahatami/protocol-emulator-asic).

## Proposing work

Open or claim an issue before a substantial investigation. State the question, the decision it could affect, and the evidence needed to answer it.

Use a short-lived branch and keep pull requests focused on one research question or decision.

## Adding research

- Prefer primary sources.
- Put links next to the claims they support.
- State assumptions and units.
- Make calculations reproducible.
- Record tool versions, commands, configuration, and code commits for measurements.
- Separate observed results from interpretation.
- Do not copy source text when a concise summary and link are enough.

## Adding diagrams

Create and edit diagrams with [Excalidraw](https://excalidraw.com/). Follow [the diagram conventions](diagrams/README.md), including committing the editable `.excalidraw` source beside an exported SVG or PNG.

## Making a decision

Copy [`decisions/000-template.md`](decisions/000-template.md). Leave the status `Proposed` while evidence or review is incomplete. An accepted record must name the accepted option, explain why alternatives lost, and list consequences.

When a decision changes implementation behavior, open a linked ASIC-repository issue to update the specification, RTL, and tests.

## Pull requests

Explain:

- the question addressed;
- sources or experiments used;
- the conclusion and its confidence;
- decisions or implementation work affected;
- remaining uncertainty.
