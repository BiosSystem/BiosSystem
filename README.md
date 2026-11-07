# BiosSystem

I design and run production software and infrastructure tools: cloud platform engineering, high-throughput network telemetry, security-hardened web applications, and real-time operational monitoring. Mostly Python and TypeScript, with Go, Java and PowerShell where they fit.

[bios-system.net](https://bios-system.net) · [What changed recently](https://bios-system.net/changelog) · [Live status](https://bios-system.net/status)

## Active Products & Live Demos

| Project | Domain | Overview | Access |
|---|---|---|---|
| **[ApexShock](https://github.com/BiosSystem/ApexShock)** | Mobile Gaming | Top-down 3v3 sci-fi hero brawler on Godot 4.3 with Vulkan Mobile rendering. | [Download APK](https://github.com/BiosSystem/ApexShock/releases/latest) (Direct sideload) |
| **[Sniplink](https://bios-system.net)** | Web Services | URL shortener with real-time referrer, click, and geographic telemetry. Batch creation supported. | [bios-system.net](https://bios-system.net) (Free tier) |
| **[BetForge](https://betforge.bios-system.net)** | Sports & Gaming | White-label sports betting portal with live odds feeds, bet slips, and private leagues. | [Live Demo](https://betforge.bios-system.net) (No sign-in) |
| **[Steady](https://steady.bios-system.net)** | Network Diagnostics | Browser-based throughput, ping latency, and jitter measurement over WebSockets. | [steady.bios-system.net](https://steady.bios-system.net) (Instant test) |
| **[StreamHub](https://bios-system.net/streamhub)** | Media & Video | Multi-stream spectator console for up to eight Twitch, YouTube, and Kick feeds simultaneously. | [bios-system.net/streamhub](https://bios-system.net/streamhub) |
| **[Neon Arcade](https://github.com/BiosSystem/retro-game-replicas)** | Browser Gaming | 28 procedural arcade titles with zero external assets. Runs offline as a PWA. | [Play Online](https://github.com/BiosSystem/retro-game-replicas) (Open access) |
| **[StatZilla](https://bios-system.net)** | Telemetry | Mobile competitive rating history for Brawl Stars, Clash Royale, and Clash of Clans. | [bios-system.net](https://bios-system.net) |
| **[Telegram Store Bot](https://bios-system.net)** | E-Commerce | Self-hosted Telegram storefront with dynamic catalog, cart management, and inline checkout. | [Waitlist](https://bios-system.net) |

Accounts on bios-system.net are approved by hand. Sniplink, BetForge, Steady, and Neon Arcade work without one.

## Open Source & Public Releases

**[ApexShock](https://github.com/BiosSystem/ApexShock)** ![release](https://img.shields.io/github/v/release/BiosSystem/ApexShock?style=flat-square&label=)  
A fast-paced 3v3 sci-fi mobile hero arena brawler built for Android on Godot 4.3. Features 6 original Vanguard heroes, 4-tier skill system with Overdrive transformations, Vulkan Mobile rendering, and direct APK sideloading.

**[AuraTorrent](https://github.com/BiosSystem/AuraTorrent)** ![release](https://img.shields.io/github/v/release/BiosSystem/AuraTorrent?style=flat-square&label=)  
A web interface for qBittorrent with a bandwidth scheduler and a Telegram alert when a download finishes. Installs on a phone as an app. Vue 3, TypeScript, Vite. Fork of [VueTorrent](https://github.com/VueTorrent/VueTorrent).

**[Winnow](https://github.com/BiosSystem/Winnow)** ![release](https://img.shields.io/github/v/release/BiosSystem/Winnow?style=flat-square&label=)  
Removes bloat and telemetry from Windows 11. Backs up the registry first, rolls back a failed apply, and every change has an undo. PowerShell 5.1. Fork of [Raphire/Win11Debloat](https://github.com/Raphire/Win11Debloat).

**[Neon Arcade](https://github.com/BiosSystem/retro-game-replicas)** ![release](https://img.shields.io/github/v/release/BiosSystem/retro-game-replicas?style=flat-square&label=)  
28 original arcade games with procedural graphics and sound and no ROMs. Plays with a keyboard, touch or most controllers, works offline as a PWA, and has an optional desktop shell. TypeScript, Phaser 4, Vite, Tauri.

**[OriginalMS](https://github.com/BiosSystem/OriginalMS)** ![release](https://img.shields.io/github/v/release/BiosSystem/OriginalMS?style=flat-square&label=)  
A MapleStory v62 (GMS 2008) server: party quests, Zakum, Horntail and Papulatus, Cygnus Knights and Aran. Runs as a Docker Compose stack. Java 8, Apache MINA, MySQL. Based on OdinMS.

## How changes get made

- Every fix or feature starts as an issue and lands as a pull request that says what was run and what was not. For example, [AuraTorrent #127](https://github.com/BiosSystem/AuraTorrent/pull/127) patches a dependency CVE and re-runs all 372 tests before it merges.
- Dependencies are checked with CodeQL, GitHub dependency review and Trivy. Fixes go out as their own pull requests.
- Releases are tagged with notes, for example [Winnow v4.4.4](https://github.com/BiosSystem/Winnow/releases/tag/v4.4.4).
- Upstream projects are credited in each repository's `CREDITS.md`.

## Tools

Python, FastAPI, TypeScript, React, Vue, Go, Java, PowerShell, Docker, GitHub Actions, Terraform, Cloudflare, PostgreSQL, SQLite, Vitest, Playwright.

Security reports: see [SECURITY.md](SECURITY.md).
