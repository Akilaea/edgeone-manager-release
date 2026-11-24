# EdgeOne Manager Release Channel

Public self-update channel for **EdgeOne Manager** (server + web frontend).

- Stable manifest: https://api.github.com/repos/Akilaea/edgeone-manager-release/contents/latest.json?ref=main
- Raw mirror: https://raw.githubusercontent.com/Akilaea/edgeone-manager-release/main/latest.json
- Latest version: 1.0.3
- Package: `edgeone-manager-1.0.3.tar.gz` (SHA256 pinned in `latest.json`)
- Download: http://47.98.228.129:57494/releases/edgeone-manager-1.0.3.tar.gz

The manager checks this manifest at startup and every 6 hours. A newer version is downloaded, SHA256-verified, then applied by a root systemd path unit: `server/` and `web/dist` are replaced, `.env` and `data/` are preserved, production dependencies are reinstalled, and the service restarts. A failed build rolls back to the previous `server/` and `web/dist` automatically.

## 1.0.3
- TW_REG accounts are paginated (20/50/100 per page) with cross-page selection preserved.
- One-click select-all covers all pages; a separate button selects all unrun accounts.
- The execution panel and execution results now sit side by side; the result table is compact.

## 1.0.2
- TW_REG execution is start-oriented: endpoint auto-configuration happens on execution, then containers start.
- A started container is recorded as a successful execution.
- Import no longer pre-configures endpoints.

This channel updates the EdgeOne Manager application itself. TW_REG package updates remain in `Akilaea/edgeone-twreg-release`.
