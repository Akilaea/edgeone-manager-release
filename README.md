# EdgeOne Manager Release Channel

Public self-update channel for **EdgeOne Manager** (server + web frontend).

- Stable manifest: https://api.github.com/repos/Akilaea/edgeone-manager-release/contents/latest.json?ref=main
- Raw mirror: https://raw.githubusercontent.com/Akilaea/edgeone-manager-release/main/latest.json
- Latest version: 1.0.5
- Package: `edgeone-manager-1.0.5.tar.gz` (SHA256 pinned in `latest.json`)
- Download: http://47.98.228.129:57494/releases/edgeone-manager-1.0.5.tar.gz

The manager checks this manifest at startup and every 6 hours. A newer version is downloaded, SHA256-verified, then applied by a root systemd path unit: `server/` and `web/dist` are replaced, `.env` and `data/` are preserved, production dependencies are reinstalled, and the service restarts. A failed build rolls back to the previous `server/` and `web/dist` automatically.

## 1.0.5
- “Available accounts” now counts every account that is neither used this cycle nor running, including accounts whose endpoints will be auto-configured on execution.
- The configured-endpoint hint uses a global count instead of the current page.

## 1.0.4
- TW_REG overview is paginated server-side (`page`, `pageSize`).
- Run creation responses are capped while still returning the batch count.
- Queue dequeue is O(1); endpoint counts are fetched in one batch.
- Cross-page selection is preserved while a new page loads.

This channel updates the EdgeOne Manager application itself. TW_REG package updates remain in `Akilaea/edgeone-twreg-release`.
