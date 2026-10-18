# ChatGPT

Use Node Command from ChatGPT as a custom MCP connector:

1. In ChatGPT, open **Settings → Connectors** (developer mode) and add a
   custom connector with the URL `https://mcp.nodecommand.app/mcp`.
2. Complete the OAuth sign-in when prompted and grant access to the
   workspace you want to operate.
3. Ask ChatGPT about your machines — it can list your fleet, and every
   host action targets an explicit machine.

ChatGPT connectors authenticate with OAuth. If you need a static-header
setup instead, use the personal access token flow with an MCP client that
supports custom headers; see [`../README.md`](../README.md).
