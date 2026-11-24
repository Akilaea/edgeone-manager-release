# EdgeOne Manager Release Channel

Public self-update channel for **EdgeOne Manager** (server + web frontend).

- Stable manifest: https://api.github.com/repos/xbox-cn/edgeone-manager-release/contents/latest.json?ref=main
- Raw mirror: https://raw.githubusercontent.com/xbox-cn/edgeone-manager-release/main/latest.json
- Latest version: 1.0.15
- Package: `edgeone-manager-1.0.15.tar.gz` (SHA256 pinned in `latest.json`)
- Download: http://47.98.228.129:57494/releases/edgeone-manager-1.0.15.tar.gz

The manager checks this manifest at startup and every 6 hours. A newer version is downloaded, SHA256-verified, then applied by a root systemd path unit: `server/` and `web/dist` are replaced, `.env` and `data/` are preserved, production dependencies are reinstalled, and the service restarts. A failed build rolls back to the previous `server/` and `web/dist` automatically.

## 1.0.15
- Dashboard page renamed to “仪表盘”.
- Its navigation group is now “概览”.
- “TW_REG” renamed to “Twitch注册机” and moved into the Automation group.

This channel updates the EdgeOne Manager application itself. TW_REG package updates remain in `xbox-cn/edgeone-twreg-release`.
