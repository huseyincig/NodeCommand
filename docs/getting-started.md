# Getting Started

## 1. Create your account

Sign up at the Node Command hub and enroll your first machine from the dashboard.
You will receive an enrollment command for your OS.

## 2. Install the agent

See `agent-installation.md`. One-liner per OS (Linux/macOS/Windows) plus
uninstall instructions. Sources: `nc-agent` repo.

## 3. Connect your AI client

Add the Node Command MCP endpoint to your client (examples in `examples/`):

```text
https://mcp.nodecommand.app/mcp
```

There is nothing to copy out of the dashboard: your app logs in by
itself using OAuth 2.1 (PKCE, no client secret) with the public client
id `nc-cli`. It opens your browser, you log in once and approve, and
the app receives its own bearer token (plus a refresh token) on a
loopback callback. Tokens are never shown in, stored in, or pasted
through the dashboard — if a page asks you to paste a token, stop.

Manual equivalent of what the app does (any loopback port works):

```text
1. Build a code_verifier + code_challenge (S256).
2. Open in your browser (replace PORT and CHALLENGE):
   https://mcp.nodecommand.app/oauth/authorize
     ?client_id=nc-cli
     &redirect_uri=http://127.0.0.1:PORT/callback
     &response_type=code
     &scope=mcp:write
     &code_challenge=CHALLENGE
     &code_challenge_method=S256
3. Log in, approve, copy the `code` your loopback listener receives.
4. POST /oauth/token { grant_type, code, client_id, redirect_uri,
   code_verifier } -> access_token, refresh_token, scope.
5. Call MCP with `Authorization: Bearer <access_token>` and, to pin a
   host, `X-Target-Client: nc_<64 hex>`.
```

A token grants only what you approved (typical scope: `mcp:write`,
which excludes admin tools). It expires; the app refreshes it with
the refresh token. To see your connected apps or disconnect one,
use your login session against `GET /api/oauth/grants` and
`POST /api/oauth/revoke` — no token secret is ever displayed.

## 4. Pick a host and act

Every host-targeting tool requires an explicit `client_id` (see
`docs/clients.md`). There is no implicit default host.
