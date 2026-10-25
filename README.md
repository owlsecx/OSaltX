# 🦉 OSaltX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OCore-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
