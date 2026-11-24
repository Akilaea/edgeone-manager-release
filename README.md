# EdgeOne Manager Release Channel

Public self-update channel for **EdgeOne Manager** (server + web frontend).

- Stable manifest: https://api.github.com/repos/Akilaea/edgeone-manager-release/contents/latest.json?ref=main
- Raw mirror: https://raw.githubusercontent.com/Akilaea/edgeone-manager-release/main/latest.json
- Latest version: 1.0.9
- Package: `edgeone-manager-1.0.9.tar.gz` (SHA256 pinned in `latest.json`)
- Download: http://47.98.228.129:57494/releases/edgeone-manager-1.0.9.tar.gz

The manager checks this manifest at startup and every 6 hours. A newer version is downloaded, SHA256-verified, then applied by a root systemd path unit: `server/` and `web/dist` are replaced, `.env` and `data/` are preserved, production dependencies are reinstalled, and the service restarts. A failed build rolls back to the previous `server/` and `web/dist` automatically.

## 1.0.9
- Quick-start default is 60 accounts per worker with batches up to 1500 seconds.
- A 3400-second container session now uses roughly 2–3 HTTP requests instead of many short 300-second batches.
- Batches remain sequential and never overlap inside one container; results are not polled.

## 1.0.8
- Sandboxes stay busy with sequential batches until the execution window ends.

This channel updates the EdgeOne Manager application itself. TW_REG package updates remain in `Akilaea/edgeone-twreg-release`.
