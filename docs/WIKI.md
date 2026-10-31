# BiosSystem profile repository

## Architecture
This repository holds the GitHub profile page (`README.md`) and the account-wide security policy (`SECURITY.md`). It contains no application code.

## Features
- The profile lists the public repositories (AuraTorrent, Winnow, OriginalMS, retro-game-replicas) and links to the products running on [bios-system.net](https://bios-system.net).
- Private projects are described only by what a visitor can use. Their code, infrastructure and security internals are not documented here.

## Deployment
GitHub renders `README.md` directly on the profile. CI checks the Markdown on every pull request.

## Security
Report vulnerabilities privately through GitHub Security Advisories on the affected repository. See [SECURITY.md](../SECURITY.md).
