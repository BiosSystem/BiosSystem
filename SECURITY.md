# BiosSystem Global Security Policy & Hardening Matrix

Security is a primary design requirement across the entire BiosSystem portfolio of projects, covering WebUI frontends, retro arcade emulation platforms, NAS operating systems, secure Telegram-based e-commerce automation, and cloud GitOps orchestration pipelines.

This document serves as the central security policy and hardening matrix for all repositories hosted under the `BiosSystem` organization/user profile.

---

## 📞 Reporting a Vulnerability

If you discover a security vulnerability in any BiosSystem project, please report it immediately. To protect our users and infrastructure, **do not open public issues on GitHub**.

* **Email**: Send detailed vulnerability reports to `security@bios_system.io`
* **Response SLA**:
  * **Acknowledgement**: Within 24 hours.
  * **Remediation Plan**: Within 3 business days.
  * **Disclosure**: Coordinated with the reporter after patches are deployed and verified.

---

## 🔒 Security Architectures & Fixes Matrix

Below is the consolidated history of security audits, hardening patches, and defense-in-depth mechanisms implemented across our active core repositories:

### 1. AuraTorrent (qBittorrent WebUI)
*Forked from VueTorrent and heavily hardened against client-side exploitation.*

* **Phishing & Open Redirect Patch (`src/pages/Login.vue`)**:
  * *Vulnerability*: The original upstream code routed users using `route.query.redirect` raw string values directly to `router.push()`. Attackers could exploit this to redirect authenticated users to external phishing domains.
  * *Mitigation*: Refactored `redirectOnSuccess` to validate that destination routes strictly begin with a single `/` and reject protocol-relative paths beginning with `//`. Safe fallback defaults to `{ name: 'dashboard' }`.
* **Credential Leakage Prevention (`src/pages/Login.vue`)**:
  * *Vulnerability*: Auto-login parsed credentials raw from query strings (`?username=...&password=...`), causing secrets to be saved in browser history, intermediate proxy access logs, and leaked via HTTP `Referer` headers.
  * *Mitigation*: Removed the mounting extraction block. Credentials must only be supplied via POST body forms.
* **Storage Namespace Isolation (`ImportSettingsDialog.vue`, `General.vue`)**:
  * *Design Flaw*: Reusing the upstream namespace `vuetorrent_webuiSettings` exposed client preferences to collision risks and session hijacking if other client variants shared the same hosting origin.
  * *Mitigation*: Migrated the setting state storage namespaces exclusively to `webuiSettings`.
* **Telegram Companion Bot Access Whitelist (`bot/main.py`)**:
  * *Vulnerability*: Unauthenticated message handlers would allow any Telegram user to request torrent lists or inject new torrent links into the daemon.
  * *Mitigation*: Wrapped all dispatcher command handlers in a strict `is_allowed()` verification function, comparing user IDs with the `ALLOWED_USERS` environment variable. Restricted administrative actions like `/add_user` exclusively to the owner ID (`ALLOWED_USERS[0]`).
* **Dependency Hardening**:
  * *Mitigation*: Automated NPM audits and updated high-severity dependency paths, pinning critical packages such as `js-cookie` (upgraded to `3.0.7`) to ensure zero active vulnerabilities.

---

### 2. Universal Retro Arcade (`retro-game-replicas`)
*Modern browser-based arcade launcher built with Tauri v2 and Phaser.*

* **Tauri v2 IPC Capability Scope (`capabilities/main.json`)**:
  * *Vulnerability*: Frontend webview environments could potentially invoke host-level commands, leading to arbitrary shell execution.
  * *Mitigation*: Enforces a minimized Tauri capabilities file, allowing only explicitly whitelisted Rust endpoints (e.g. read/write score records) and disabling arbitrary command execution.
* **PostFX Shader Bounds Checking (`src/scenes/LobbyScene.ts` / GLSL Shaders)**:
  * *Vulnerability*: Improper calculation matrices in the custom CRT post-processing shader could trigger out-of-bounds GPU reads or WebGL context failures, crashing the browser tab (local DoS).
  * *Mitigation*: Clamped resolution coordinate floats and validated boundary matrices inside the shader rendering pass.
* **IndexedDB Score Verification & State Clamping**:
  * *Vulnerability*: Locally stored game scores could be spoofed or modified to cause database buffer overflows or injection of scripts.
  * *Mitigation*: Extracted score values are parsed as strict integers, ran through positive boundary clamps, and HTML-escaped before rendering in high-score overlays to prevent persistent XSS.

---

### 3. AuraOS (`aura-os`)
*Enterprise-grade cloud storage and NAS operating system.*

* **mDNS Local Spoofing Protection (`service/system.go`)**:
  * *Vulnerability*: In local area networks, spoofed multicast DNS responder advertisements can trigger domain hijacking and intermediate MitM sniffing.
  * *Mitigation*: The networking stack validates responder source MAC addresses against the host's ARP table before registering hosts, ignoring untrusted endpoints.
* **Docker Socket Hardening & Access Control**:
  * *Vulnerability*: Mount-sharing the host Docker socket `/var/run/docker.sock` exposes the OS to root-level privilege escalation.
  * *Mitigation*: AuraOS routes Docker control plane queries via a local-loopback TCP port secured by Mutual TLS (mTLS) with client certificates. Deployed containers run under non-root context constraints with CPU/Memory limits.
* **ZFS Dataset Import Policies (`service/zfs.go`)**:
  * *Vulnerability*: Importing external pools can execute malicious SUID scripts or binaries.
  * *Mitigation*: AuraOS imports all non-root storage pools using strict `noexec` and `nosuid` verification rules. Additionally, input sanitization rejects ZFS identifier strings containing control symbols by applying strict regex formatting checks (`zfsIdentRe`).

---

### 4. StealthMatrix Bot (`stealth-matrix`)
*Self-hosted Telegram e-commerce automation bot.*

* **Middlewares Input Sanitization (`middlewares.py`)**:
  * *Vulnerability*: Arbitrary user strings passed to Telegram HTML parser modes could cause tag injection, and long strings could invoke CPU exhaustion or ReDoS attacks.
  * *Mitigation*: Implements `RateLimitMiddleware` (sliding window: max 8 queries/10s per user) and `SanitizeMiddleware` (removes HTML tags via bounded regex `<[^>]{0,200}>` to prevent ReDoS, blocks `javascript:`/`data:` schemes, and truncates text to 512 characters).
* **Parameterized SQLite Queries (`database.py`)**:
  * *Vulnerability*: Injection of malicious SQL sequences via product search queries or checkout notes.
  * *Mitigation*: Parameterized all SQL statements (`?` bindings) and implemented database-level `CHECK` constraints (e.g. `price >= 0`) along with transaction wrapper safety clamps.
* **Payment Signature Verification**:
  * *Vulnerability*: Spoofed payment payload callbacks could trick the handler into fulfilling orders without valid transaction tokens.
  * *Mitigation*: Fully validates `PreCheckoutQuery` IDs and hashes against official Telegram API webhook endpoints before processing.

---

### 5. Universal Platform Engineering (`universal-platform-engineering`)
*Zero-Trust GitOps orchestration and Cloud Delivery infrastructure.*

* **Mutual TLS Service Mesh**:
  * *Mitigation*: Enforces strict mTLS traffic policies via service mesh overlays, securing communication routes between internal components.
* **GitOps RBAC Rules**:
  * *Mitigation*: Deployments are automated strictly using namespace-scoped ArgoCD accounts. Direct CLI permissions on workloads are blocked.
* **AWS Secrets Manager Envelope Encryption**:
  * *Mitigation*: Secrets are injected at runtime using KMS envelope encryption keys. No plaintext configurations are stored in Git.
* **Hardened Terraform State Storage**:
  * *Mitigation*: Remote tfstates are encrypted using AES256 inside private S3 buckets with public access blocked and DynamoDB locking.

---

## 🛠️ DevOps Showcase Projects (Junior level)

Our DevOps interview sandbox repositories follow these security baselines:
* **`k8s-app-delivery`**: Executes containers under non-root UIDs (`10001`), drops kernel capabilities via `securityContext`, and validates Dockerfiles and images via `hadolint` and `trivy` in the CI pipeline.
* **`terraform-aws-bootstrap`**: Configures AWS VPC subnets with NAT routing (no direct SSH port 22 exposed to the public), enforces IMDSv2 tokens, enables S3 encryption, and verifies configurations via `checkov` and `tflint`.
