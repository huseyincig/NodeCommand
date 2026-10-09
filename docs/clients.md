# Clients (Hosts)

- Each enrolled machine is a **client** with an ID like `nc_<64 hex>`.
- List your clients in the dashboard fleet view.
- Host-targeting tools require explicit `client_id`; the platform never
  guesses a host.
- A client shows `online` only with a live authenticated session; stale
  rows never count as ready.
- Remove a machine with forget (hub record) or uninstall (device cleanup).
