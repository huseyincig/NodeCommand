# Architecture (User View)

```text
your AI client ──MCP──▶ Node Command hub ──device protocol──▶ Node Command agent ──▶ your machine
```

- The **hub** hosts identity, workspaces, billing, the MCP gateway, and policy.
- The **agent** (`nc-agent`, open source) runs on your machine and executes
  admitted jobs: shell, files, logs, browser, services.
- The **contract** (`nc-protocol`, open source) pins tool names, schemas,
  and the agent wire shapes both sides implement.
- Hub internals (database, tenant logic, billing, deployment) are closed
  source; the agent and the contracts are fully auditable.
