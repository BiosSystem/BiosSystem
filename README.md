<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=00FF72&height=200&section=header&text=BiosSystem&fontSize=70&fontAlignY=35&desc=Security-Hardened%20Software%20%26%20Infrastructure&descAlignY=55&descAlign=50" alt="BiosSystem Header" />
</div>

<h1 align="center">BiosSystem</h1>

<p align="center">
  <strong>🌐 <a href="https://bios-system.net">bios-system.net</a></strong>
</p>

<p align="center">
  <strong>Systems Engineering | Security Architecture | DevOps</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vue.js&logoColor=4FC08D" alt="Vue.js" />
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React" />
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white" alt="Rust" />
  <img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Go" />
  <br>
  <img src="https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Kubernetes-326ce5?style=for-the-badge&logo=kubernetes&logoColor=white" alt="Kubernetes" />
  <img src="https://img.shields.io/badge/Terraform-5835CC?style=for-the-badge&logo=terraform&logoColor=white" alt="Terraform" />
  <img src="https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white" alt="FastAPI" />
</p>

<br>

## What I Build

Full-stack systems from the NAS up. The production stack at [bios-system.net](https://bios-system.net) runs a React 19 + FastAPI portal behind a Cloudflare tunnel with a 7-layer middleware chain (origin shield, GeoIP, CORS, CSP, anti-scraper, rate limiter, CSRF), non-root Docker containers, Litestream WAL replication to R2, and DNSSEC signed end-to-end. The CI pipeline gates every push on Bandit, Semgrep, OWASP Dependency Check, npm audit, and pip-audit before anything reaches production.

The public repos cover different slices of that same discipline: a Vue 3 PWA that replaces the qBittorrent web UI ([AuraTorrent](https://github.com/BiosSystem/AuraTorrent)), a Tauri v2 desktop launcher for 11 arcade games with GLSL CRT shaders and hardware gamepad support ([retro-game-replicas](https://github.com/BiosSystem/retro-game-replicas)), a Dockerized 2008 MapleStory emulator with every PQ and boss route working ([OriginalMS](https://github.com/BiosSystem/OriginalMS)), a Telegram Stars e-commerce bot with order tracking and a real admin panel ([stealth-matrix](https://github.com/BiosSystem/stealth-matrix)), and a Go gateway exposing a custom API layer for a self-hosted NAS ([aura-os](https://github.com/BiosSystem/aura-os)).

Infrastructure work lives in [universal-platform-engineering](https://github.com/BiosSystem/universal-platform-engineering) (Kustomize + ArgoCD GitOps delivery) and [terraform-aws-bootstrap](https://github.com/BiosSystem/terraform-aws-bootstrap) (VPC + EC2 + S3 with Checkov and TFLint gating).

> 📚 Architecture detail, security hardening matrix, and deployment contracts: [**WIKI.md**](docs/WIKI.md)

## Active Public Projects

| Project | Stack | Description |
|---|---|---|
| [AuraTorrent](https://github.com/BiosSystem/AuraTorrent) | Vue 3, Vite, Pinia, SCSS | PWA replacement web UI for qBittorrent with Telegram finish alerts |
| [retro-game-replicas](https://github.com/BiosSystem/retro-game-replicas) | TypeScript, Phaser 3, Tauri v2 | Desktop arcade launcher - 11 games, GLSL CRT shaders, gamepad API |
| [OriginalMS](https://github.com/BiosSystem/OriginalMS) | Java, Apache MINA, MySQL, Docker | MapleStory v62 server emulator - all PQs, bosses, and jobs working |
| [stealth-matrix](https://github.com/BiosSystem/stealth-matrix) | Python, Aiogram 3, SQLite | Telegram Stars e-commerce bot with order tracking and admin dashboard |
| [aura-os](https://github.com/BiosSystem/aura-os) | Go, Echo, SQLite | NAS OS gateway with Docker virtualization and ZFS pool management |
| [WinSwift](https://github.com/BiosSystem/WinSwift) | PowerShell | Windows debloat and setup toolkit with audit mode and exportable profiles |
| [universal-platform-engineering](https://github.com/BiosSystem/universal-platform-engineering) | Kustomize, ArgoCD, Terraform | GitOps delivery layer for BiosSystem infrastructure |
| [terraform-aws-bootstrap](https://github.com/BiosSystem/terraform-aws-bootstrap) | Terraform, Checkov, TFLint | Modular AWS VPC/EC2/S3 bootstrap with static analysis gating |

## GitHub Stats

<p align="center">
  <a href="https://github.com/BiosSystem">
    <img src="https://github-readme-stats-eight-theta.vercel.app/api?username=BiosSystem&show_icons=true&title_color=00FF72&icon_color=00FF72&text_color=a1a1aa&bg_color=0D1117&border_color=30363d&hide_border=true" alt="BiosSystem GitHub Stats" />
  </a>
  <a href="https://github.com/BiosSystem">
    <img src="https://github-readme-stats-eight-theta.vercel.app/api/top-langs/?username=BiosSystem&layout=compact&title_color=00FF72&text_color=a1a1aa&bg_color=0D1117&border_color=30363d&hide_border=true" alt="BiosSystem Top Languages" />
  </a>
</p>

<br>

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=BiosSystem&color=00FF72&style=for-the-badge&label=PROFILE+VIEWS" alt="Profile Views" />
</div>