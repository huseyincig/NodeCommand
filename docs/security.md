# Security Model (User View)

- Bearer tokens (`nc_tok_…`) authenticate devices and API clients. The hub
  stores digests only, never plaintext.
- Devices prove every request with an Ed25519 device key enrolled
  out-of-band; replays and expired proofs are rejected.
- Host policy is fail-closed per machine: capabilities, file roots, and
  browser/egress rules default to deny.
- High-risk tools (`shell_exec`, `file_delete`, privileged execution) are
  rate-limited and should be human-confirmed.
- Updates install only staged releases whose hash matches the signed
  manifest and whose version is newer.
- Report vulnerabilities per `SECURITY.md` — never as public issues.
