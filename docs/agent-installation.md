# Agent Installation

Run the enrollment command from your dashboard (it embeds a one-time
enrollment token). Manual equivalents:

**Linux:**

```sh
curl -fsSL https://agent.nodecommand.app/install.sh | sudo -E sh -s -- <HOST_ID> <ENROLL_TOKEN>
```

**macOS:** same as Linux (runs as a launchd service).

**Windows (PowerShell, admin):**

```powershell
iwr -useb https://agent.nodecommand.app/install.ps1 -OutFile "$env:TEMP\nc.ps1"
powershell -ExecutionPolicy Bypass -File "$env:TEMP\nc.ps1" -HostId <HOST_ID> -Token <ENROLL_TOKEN>
```

**Uninstall:** see the `nc-agent` repo (`docs/UNINSTALL.md`) or the
dashboard device panel. Full source and service definitions are public.
