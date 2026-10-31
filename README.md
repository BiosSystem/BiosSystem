# BiosSystem

I write and run small products that people use every day: a link shortener with click analytics, a live odds board for sports and esports, a MapleStory v62 server people still log into, and the tooling that keeps all of it up and patched. Mostly Python and TypeScript, with Go, Java and PowerShell where they fit.

[bios-system.net](https://bios-system.net) · [What changed recently](https://bios-system.net/changelog) · [Live status](https://bios-system.net/status)

## Products you can try

- **Sniplink**: short links with click analytics, referrers and geo breakdowns. Paste a whole list of links at once. [Try it](https://bios-system.net), 5 links free, no sign-in.
- **BetForge**: a white-label betting portal with live odds for football, basketball and esports, bet slips and private group play. [15-second demo](https://betforge.bios-system.net), no money, no account.
- **Steady**: download, upload, latency and jitter, measured in the browser in about twenty seconds. [steady.bios-system.net](https://steady.bios-system.net), no account.
- **StreamHub**: up to eight Twitch, YouTube and Kick streams on one screen, with saved layouts. [Free plan](https://bios-system.net/streamhub).
- **StatZilla**: rating history for Brawl Stars, Clash Royale and Clash of Clans player tags. Free plan on bios-system.net.
- **Telegram Store Bot**: a storefront inside Telegram, with catalog, cart and checkout through inline buttons. Waitlist on bios-system.net.

Accounts on bios-system.net are approved by hand. Sniplink, BetForge and Steady work without one.

## Open source

**[AuraTorrent](https://github.com/BiosSystem/AuraTorrent)** ![release](https://img.shields.io/github/v/release/BiosSystem/AuraTorrent?style=flat-square&label=)
A web interface for qBittorrent with a bandwidth scheduler and a Telegram alert when a download finishes. Installs on a phone as an app. Vue 3, TypeScript, Vite. Fork of [VueTorrent](https://github.com/VueTorrent/VueTorrent).

**[Winnow](https://github.com/BiosSystem/Winnow)** ![release](https://img.shields.io/github/v/release/BiosSystem/Winnow?style=flat-square&label=)
Removes bloat and telemetry from Windows 11. Backs up the registry first, rolls back a failed apply, and every change has an undo. PowerShell 5.1. Fork of [Raphire/Win11Debloat](https://github.com/Raphire/Win11Debloat).

**[OriginalMS](https://github.com/BiosSystem/OriginalMS)** ![release](https://img.shields.io/github/v/release/BiosSystem/OriginalMS?style=flat-square&label=)
A MapleStory v62 (GMS 2008) server: party quests, Zakum, Horntail and Papulatus, Cygnus Knights and Aran. Runs as a Docker Compose stack. Java 8, Apache MINA, MySQL. Based on OdinMS.

**[Neon Arcade](https://github.com/BiosSystem/retro-game-replicas)** ![release](https://img.shields.io/github/v/release/BiosSystem/retro-game-replicas?style=flat-square&label=)
28 original arcade games with procedural graphics and sound and no ROMs. Plays with a keyboard, touch or most controllers, works offline as a PWA, and has an optional desktop shell. TypeScript, Phaser 4, Vite, Tauri.

## How changes get made

- Every fix or feature starts as an issue and lands as a pull request that says what was run and what was not. For example, [AuraTorrent #127](https://github.com/BiosSystem/AuraTorrent/pull/127) patches a dependency CVE and re-runs all 372 tests before it merges.
- Dependencies are checked with CodeQL, GitHub dependency review and Trivy. Fixes go out as their own pull requests.
- Releases are tagged with notes, for example [Winnow v4.4.4](https://github.com/BiosSystem/Winnow/releases/tag/v4.4.4).
- Upstream projects are credited in each repository's `CREDITS.md`.

## Tools

Python, FastAPI, TypeScript, React, Vue, Go, Java, PowerShell, Docker, GitHub Actions, Terraform, Cloudflare, PostgreSQL, SQLite, Vitest, Playwright.

Security reports: see [SECURITY.md](SECURITY.md).
