# Troubleshooting

| Symptom | Check |
|---|---|
| Machine never shows online | Is the agent service running? Is the clock in sync? Re-run `npx node-command` to re-enroll if keys were rotated |
| Pairing code rejected or expired | Codes and enrollment tokens are short-lived — re-run `npx node-command` for a fresh one |
| `CLIENT_NOT_FOUND` | Wrong machine ID, or the machine belongs to another workspace |
| `HOST_POLICY_DENIED` | The requested capability is not granted to this machine |
| Update stuck | Check the dashboard job status; the agent rolls back automatically on a failed activation |
| 429 rate limited | High-risk operations are throttled; space out requests |
| Assistant cannot reach the endpoint | Confirm the client points at `https://mcp.nodecommand.app/mcp` and completed sign-in |

Still stuck: open an issue with the machine platform, the agent version
shown in the dashboard, and the error message (redact tokens and
hostnames).
