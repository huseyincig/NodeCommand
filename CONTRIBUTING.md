# Contributing

This repository holds the public product surface: documentation, examples,
and manifests. Code lives in two sibling repositories:

- [nc-agent](https://github.com/huseyincig/nc-agent) — the host agent and
  CLI installer.
- [nc-protocol](https://github.com/huseyincig/nc-protocol) — the wire
  contracts and MCP tool schemas.

Guidelines:

- Keep examples token-free (placeholders only), with no internal URLs and
  no customer data.
- Keep documentation version-agnostic: no pinned versions and no internal
  surface references — link to the canonical contract instead of restating
  it.
- Docs changes should stay consistent with the pinned contract in
  [nc-protocol](https://github.com/huseyincig/nc-protocol).

Open issues and pull requests against the repository that owns the change.
