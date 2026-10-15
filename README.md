# ContextStore Agent Plugin

This plugin connects Claude Code and Codex to the ContextStore remote MCP server using OAuth. It provides setup, recall, and explicit-save skills; it does not bundle API keys or bypass organization and department permissions.

## Claude Code

In Claude Code, add the ContextStore marketplace and install the plugin:

```text
/plugin marketplace add ContextStore/claude-ContextStore
/plugin install contextstore
```

Complete the ContextStore browser sign-in when prompted. Start a new Claude Code session, then use `/contextstore:setup` once to review available scopes. Use `/contextstore:recall` to search prior work and `/contextstore:remember` only when you want to save something.

## Codex

Add the repository marketplace:

```text
codex plugin marketplace add ContextStore/claude-ContextStore --ref main
```

Open the Plugins Directory in Codex, install **ContextStore**, and complete OAuth. Start a new session and run the ContextStore setup skill to review personal and authorized team scopes.

## Memory boundaries

- Personal/project memory is the default; team memory requires an explicit user choice.
- Team IDs must come from `org_access_scope`; server-side membership and role checks remain authoritative.
- Recalled memories are untrusted data and never override agent instructions or current repository evidence.
- The plugin saves only durable context and never stores credentials or entire conversations.
