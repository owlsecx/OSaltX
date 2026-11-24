# 🦉 OSaltX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSaltX** — SaltStack Configuration-Hardening Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OSaltX is an offline, read-only configuration-hardening auditor for SaltStack. It parses salt-master, salt-minion, salt-api, pillar and state files to flag insecure key acceptance, weak eAuth/ACL settings, plaintext secrets and known CVEs. Secrets are masked and findings map to CWE and MITRE.

---

## ✨ Features

- Stdlib YAML-subset parser that skips and flags Jinja lines
- Master checks for auto_accept, open_mode, ACL/eauth wildcards, peer and gitfs settings
- Minion checks for master fingerprint, key verification and autosign grains
- salt-api TLS, webhook auth and token-lifetime review
- Pillar plaintext-secret detection (gpg-aware, masked) and state cmd.run injection checks
- Version-based CVE check (CVE-2020-11651/11652 and later) with TXT/MD/JSON/CSV/SARIF export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSaltX --scan --root /mnt/collected
./OSaltX --salt-version 3006.1 --sarif -o report.sarif
./OSaltX -r / --fail-on high
./OSaltX --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OSaltX --help   # watch every network call
firejail --net=none ./OSaltX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
