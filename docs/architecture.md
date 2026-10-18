# Architecture (User View)

```text
your AI client ──MCP over HTTPS──▶ Node Command hub ──device protocol──▶ nc-agent ──▶ your machine
```

- The **hub** hosts identity, workspaces, billing, the MCP gateway, and
  policy. It never exposes inbound access to your machines.
- The **agent** ([nc-agent](https://github.com/huseyincig/nc-agent)) runs on
  your machine and executes admitted operations: shell, files, logs,
  services, browsers.
- The **contract** ([nc-protocol](https://github.com/huseyincig/nc-protocol))
  is the canonical public definition of the agent wire protocol, the MCP
  tool surface, and the host policy schema.

Connections are outbound-only: the agent dials the hub over an encrypted
WebSocket and keeps a live authenticated session. Each machine has one
device identity (an Ed25519 key) enrolled out-of-band, and every admitted
action is recorded in the workspace audit chain.

Hub internals (database, tenant logic, billing, deployment) are closed
source. The agent and the contracts are fully auditable.

## Related

- [Getting started](getting-started.md)
- [Security model](security.md)
- [Clients (hosts)](clients.md)
