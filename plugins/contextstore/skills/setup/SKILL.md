---
name: setup
description: Connect ContextStore memory to this coding agent and choose personal or authorized team memory scopes.
disable-model-invocation: true
---

# Set up ContextStore

Use the ContextStore MCP server already bundled with this plugin. If it is not connected, ask the user to finish the browser OAuth prompt shown by the coding agent, then retry.

1. Call `org_list` and `org_access_scope` to discover this signed-in account's organizations and exact permitted team IDs.
2. Show the user the available personal, organization, and department scopes. Do not infer a default team or department.
3. Ask which scope they want the agent to use for shared company context. Personal memory remains private and is not copied into a team scope.
4. Explain that backend membership, role, and department checks remain authoritative. Never ask for or store an API key for this plugin.
5. If the user does not choose a team scope, leave team memory unused and continue with personal/project memory only.
