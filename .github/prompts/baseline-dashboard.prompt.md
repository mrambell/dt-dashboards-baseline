---
description: "Create a baseline Dynatrace dashboard"
argument-hint: "Domain, use case, or artifact context"
agent: "agent"
---
Create a baseline Dynatrace dashboard for: $ARGUMENTS

Use [Dynatrace artifact rules](../instructions/dynatrace-artifacts.instructions.md) as a hard requirement.

The dashboard must:
- Stay simple to read and immediately useful for the domain at hand.
- Visually demonstrate value through correlated data, not isolated charts.
- Highlight where Problems affect other metrics, services, events, alerts, or user-facing behavior.
- Surface value-generation patterns such as many events or alerts concentrated into a single Problem.
- Emphasize views that make operations and SRE work easier during triage, diagnosis, and prioritization.

Execution requirements:
- Propose a compact dashboard structure with a small number of purposeful tiles.
- Prefer clear labels, readable visualizations, and direct signal over decorative complexity.
- If the best DQL is unclear, create generic prototypes first and refine them for the requested domain.
- Validate every DQL query, correct issues until valid, and verify the final artifact has no component errors.

In your response:
- State the dashboard goal in one short paragraph.
- List the proposed tiles and what decision each tile supports.
- Produce the dashboard artifact as dtctl-ready YAML by default.
- Include the dtctl upload and verification steps needed to apply the artifact and confirm it runs without errors.
- Summarize how the dashboard shows operational value and cross-signal correlation.