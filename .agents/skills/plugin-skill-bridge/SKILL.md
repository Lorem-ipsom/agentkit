---
name: plugin-skill-bridge
description: Associate authorized MCP/plugin capabilities with reusable agent skills, maintaining an auditable registry.
---
# Plugin-to-Skill Bridge

When asked to integrate a plugin, discover its actual tools and input schemas first. Associate each tool to a skill by provider, capability, and intent. Generate a SKILL.md and registry record with tool name, description, input schema, permission class, required connection, and provenance. Never invent tools or infer permissions from a plugin name.

## Workflow
1. Discover installed connectors and their tools; distinguish installed from available.
2. Group read, write, deploy, and financial capabilities by intent.
3. Generate or update the registry; preserve stable identifiers and version history.
4. Require explicit authorization before installing connections, writes, deployments, transactions, or credential changes.
5. Never include access tokens, private keys, mnemonic phrases, or passwords in generated skills, commits, logs, or public endpoints.
6. Validate schemas and perform read-only checks before invoking an action.
7. Record outcomes accurately; do not claim deployment or execution without tool confirmation.

## Vercel and Codex
Use Vercel Connect for managed authorization and eve for durable agents. The skill is reusable by Codex when added to its project skills directory. A skill is instructions, not a grant of access to tools. The deployed registry is descriptive and must not expose secrets.
