# EdgeOne Manager Release Channel

Public self-update channel for **EdgeOne Manager** (server + web frontend).

- Stable manifest: https://api.github.com/repos/Akilaea/edgeone-manager-release/contents/latest.json?ref=main
- Raw mirror: https://raw.githubusercontent.com/Akilaea/edgeone-manager-release/main/latest.json
- Latest version: 1.0.10
- Package: `edgeone-manager-1.0.10.tar.gz` (SHA256 pinned in `latest.json`)
- Download: http://47.98.228.129:57494/releases/edgeone-manager-1.0.10.tar.gz

The manager checks this manifest at startup and every 6 hours. A newer version is downloaded, SHA256-verified, then applied by a root systemd path unit: `server/` and `web/dist` are replaced, `.env` and `data/` are preserved, production dependencies are reinstalled, and the service restarts. A failed build rolls back to the previous `server/` and `web/dist` automatically.

## 1.0.10
- Embedded TW_REG is now 2.0.2.
- `POST /reg` supports `continuous: true` and `duration`; the sandbox starts a detached batch loop and returns immediately.
- The manager sends one start request per container; no follow-up request is needed.
- Existing managed endpoints are lazily redeployed to 2.0.2 the first time they execute.

This channel updates the EdgeOne Manager application itself. TW_REG package updates remain in `Akilaea/edgeone-twreg-release`.
