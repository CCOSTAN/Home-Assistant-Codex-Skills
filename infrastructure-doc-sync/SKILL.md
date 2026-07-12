---
name: infrastructure-doc-sync
description: "Use when Home Assistant, container, host, network, or service-placement changes require synchronized workspace instructions, README files, runbooks, dashboard shortcuts, and infrastructure inventories while keeping agent instructions concise and non-runbook."
---

# Infrastructure Documentation Sync

Keep Home Assistant and self-hosted infrastructure documentation aligned after operational changes. Discover the workspace's real documentation surfaces instead of assuming hostnames, paths, or products.

## Discover Update Targets

Inspect the workspace and update only applicable surfaces:

1. Workspace-level infrastructure instructions, such as a root `AGENTS.md` or equivalent policy file.
2. Repository-scoped instruction files affected by the change.
3. User-facing `README.md` files and architecture documentation.
4. Dedicated runbooks or operational baseline documents.
5. Dashboard, start-page, or service-catalog shortcuts.
6. Machine-readable infrastructure inventory or assistant-facing environment snapshots.

Do not invent a missing surface solely to satisfy this list.

## Workflow

1. Collect current runtime truth from the relevant hosts, containers, compose files, service APIs, and repository state.
2. Identify the authoritative source for host roles, service placement, URLs, ports, and storage.
3. Update workspace instructions first when shared topology changed.
4. Keep repository instructions limited to non-discoverable constraints and applicability gates.
5. Move long procedures from agent instructions into dedicated runbooks when practical.
6. Update user-facing documentation and shortcuts affected by the same change.
7. Refresh machine-readable infrastructure inventory when the workspace uses one.
8. Validate references against runtime and check that documentation surfaces do not conflict.
9. Reload or restart only the specific documentation/dashboard service when explicitly authorized and necessary.

## Instruction Quality Rules

- Prefer short constraints and checklists over narrative runbooks.
- Keep only high-impact, non-discoverable context in agent instruction files.
- Add applicability gates when guidance covers multiple scopes.
- Avoid duplicating the same policy across workspace and repository levels.
- Never publish credentials, tokens, private addresses, personal paths, or internal-only operational details.

## Dashboard and Shortcut Rules

- Prefer stable service names or public URLs over raw private IP addresses.
- Preserve the existing category and naming conventions.
- Change only the affected shortcut entries.
- Validate the dashboard configuration before any targeted reload.

## Inventory Content Rules

- Keep inventory content high-level and planning-focused.
- Record roles, relationships, and public-safe service identities.
- Avoid secrets, private file paths, and step-by-step recovery commands.
- Verify the rendered or API representation after writing when a live inventory surface exists.

## Output Contract

Always report:

- Files and surfaces changed, with their purpose.
- Final intended topology or service placement.
- Dashboard or shortcut changes, or that none were needed.
- Whether runbook content moved out of agent instructions.
- Inventory/snapshot validation status, or that no such surface exists.
- Runtime validation performed and unresolved follow-up items.
