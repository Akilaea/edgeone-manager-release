# EdgeOne Manager Release Channel

Public self-update channel for **EdgeOne Manager** (server + web frontend).

- Stable manifest: https://api.github.com/repos/xbox-cn/edgeone-manager-release/contents/latest.json?ref=main
- Raw mirror: https://raw.githubusercontent.com/xbox-cn/edgeone-manager-release/main/latest.json
- Latest version: 1.0.12
- Package: `edgeone-manager-1.0.12.tar.gz` (SHA256 pinned in `latest.json`)
- Download: http://47.98.228.129:57494/releases/edgeone-manager-1.0.12.tar.gz

The manager checks this manifest at startup and every 6 hours. A newer version is downloaded, SHA256-verified, then applied by a root systemd path unit: `server/` and `web/dist` are replaced, `.env` and `data/` are preserved, production dependencies are reinstalled, and the service restarts. A failed build rolls back to the previous `server/` and `web/dist` automatically.

## 1.0.12
- Added an automation log page with pagination, status/trigger filters, search, and 24-hour statistics.
- Replaced the old liveness-settings nav entry; scheduler settings now live under Automation → Scheduler settings.
- Navigation regrouped into Assets, Automation, System, and Developer.

This channel updates the EdgeOne Manager application itself. TW_REG package updates remain in `xbox-cn/edgeone-twreg-release`.
