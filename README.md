<div align="center">
  <img src="assets/header.svg" alt="BiosSystem" width="100%" />
</div>

<h1 align="center">BiosSystem</h1>

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Share+Tech+Mono&weight=700&size=20&duration=2500&pause=1000&color=00FF72&center=true&vCenter=true&width=750&lines=Systems+Engineering+%7C+Full-Stack+Web+Applications;Real-Time+Gaming+Telemetry+%7C+Network+Engines;Desktop+Tooling+%7C+Tauri+v2+%7C+PowerShell+Core;Security-Hardened+GitOps+%26+Cloud+Infrastructure" alt="BiosSystem Specializations" />
</p>

<p align="center">
  <strong>Systems Engineering | Full-Stack Applications | Security Architecture | DevOps</strong>
</p>

<br>

<div align="center">

### Core Technologies & Toolchain

| Domain | Stack & Ecosystem |
|---|---|
| **Core Languages** | ![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white) ![Python](https://img.shields.io/badge/Python-14354C?style=flat-square&logo=python&logoColor=white) ![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white) ![Rust](https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white) ![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=java&logoColor=white) ![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-336791?style=flat-square&logo=postgresql&logoColor=white) |
| **Frontend & UI** | ![React 19](https://img.shields.io/badge/React_19-20232A?style=flat-square&logo=react&logoColor=61DAFB) ![Vue.js 3](https://img.shields.io/badge/Vue.js_3-35495E?style=flat-square&logo=vue.js&logoColor=4FC08D) ![Next.js 15](https://img.shields.io/badge/Next.js_15-000000?style=flat-square&logo=nextdotjs&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white) ![Tailwind](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white) ![Tauri v2](https://img.shields.io/badge/Tauri_v2-24C8DB?style=flat-square&logo=tauri&logoColor=white) |
| **Backend & APIs** | ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=flat-square&logo=nestjs&logoColor=white) ![Apache MINA](https://img.shields.io/badge/Apache_MINA-D22128?style=flat-square&logo=apache&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white) |
| **Cloud & DevOps** | ![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=flat-square&logo=docker&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326ce5?style=flat-square&logo=kubernetes&logoColor=white) ![Terraform](https://img.shields.io/badge/Terraform-5835CC?style=flat-square&logo=terraform&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazon-aws&logoColor=white) ![GitOps](https://img.shields.io/badge/GitOps-00FF72?style=flat-square&logo=git&logoColor=black) |

</div>

<br>

## Architecture & System Topology

```mermaid
flowchart TD
    subgraph ClientLayer["Client & Desktop Tier"]
        Aura["AuraTorrent (Vue 3 PWA)"]
        Arcade["retro-game-replicas (Tauri v2 + Phaser 3)"]
        Winnow["Winnow (PowerShell + WPF CLI)"]
        Therm["Therm Studio (USB Cooler LCD Suite)"]
        StatZilla["StatZilla (React 19 Gaming Telemetry)"]
    end

    subgraph ServiceLayer["Application & Telemetry Tier"]
        Steady["Steady (Network Throughput & Latency Engine)"]
        Sniplink["Sniplink (Privacy URL Shortener & Analytics)"]
        OmniToken["OmniToken Suite (Protobuf Ingestion & Governance)"]
        BetForge["BetForge (Sports Odds & In-Play Simulation)"]
        Tracker["TorrentsTracker (NestJS Tracker Daemon)"]
        Stealth["StealthMatrix (Telegram Stars Storefront)"]
    end

    subgraph CoreLayer["Emulation & Spatial Tier"]
        OrigMS["OriginalMS (MapleStory v62 - MINA + MySQL)"]
        Outbreak["OutbreakRP (FiveM Multiplayer Framework)"]
        Globe["God's Eye View (3D Geospatial Engine)"]
    end

    subgraph InfraLayer["Infrastructure & Security Tier"]
        K8s["k8s-app-delivery (Kubernetes GitOps + Trivy)"]
        AWS["terraform-aws-bootstrap (VPC + EC2 + S3 IaC)"]
        Docker["Docker Multi-Stage Containerization"]
    end

    ClientLayer --> ServiceLayer
    ServiceLayer --> InfraLayer
    CoreLayer --> InfraLayer
```

<br>

---

## Open-Source Public Projects

These repositories are open-source and publicly accessible on GitHub:

### [AuraTorrent](https://github.com/BiosSystem/AuraTorrent)
![Type](https://img.shields.io/badge/Type-Public_OSS-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Vue_3_%7C_Vite_%7C_Pinia_%7C_TypeScript-blue?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-PWA_%7C_Web-orange?style=flat-square)

A lightweight, responsive Vue 3 Progressive Web Application (PWA) designed as a comprehensive alternative WebUI for qBittorrent.
- **Drag-and-Drop RSS**: Full feed hierarchy management with custom regex rule filtering.
- **Telegram Bot Integration**: Instant alerts pushed directly on torrent download completion.
- **Multi-Server Switcher**: Real-time management across multiple remote daemon instances with persistent local preferences.
- **Security Hardened**: Clamped route redirection guards, origin isolation, and zero query-string credential persistence.

---

### [Winnow](https://github.com/BiosSystem/Winnow)
![Type](https://img.shields.io/badge/Type-Public_OSS-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-PowerShell_%7C_WPF_%7C_Windows_Sandbox-blue?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Windows_10_%2F_11-orange?style=flat-square)

A modular PowerShell debloat, privacy enforcement, and setup optimization toolkit for Windows 10 and 11.
- **Audit Mode Support**: Dry-run verification reports changes before system execution.
- **Granular Feature Toggles**: Selective removal of telemetry, consumer bloat, and unwanted background scheduled tasks.
- **Zero Runtime Residue**: Portable JSON profile export and import with zero external binary dependencies.

---

### [retro-game-replicas](https://github.com/BiosSystem/retro-game-replicas)
![Type](https://img.shields.io/badge/Type-Public_OSS-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Tauri_v2_%7C_Phaser_3_%7C_TypeScript_%7C_Rust-blue?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Desktop_App-orange?style=flat-square)

BiosSystem Neon Arcade: a cross-platform desktop arcade launcher and recreation engine.
- **11 Bundled Arcade Classics**: Full recreations optimized for responsive input and 60 FPS rendering.
- **GLSL CRT PostFX Shaders**: Authentically simulated scanlines, shadow masks, curvature, and phosphor glow with bounds clamping.
- **Native Gamepad API**: Local co-op multiplayer support via HTML5 Gamepad API.
- **Local Persistence**: Secure high-score tracking and achievement unlocks via isolated local state.

---

### [OriginalMS](https://github.com/BiosSystem/OriginalMS)
![Type](https://img.shields.io/badge/Type-Public_OSS-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Java_8_%7C_Apache_MINA_%7C_MySQL_%7C_Docker-blue?style=flat-square)
![Platform](https://img.shields.io/badge/Platform-Server_Emulator-orange?style=flat-square)

A full-fidelity MapleStory v62 (GMS 2008) server emulator running over Apache MINA network sockets.
- **Complete Content Coverage**: Scripted party quests (KPQ, LPQ, OPQ, CWKPQ), boss instances (Zakum, Horntail, Pink Bean), Cygnus Knights, and Aran classes.
- **Containerized Architecture**: Packaged in Docker Compose with auto-importing MySQL database initialization for one-command deployment.
- **High-Throughput Sockets**: Non-blocking asynchronous I/O handling channel, world, and login network traffic.

<br>

---

## Featured Engineering Portfolio

Comprehensive applications, telemetry engines, and specialized platforms engineered across the software stack:

### Gaming Telemetry & Desktop Systems

#### StatZilla
![Domain](https://img.shields.io/badge/Domain-Gaming_Telemetry-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-React_19_%7C_TypeScript_%7C_Vite_%7C_Tailwind-blue?style=flat-square)

High-performance mobile gaming statistics tracker and live player analytics PWA.
- **Direct Official APIs**: Instantaneous player statistics, win rates, and battle logs straight from official Supercell developer endpoints.
- **Multi-Game Aggregation**: Unified tracking across Brawl Stars, Clash Royale, and PUBG Mobile.
- **Competitive Metrics**: Real-time trophy tracking, win/loss ratio graphs, and historical leaderboard indexing.

#### Therm Studio (Cpu-LCD-Therm)
![Domain](https://img.shields.io/badge/Domain-Hardware_Desktop-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-TypeScript_%7C_Electron_%7C_Hardware_APIs-blue?style=flat-square)

A local-first creator suite and hardware telemetry engine for USB CPU-cooler LCD panels (320x320).
- **Custom Display Canvas**: Converts cooler panels into real-time sensor dashboards, layered media canvases, and system gauges.
- **Zero Vendor Bloat**: Operates independently without keeping proprietary heavy vendor suites open.
- **Hardware Telemetry**: Direct sensor readings for temperatures, fan speeds, clock frequencies, and load graphs.

#### OutbreakRP
![Domain](https://img.shields.io/badge/Domain-Multiplayer_Modding-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Lua_%7C_TypeScript_%7C_FiveM_FXServer-blue?style=flat-square)

Post-apocalyptic multiplayer zombie survival roleplay framework engineered for GTA V FiveM.
- **Dynamic Infection Mechanics**: Custom health, hunger, stamina, infection progression, and medical treatment loops.
- **Modular Factions**: Territory control, safehouse construction, dynamic loot economy, and barter markets.

---

### Network Tooling & Web Services

#### Steady (SpeedTest)
![Domain](https://img.shields.io/badge/Domain-Network_Tooling-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-React_19_%7C_FastAPI_%7C_SQLite_WAL_%7C_Docker-blue?style=flat-square)

Standalone self-hosted network performance and bandwidth measurement service.
- **Zero Third-Party Dependency**: Pure internal benchmarking engine without third-party speedtest API rate limits.
- **Granular Metrics**: Measures download/upload throughput, ping, jitter, loaded latency, tail latency, and UDP packet loss.
- **Automated Scheduling**: Scheduled measurement daemons storing time-series telemetry in SQLite WAL mode.

#### Sniplink
![Domain](https://img.shields.io/badge/Domain-Web_Service-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-React_19_%7C_FastAPI_%7C_SQLAlchemy-blue?style=flat-square)

Privacy-first URL shortening and link management service.
- **Custom Routing**: Custom alias creation, link expiration rules, and password-protected redirects.
- **Telemetry & Analytics**: Real-time click counter, referer breakdown, and geographical distribution.
- **Abuse Prevention**: Sliding-window rate limiting, origin verification, and bot detection filters.

#### TorrentsTracker
![Domain](https://img.shields.io/badge/Domain-BitTorrent_Infra-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-NestJS_%7C_Next.js_%7C_PostgreSQL_%7C_Prisma-blue?style=flat-square)

Private invite-based BitTorrent tracker platform with an end-to-end TypeScript architecture.
- **High-Performance Tracker**: Dedicated NestJS announce and scrape daemon handling concurrent peer swarms.
- **Modern Catalog UI**: Next.js App Router member portal with category browsing, peer tables, and ratio enforcement.

---

### AI Governance & Specialized Platforms

#### OmniToken Suite
![Domain](https://img.shields.io/badge/Domain-AI_Governance-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Next.js_15_%7C_Python_3.12_%7C_Tailwind-blue?style=flat-square)

Multi-agent AI token metering, protobuf telemetry decoding, and cost governance suite.
- **Offline Ingestion Engine (`omni-token-telemetry`)**: Decodes protobuf and wire logs, executing monotonic high-water ratchets.
- **Analytics Dashboard (`tokens-dashboard`)**: Next.js 15 App Router executive dashboard for real-time model token consumption and ROI reporting.

#### BetForge
![Domain](https://img.shields.io/badge/Domain-Sports_Analytics-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-React_18_%7C_TypeScript_%7C_Vite_%7C_Tailwind-blue?style=flat-square)

Sports analytics platform and dynamic odds computation sandbox.
- **In-Play Market Pricing**: Real-time odds conversion across decimal, American, and fractional representations.
- **Interactive Bet Slip**: Dynamic bet accumulation, payout multipliers, cash-out workflows, and live model simulation.

#### God's Eye View
![Domain](https://img.shields.io/badge/Domain-Geospatial_3D-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-TypeScript_%7C_Cesium_%7C_Three.js_%7C_WebGL-blue?style=flat-square)

Interactive 3D geospatial intelligence platform rendering real-time spatial telemetry on a photorealistic digital globe.
- **Live Entity Tracking**: Simultaneous visualization of orbital satellites, commercial aviation, maritime vessels, and seismic events.
- **Tactical HUD**: WebGL-powered telemetry HUD with coordinates, altitude, velocity, and trajectory vectors.

#### StealthMatrix
![Domain](https://img.shields.io/badge/Domain-E_Commerce-00FF72?style=flat-square)
![Stack](https://img.shields.io/badge/Stack-Python_3.11_%7C_Aiogram_3.7_%7C_SQLite-blue?style=flat-square)

Self-hosted Telegram e-commerce storefront bot.
- **Telegram Stars Payments**: In-app digital payments integration with invoice validation and order fulfillment.
- **Security Middlewares**: Sliding-window rate limiting, input sanitization against HTML injection, and parameterized queries.

---

### Cloud Infrastructure & Security Sandboxes

- **terraform-aws-bootstrap**: Modular, secure-by-default AWS infrastructure deploying an isolated VPC across two AZs, a private-subnet EC2 instance accessible strictly via SSM Session Manager, and an encrypted S3 bucket with Checkov and TFLint validation.
- **k8s-app-delivery**: Production-grade Kubernetes GitOps application delivery sandbox with multi-stage Docker builds, liveness/readiness probes, and Trivy static security scanning in CI.

<br>

---

## Active Projects Overview

| Project | Domain | Stack | Delivery & Highlights |
|---|---|---|---|
| [AuraTorrent](https://github.com/BiosSystem/AuraTorrent) | Web Application | Vue 3, Vite, Pinia, TypeScript | Public OSS - PWA replacement WebUI for qBittorrent with Telegram finish alerts |
| [Winnow](https://github.com/BiosSystem/Winnow) | System Utility | PowerShell, WPF | Public OSS - Windows debloat and setup toolkit with audit mode and JSON profiles |
| [retro-game-replicas](https://github.com/BiosSystem/retro-game-replicas) | Desktop Gaming | Tauri v2, Phaser 3, TypeScript, Rust | Public OSS - Desktop arcade launcher with 11 games, CRT shaders, and gamepad API |
| [OriginalMS](https://github.com/BiosSystem/OriginalMS) | Game Server | Java 8, Apache MINA, MySQL, Docker | Public OSS - MapleStory v62 server emulator with all PQs, bosses, and jobs working |
| StatZilla | Gaming Telemetry | React 19, TypeScript, Supercell APIs | Mobile game player stats and live battle analytics for top mobile titles |
| Steady | Network Tooling | React 19, FastAPI, SQLite, Docker | Self-hosted network performance, latency, and throughput testing suite |
| Sniplink | Web Service | React 19, FastAPI, SQLAlchemy | Secure URL shortener with custom slugs, link expiration, and telemetry |
| OmniToken Suite | AI Governance | Next.js 15, Python 3.12, TypeScript | AI token telemetry, protobuf decoding, and cost governance dashboard |
| Therm Studio | Desktop Hardware | TypeScript, Electron, Hardware APIs | Local-first USB CPU-cooler LCD dashboard and creator suite |
| BetForge | Sports Analytics | React 18, TypeScript, Vite | Sports betting odds display, bet slip manager, and cash-out flow |
| God's Eye View | Geospatial 3D | TypeScript, Cesium, Three.js, WebGL | Photorealistic 3D globe with live satellite, air, and maritime tracking |
| StealthMatrix | E-Commerce | Python 3.11, Aiogram 3.7, SQLite | Telegram store bot with Telegram Stars payments and order management |
| TorrentsTracker | BitTorrent Infra | NestJS, Next.js, PostgreSQL, Prisma | Private BitTorrent tracker platform with announce/scrape daemon |
| OutbreakRP | Multiplayer Modding | Lua, TypeScript, FiveM FXServer | GTA V zombie apocalypse roleplay server framework with loot economy |
| Cloud DevOps Sandboxes | Cloud & GitOps | Terraform, Kubernetes, AWS, Docker | Secure AWS VPC/EC2/S3 IaC and Kubernetes GitOps delivery pipelines |

<br>

> Detailed architecture specifications, hardening models, and security protocols: [**WIKI.md**](docs/WIKI.md)

<br>

---

## GitHub Activity & Statistics

<p align="center">
  <a href="https://github.com/BiosSystem">
    <img src="https://github-readme-stats-eight-theta.vercel.app/api?username=BiosSystem&show_icons=true&title_color=00FF72&icon_color=00FF72&text_color=a1a1aa&bg_color=0D1117&border_color=30363d&hide_border=true" alt="BiosSystem GitHub Stats" />
  </a>
  <a href="https://github.com/BiosSystem">
    <img src="https://streak-stats.demolab.com/?user=BiosSystem&theme=dark&background=0D1117&border=30363d&stroke=00FF72&ring=00FF72&fire=00FF72&currStreakLabel=00FF72&currStreakNum=00FF72&sideNums=a1a1aa&sideLabels=a1a1aa&dates=a1a1aa&hide_border=true" alt="BiosSystem GitHub Streak" />
  </a>
</p>

<p align="center">
  <a href="https://github.com/BiosSystem">
    <img src="https://github-readme-stats-eight-theta.vercel.app/api/top-langs/?username=BiosSystem&layout=compact&title_color=00FF72&text_color=a1a1aa&bg_color=0D1117&border_color=30363d&hide_border=true" alt="BiosSystem Top Languages" />
  </a>
</p>

<br>

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=BiosSystem&color=00FF72&style=for-the-badge&label=PROFILE+VIEWS" alt="Profile Views" />
</div>