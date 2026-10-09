# Troubleshooting

| Symptom | Check |
|---|---|
| Client stays offline | Agent service running? Clock in sync? Re-enroll if keys rotated |
| `CLIENT_NOT_FOUND` | Wrong `client_id`, or host belongs to another workspace |
| `HOST_POLICY_DENIED` | Capability not granted for this host profile |
| Update stuck | Dashboard job status; agent rolls back automatically on bad activation |
| 429 rate limited | High-risk tools are throttled; space out calls |

Still stuck: open an issue with client platform, agent version, and the
job error (redact tokens and hostnames).
