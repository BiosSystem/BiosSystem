# BiosSystem Global Security Policy

Security is a core design requirement across the entire BiosSystem portfolio of projects, covering WebUI frontends, arcade engines, NAS operating systems, e-commerce automation, and cloud infrastructure pipelines.

This document serves as the central security coordination policy for all repositories hosted under the `BiosSystem` organization/user profile.

---

## 📞 Reporting a Vulnerability

If you discover a security vulnerability in any BiosSystem project, please report it immediately. To protect our users and infrastructure, **do not open public issues on GitHub**.

* **Email**: Send your reports to `security@bios_system.io`
* **Response SLA**:
  * **Acknowledgement**: Within 24 hours.
  * **Remediation Plan**: Within 3 business days.
  * **Disclosure**: Coordinated with the reporter after patches are deployed.

---

## 🔒 Security Architectures & Fixes Matrix

Below is the consolidated history of security audits, hardening patches, and defense-in-depth mechanisms implemented across our projects.

### 1. AuraTorrent (qBittorrent WebUI)
*Forked from VueTorrent and heavily hardened against client-side exploitation.*

* **Phishing & Open Redirect Patch (`Login.vue`)**: Refactored the `redirectOnSuccess` handler to validate destination URLs. The app rejects absolute URLs and protocol-relative links (e.g. `//evil.com`), preventing phishing redirect campaigns.
* **Credential Leakage Prevention (`Login.vue`)**: Removed query parameter auto-extraction on mount. The system no longer permits credentials inside the URL path (e.g. `?username=...&password=...`), protecting credentials from browser history and proxy logging.
* **Storage Namespace Isolation**: Migrated local storage namespaces from `vuetorrent_webuiSettings` to an isolated `webuiSettings` namespace to prevent storage conflicts or cross-application configuration hijacking on shared domains.
* **AuraBot Access Controls**: Implemented a strict `ALLOWED_USERS` whitelist checks in the Telegram companion bot dispatcher. Administrative commands (like `/add_user`) are strictly limited to the primary owner (`ALLOWED_USERS[0]`), preventing unauthorized remote access to the seedbox.
* **Dependency Hardening**: Enforced continuous dependency audits, locking packages like `js-cookie` (upgraded to `3.0.7`) to maintain a clean `npm audit` report with zero vulnerabilities.

### 2. Universal Retro Arcade (`retro-game-replicas`)
*Modern browser-based arcade launcher built with Tauri v2 and Phaser.*

* **Tauri v2 IPC Isolation**: Enforced a minimized capability profile (`capabilities/main.json`). Webview contexts are strictly prohibited from executing arbitrary host-level shell commands; only whitelisted Rust calls are allowed.
* **PostFX Shader Bounds Checking**: Validates rendering boundaries and coordinate matrices within the GLSL CRT scanline shader to prevent canvas buffer overflows and browser tab crashes (local denial of service).
* **IndexedDB Anti-Tampering**: High scores and save states are validated against strict types and positive integer clamps upon load, preventing high score injection or scripting attacks.

### 3. AuraOS (`aura-os`)
*Enterprise-grade cloud storage and NAS operating system.*

* **mDNS Local Spoofing Protection**: Network stack validates incoming multicast DNS (mDNS) responder MAC addresses against the local ARP table before registering hosts, neutralising local MitM domain hijacking.
* **Docker Socket Hardening**: The control plane interfaces with the Docker engine via a local-loopback-only TCP socket protected by Mutual TLS (mTLS) with client certificates. Deployed user containers are stripped of root privileges and bound to resource quotas.
* **ZFS Verification Rules**: Automatically applies security mount flags (`noexec`, `nosuid`) on non-root storage datasets to prevent arbitrary execution of imported filesystem scripts.

### 4. StealthMatrix Bot (`stealth-matrix`)
*Self-hosted Telegram e-commerce automation bot.*

* **Middlewares Input Sanitization**: Implements regex sanitization to strip HTML/XML tags, restrict `javascript:` protocol schemas, and truncate messages to 512 characters.
* **Sliding Window Rate Limiting**: The custom `RateLimitMiddleware` limits messaging rates to at most 8 queries per 10-second window per user, mitigating API flooding.
* **SQL Injection Mitigation**: All SQLite transactions are fully parameterized. Column boundaries are protected by SQLite `CHECK` database constraints.
* **Payment Validation**: Validates `PreCheckoutQuery` transaction IDs and checksum hashes directly against official Telegram API responses before fulfilling store orders.

### 5. Universal Platform Engineering (`universal-platform-engineering`)
*Zero-Trust GitOps orchestration and Cloud Delivery infrastructure.*

* **Service Mesh Isolation**: Enforces mutual TLS (mTLS) traffic encryption and authorization policies between all Kubernetes microservices.
* **GitOps RBAC Rules**: Deployments are automated strictly via ArgoCD namespace-scoped service accounts, preventing cluster privilege escalation.
* **Runtime Envelope Encryption**: Secrets are dynamically injected into pods at runtime via AWS Secrets Manager using KMS envelope encryption keys, keeping plaintext secrets out of git.
* **Terraform State Security**: State files are stored in private, encrypted S3 buckets with DynamoDB state locking enabled to prevent race conditions.

---

## 🛠️ DevOps Showcase Projects (Junior level)

Our dedicated DevOps interview reference projects are configured with modern security defaults:

* **`k8s-app-delivery`**: Builds multi-stage containers executing as non-root `UID 10001` with Kubernetes `securityContext` restrictions (dropping kernel privileges) and automated `trivy`/`hadolint` CI scanning.
* **`terraform-aws-bootstrap`**: Configures AWS VPC subnets with strict egress-only NAT routing, EC2 instances restricted to AWS Systems Manager (SSM) Session Manager (no SSH port 22 exposed), IMDSv2 metadata enforcement, encrypted S3 storage buckets, and automated `checkov` static security scans.
