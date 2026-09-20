# Diagram conventions

All project diagrams are created and maintained with [Excalidraw](https://excalidraw.com/).

## Required files

Keep the editable source and a rendered export together:

```text
diagrams/
  architecture-overview.excalidraw
  architecture-overview.svg
```

Prefer SVG for block diagrams, timing explanations, and other line art. Use PNG only when SVG does not render correctly in the target document.

## Naming

- Use lowercase kebab-case names.
- Give the source and export the same base name.
- Name diagrams for the concept they explain, not the document containing them.

## Editing workflow

1. Open the `.excalidraw` source in Excalidraw.
2. Make the change without flattening or replacing editable elements.
3. Export the updated diagram with the same base name.
4. Commit both the source and export in the same change.
5. Update Markdown references if the filename or purpose changed.

Do not edit only the exported image. The `.excalidraw` file is the source of truth.

## Review checklist

- Text remains readable at normal Markdown width.
- Signal names and terminology match the current specification or decision record.
- Colors are distinguishable without relying on color alone.
- Connectors do not ambiguously cross or terminate.
- The editable source and rendered export show the same revision.
