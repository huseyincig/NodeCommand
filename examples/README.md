# Client examples

Ready-made MCP client configurations for the Node Command endpoint:

```text
https://mcp.nodecommand.app/mcp
```

| Client | File | Where it goes |
| --- | --- | --- |
| ChatGPT | [`chatgpt/README.md`](chatgpt/README.md) | Custom connector (settings) |
| Claude Code | [`claude/claude.json`](claude/claude.json) | Project `.mcp.json`, or merge into your user config |
| Cursor | [`cursor/mcp.json`](cursor/mcp.json) | Merge into `~/.cursor/mcp.json` |
| VS Code | [`vscode/mcp.json`](vscode/mcp.json) | Copy to `.vscode/mcp.json` in your workspace |
| OpenCode | [`opencode/opencode.json`](opencode/opencode.json) | Merge into `opencode.json` |

## Authentication

Clients that support MCP OAuth discovery sign in interactively — nothing
to copy. The examples also cover clients that take a static
`Authorization: Bearer` header: create a personal access token in the Node
Command dashboard and expose it as the `NC_TOKEN` environment variable
(or paste it when the client prompts).

All secrets in these examples are placeholders or environment references —
never commit a real token.
