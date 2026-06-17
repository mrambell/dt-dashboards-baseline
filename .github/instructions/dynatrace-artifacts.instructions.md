---
description: "Use when creating or updating Dynatrace artifacts (dashboard, notebook, workflow), writing DQL for artifacts, validating tile/component execution, or using dtctl and Dynatrace MCP together for upload/deployment."
applyTo: "**"
---
# Dynatrace Artifact Creation Rules (dtctl + MCP)

## Scope and terminology

- An artifact means exactly one of: dashboard, notebook, workflow.
- Treat these rules as hard requirements, not optional preferences.

## Required toolchain

- Ensure both dtctl and Dynatrace MCP server are configured before creating or uploading any artifact.
- If either is missing or misconfigured, stop artifact generation and fix configuration first.

## DQL authoring and validation loop

- Always validate every DQL query used in an artifact component before upload.
- Use Dynatrace MCP server tools to create and check DQL.
- Also run a dtctl runtime check for each query (for example via `dtctl query ...`) to confirm executable behavior.
- Enter a correction loop until both MCP validation and dtctl runtime checks are valid.
- If uncertain about a query, build a generic working prototype first, validate it, then adapt to the specific use case.

## Artifact execution validation loop

- Before upload completion, test dashboards, notebooks, and workflows so all tiles/components execute successfully.
- After upload, validate the entire artifact (not only changed components) and verify there are no runtime/display errors in any tile/component.
- Enter a correction loop until display and execution are valid without errors.

## Quality and best practices

- Apply programming best practices: clear structure, maintainability, safe defaults, and explicit error handling.
- Apply data visualization best practices for dashboard/notebook components: readable layouts, meaningful labels, and appropriate chart/query pairing.
- Apply Dynatrace best practices for schema usage, DQL correctness, and artifact compatibility.

## Completion criteria

- Do not claim completion unless:
  - DQL is validated and corrected as needed.
  - Artifact components execute without errors.
  - Uploaded artifacts show no errors post-upload.
  - dtctl and Dynatrace MCP server were both used/configured as required.
