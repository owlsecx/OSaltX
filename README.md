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

SaltStack master / minion / salt-api / pillar / state / PKI configuration-hardening auditor

---

## ✨ Features

- Stdlib YAML-subset parser (maps, lists, flow, block scalars, renderer shebangs); Jinja lines skipped & flagged
- Master — auto_accept, autosign_file / grains, open_mode, publisher_acl / external_auth / client_acl wildcards, eauth pam broad groups, peer / peer_run, file_recv, pillar_opts, interface exposure, user root, gitfs / git_pillar transport, rotate_aes_key, reactor wildcards
- Minion — master_finger, verify_master_pubkey_sign, open_mode, mine cmd.run, autosign_grains
- salt-api — rest_cherrypy / rest_tornado TLS, webhook auth, netapi clients, token lifetime
- Pillar plaintext secrets (gpg renderer aware, masked), State cmd.run Jinja injection, insecure sources, gpgcheck
- PKI dir 0700 / key-file permission audit; transport TLS
- Version check vs CVE-2020-11651 / 11652 and later CVEs
- Export TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Self-test --demo, CI gates --fail-on / --min-severity

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSaltX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
