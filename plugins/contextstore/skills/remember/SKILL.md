---
name: remember
description: Save a durable project decision, convention, or fact to ContextStore when the user explicitly asks to remember it.
disable-model-invocation: true
---

# Save to ContextStore

Save only durable, useful context. Do not save credentials, tokens, secrets, personal data about other people, temporary debugging output, or entire conversations.

1. Summarize the fact or decision as a short, standalone statement and identify the project using a stable project slug when relevant.
2. Save to personal/project memory by default with `memory_store`, using a suitable `memory_type`, `project`, and tags.
3. Save to company memory only when the user explicitly asks. Call `org_access_scope`, show the exact authorized `team_id` choices, and ask which organization or department should receive the memory if the target is ambiguous.
4. For team saves, pass the exact returned `team_id`; do not construct IDs or infer access. The server enforces membership and role permissions.
5. Report whether the save succeeded. Do not claim success if the tool returns an error or `stored: false`.
