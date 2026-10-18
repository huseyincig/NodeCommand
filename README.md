# Node Command

Operate your Windows, macOS, and Linux machines from any AI assistant —
through one Model Context Protocol (MCP) endpoint.

Give ChatGPT, Claude, Grok, Muse, and Gemini direct, secure access to your
computers. Read files, inspect services, and run commands over outbound-only
connections with strict policy ceilings and a cryptographic audit trail.

- **One connector URL** — `https://mcp.nodecommand.app/mcp`. Clients that
  support MCP OAuth discovery sign in automatically; nothing to copy or
  paste.
- **Single-command install** — `npx nc-agent` pairs the machine with an
  eight-character code, installs it as a service, and verifies it online.
- **Multi-host fleets** — talk to a cloud VPS, a home lab server, and a
  laptop in the same conversation. No inbound ports, no firewall changes.
- **Team access** — share machines as Viewer, Operator, or Admin. Never
  share SSH keys or credentials again.
- **Cryptographic proof** — every action is signed and chained in an
  immutable SHA-256 audit trail. Know who ran what, when, on which machine,
  and with what result.
- **Hard safety limits** — per-machine policy ceilings restrict file access,
  block dangerous commands, and enforce read-only execution modes.

## Quick start

1. **Install the agent** on the machine you want to control:

   ```bash
   npx nc-agent
   ```

   Approve the pairing in your browser with the eight-character code shown
   in your terminal. The agent connects outbound-only and runs as a system
   or user service. Your dashboard can also provide a direct command —
   `npx nc-agent <host_id> <token>` — for hands-off enrollment.

2. **Connect your AI assistant.** Add the MCP endpoint above as a custom
   connector or MCP server. Ready-made configurations live in
   [`examples/`](examples/) for ChatGPT, Claude, Cursor, VS Code, and
   OpenCode. Sign-in is automatic for clients that support MCP OAuth;
   header-based clients can use a personal access token.

3. **Ask.** Your assistant can see every enrolled machine in your
   workspace, and host actions always target an explicit machine — the
   platform never guesses one.

Full walkthrough: [`docs/getting-started.md`](docs/getting-started.md).

## Documentation

| Guide | What it covers |
| --- | --- |
| [Getting started](docs/getting-started.md) | Account, first machine, first connection |
| [Agent installation](docs/agent-installation.md) | Install, verify, update, uninstall |
| [Architecture](docs/architecture.md) | Hub, agent, and contract — what is open |
| [Security model](docs/security.md) | Tokens, device identity, audit chain, policy |
| [Clients (hosts)](docs/clients.md) | Machine IDs, fleet views, explicit targeting |
| [Troubleshooting](docs/troubleshooting.md) | Common symptoms and fixes |

## Related repositories

- **[nc-agent](https://github.com/huseyincig/nc-agent)** — the open-source
  host agent and CLI installer that runs on your machines.
- **[nc-protocol](https://github.com/huseyincig/nc-protocol)** — the
  canonical public wire contracts: agent protocol and MCP tool schemas.

## Contributing, security, license

- Contributions: [`CONTRIBUTING.md`](CONTRIBUTING.md) — docs, examples, and
  manifests live here; code lives in the two repositories above.
- Vulnerabilities: [`SECURITY.md`](SECURITY.md) — coordinated disclosure,
  never a public issue.
- License: Apache-2.0 — [`LICENSE`](LICENSE). Brand usage:
  [`TRADEMARKS.md`](TRADEMARKS.md).
