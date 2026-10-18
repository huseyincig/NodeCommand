# Clients (Hosts)

- Each enrolled machine is a **client** with an ID like `nc_<64 hex>`.
- The dashboard fleet view lists every machine with live status, platform,
  and role assignments.
- Host-targeting requests require an explicit machine ID; the platform
  never guesses a target.
- A client counts as **online** only while it holds a live authenticated
  session — stale records never report as ready.
- Team members see the machines they are granted, scoped by role
  (Viewer, Operator, or Admin).
- Remove a machine with *forget* (drops the hub record) or *uninstall*
  (cleans the device); see [`agent-installation.md`](agent-installation.md).
