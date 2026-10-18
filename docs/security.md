# Security Model (User View)

- Bearer tokens (`nc_tok_…`, personal access tokens) authenticate API
  clients. The hub stores digests only, never plaintext, and redacts
  secrets from logs and support bundles.
- Devices prove every request with an Ed25519 device key enrolled
  out-of-band; replays and expired proofs are rejected.
- Host policy is fail-closed per machine: capabilities, file roots, and
  browser/egress rules default to deny until explicitly granted.
- Every admitted action is appended to a SHA-256 chained audit trail:
  each entry commits to its predecessor, so tampering is detectable and
  the record is exportable.
- High-risk classes of work — shell execution, file deletion, privileged
  execution — are rate-limited and should require human confirmation.
- Team members act under per-machine roles: Viewers inspect, Operators
  operate, Admins manage policy. No shared credentials.
- Updates install only staged releases whose hash matches the signed
  manifest and whose version is newer than the running one.
- Report vulnerabilities per [`SECURITY.md`](../SECURITY.md) — never as a
  public issue.
