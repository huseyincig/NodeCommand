# Getting Started

This guide takes you from zero to operating a machine from your AI
assistant.

## 1. Create your account

Sign up at [nodecommand.app](https://nodecommand.app) and open the
dashboard. You can enroll your first machine right away — the dashboard
offers both the one-command install and a direct enrollment command for
each machine.

## 2. Install the agent

On the machine you want to control, run:

```bash
npx nc-agent
```

The CLI prints an eight-character code and a verification URL. Open the URL,
sign in, enter the code, and approve. The agent then enrolls the machine,
installs itself as a service (machine-wide when elevated, per-user
otherwise), and comes online. No inbound ports, no firewall changes.

The dashboard also shows a ready-made command for the machine you are
enrolling:

```bash
npx nc-agent <host_id> <token>
```

which redeems that enrollment directly — useful for scripted setups.
Enrollment tokens are single-use and short-lived.

More detail: [`agent-installation.md`](agent-installation.md).

## 3. Connect your AI client

Add the Node Command MCP endpoint to your client:

```text
https://mcp.nodecommand.app/mcp
```

Clients that support MCP OAuth discovery handle sign-in automatically: the
client opens your browser once, you approve, and it receives its own
short-lived token. Nothing is copied out of the dashboard — if a page ever
asks you to paste a token, stop.

If your client takes a static `Authorization: Bearer` header instead,
create a personal access token in the dashboard and use it there. The
platform never displays or stores tokens in plaintext.

Ready-made client configurations: [`../examples/`](../examples/).

## 4. Choose a machine and ask

Every host-targeting request names an explicit machine — there is no
implicit default. List your fleet from the assistant or the dashboard,
pick a machine, and describe what you want in natural language.

## Where to go next

- Security model: [`security.md`](security.md)
- Machine management: [`clients.md`](clients.md)
- Troubleshooting: [`troubleshooting.md`](troubleshooting.md)
- Architecture: [`architecture.md`](architecture.md)
- Source and contracts:
  [nc-agent](https://github.com/huseyincig/nc-agent) ·
  [nc-protocol](https://github.com/huseyincig/nc-protocol)
