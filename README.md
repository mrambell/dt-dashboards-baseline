# dashboards-value-rca

This repository packages practical guidance for creating and validating Dynatrace artifacts with an AI-assisted workflow focused on operational value and root-cause analysis (RCA).

## Purpose

The repository helps you:
- Build Dynatrace dashboards, notebooks, and workflows with consistent quality.
- Validate DQL queries before and during artifact creation.
- Use both dtctl and Dynatrace MCP together as the standard toolchain.
- Keep artifacts error-free after upload, with correction loops until all components execute cleanly.

## What is included

- `skills/dtctl/`
  - Core skill definition for dtctl usage in investigative and artifact-creation scenarios.
  - Command patterns, output conventions, and Dynatrace resource operations.
  - comes from the dtctl project https://github.com/dynatrace-oss/dtctl

- `skills/dtctl/references/`
  - Focused reference docs for DQL, troubleshooting, config management, and resource-specific patterns.

- `.github/instructions/dynatrace-artifacts.instructions.md`
  - Always-on workspace instruction defining hard rules for artifact scope, DQL validation loops, execution validation loops, and completion criteria.

- `.github/prompts/baseline-dashboard.prompt.md`
  - Reusable prompt template for generating baseline, domain-specific dashboards that highlight correlation and SRE value.

- `.vscode/mcp.json`
  - Workspace MCP server configuration for Dynatrace MCP.

## Working model

1. Configure dtctl context and Dynatrace MCP server.
2. Draft DQL queries (or start from generic prototypes when uncertain).
3. Validate queries with MCP checks and dtctl runtime checks.
4. Build artifact components (dashboard/notebook/workflow).
5. Test all components before upload.
6. Upload and validate the entire artifact.
7. Iterate until there are no display or runtime errors.

## Target audience

- SRE and operations engineers.
- Platform teams managing observability artifacts at scale.
- Developers performing incident triage and RCA with Dynatrace data.

## Outcome focus

The repository is optimized for dashboards and artifact flows that make day-to-day operations easier by showing correlated impact, not isolated metrics.
