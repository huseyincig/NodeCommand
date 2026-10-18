# Agent Installation

The Node Command agent is the open-source runtime
([nc-agent](https://github.com/huseyincig/nc-agent)) that executes admitted
operations on your machine. It connects outbound over an encrypted
WebSocket — no inbound ports and no firewall rules.

## Requirements

- A current Node.js runtime (the installer enforces the supported engine
  version).
- A browser sign-in as the workspace user who owns the machine.

## Install (recommended: one command)

```bash
npx node-command
```

1. The CLI requests a device authorization and prints an eight-character
   code plus a verification URL.
2. Open the URL, sign in, enter the code, and approve the request.
3. The agent enrolls the machine, installs itself as a service, and
   verifies itself online.

Install mode is automatic — elevated shells install machine-wide,
everything else installs per-user. There are no prompts and no manual
service files.

The previous `npx nc-agent` command remains supported as an alias for the
same CLI.

### Direct enrollment command

The dashboard provides a per-machine host ID and one-time enrollment
token — redeem them directly:

```bash
npx node-command <host_id> <token>
```

Use it for scripted or hands-off enrollment. Enrollment tokens are
single-use and short-lived. Re-running `npx node-command` without arguments
resumes a minted-but-unused enrollment or starts a fresh one.

## Verify

The machine appears in your dashboard fleet as **online** once it holds a
live authenticated session. If it stays offline, see
[`troubleshooting.md`](troubleshooting.md).

## Updates

The agent updates itself from staged, hash-verified releases and rolls back
automatically if a new release fails its post-update health check. No
manual update step is required; update status is visible in the dashboard.

## Uninstall

```bash
npx node-command uninstall
```

This removes the local runtime and service registration while preserving
device identity, so the machine can reconnect without a new enrollment.
Server-side removal is a separate dashboard action. Details:
[nc-agent `docs/UNINSTALL.md`](https://github.com/huseyincig/nc-agent/blob/main/docs/UNINSTALL.md).
