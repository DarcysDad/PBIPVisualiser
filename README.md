# Power BI Model Visualizer

A browser-based tool for exploring Power BI semantic models and report definitions.

Built after finding it increasingly difficult to navigate an expanding consolidated model, it helps make dependencies, calculations and data sources easier to understand.

## Key features

- **Lineage:** Trace measures through dependent measures, columns, tables and underlying sources.
- **Source & Detail:** Inspect DAX, Power Query expressions and object properties, with links back to VS Code for editing.
- **Model Explorer:** Find a table and explore its immediate relationships without displaying the entire model at once.
- **Change impact:** Identify downstream calculations and report visuals potentially affected by a change.
- **Report view:** Explore PBIR page layouts and visual field bindings.
- **Audit and export:** Review potential reference issues and export documentation or audit results.

## Getting started

1. Download the HTML file and open it in a modern desktop browser.
2. Click **Open PBIP / model folder**.
3. Select a directory containing a **single PBIP project**, with its TMDL semantic model. Include the `.Report` folder to explore PBIR report definitions.
4. Select a measure or column, then explore **Lineage** and **Source & Detail**.
5. Click **VS Code** and enter the absolute path of the folder you opened to enable links to the corresponding source files.

The visualiser reads your project files locally. Editing takes place in VS Code; reopen the project folder in the visualiser to load your changes.

## Requirements and limitations

- Supports TMDL semantic models and PBIR report definitions. It does not open `.pbix` files directly.
- Analyses metadata and expressions; it does not execute DAX, refresh data or render live report results.
- Dependency and audit checks are static and may miss dynamic references, field parameters, calculation groups, filters and conditional formatting.
- **Not observed** means no usage was found in the scanned report bindings. It does not mean an object is safe to delete.
- Lineage diagrams use Mermaid, loaded from a local `mermaid.min.js` file or a CDN. If unavailable, diagram text remains available to copy.

## Possible future improvements

- Compare model versions and highlight changes.
- Expand report dependency coverage.
- Add a governed measure catalogue with ownership, approval status and review dates.
