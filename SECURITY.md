# Security Policy

This policy covers the public BiosSystem repositories: AuraTorrent, Winnow, OriginalMS and retro-game-replicas.

## Reporting a vulnerability

Please do not open a public issue for a security problem.

* **Where**: open a private report through GitHub Security Advisories on the affected repository (its Security tab, "Report a vulnerability"). If you are unsure which repository is affected, use [this one](https://github.com/BiosSystem/BiosSystem/security/advisories/new).
* **Acknowledgement**: within 24 hours.
* **Remediation plan**: within 3 business days.
* **Disclosure**: agreed with the reporter once the fix is released and verified.

## Fixes in public repositories

### AuraTorrent (qBittorrent WebUI)
*Forked from VueTorrent.*

* **Open redirect on login (`src/pages/Login.vue`)**: the upstream code passed `route.query.redirect` straight to `router.push()`, so a crafted link could send a signed-in user to another site. Redirects must now start with a single `/`; anything starting with `//` is rejected and falls back to the dashboard.
* **Credentials in the URL (`src/pages/Login.vue`)**: auto-login read `?username=...&password=...` from the query string, which ends up in browser history, proxy logs and `Referer` headers. That code is removed; credentials only go in the POST body.
* **Telegram bot allow-list (`bot/main.py`)**: every command handler checks the sender against `ALLOWED_USERS`; admin commands such as `/add_user` are limited to the owner (`OWNER_ID`, or the first allowed user if it is unset).
* **Dependencies**: CodeQL and dependency review run on every pull request; vulnerable packages are raised in their own pull requests.

### retro-game-replicas (Neon Arcade)

* **Tauri permissions (`src-tauri/capabilities/default.json`)**: the desktop shell is granted only Tauri's `core:default` set, and the only plugin is logging. There is no shell, filesystem or process access from the web view.
* **CRT shader bounds (`src/engine/graphics/CrtShaderPipeline.ts`)**: coordinates are clamped in the post-processing shader so bad values cannot cause out-of-bounds reads or crash the WebGL context.
