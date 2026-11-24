# EdgeOne Manager Release Channel

Public self-update channel for **EdgeOne Manager** (server + web frontend).

- Stable manifest: https://api.github.com/repos/Akilaea/edgeone-manager-release/contents/latest.json?ref=main
- Raw mirror: https://raw.githubusercontent.com/Akilaea/edgeone-manager-release/main/latest.json
- Latest version: 1.0.6
- Package: `edgeone-manager-1.0.6.tar.gz` (SHA256 pinned in `latest.json`)
- Download: http://47.98.228.129:57494/releases/edgeone-manager-1.0.6.tar.gz

The manager checks this manifest at startup and every 6 hours. A newer version is downloaded, SHA256-verified, then applied by a root systemd path unit: `server/` and `web/dist` are replaced, `.env` and `data/` are preserved, production dependencies are reinstalled, and the service restarts. A failed build rolls back to the previous `server/` and `web/dist` automatically.

## 1.0.6
- Removed registration/upload/vCPU totals that are not produced in start-only mode.
- Removed the manual pre-configuration entry points from TW_REG; endpoints are configured on execution.
- Account table now shows latest execution status instead of registration/upload usage.
- Run details and active-run cards adapt to start-only runs.

## 1.0.5
- “Available accounts” matches the set selected by “select all unrun”.
- The configured-endpoint hint uses a global count.

This channel updates the EdgeOne Manager application itself. TW_REG package updates remain in `Akilaea/edgeone-twreg-release`.
