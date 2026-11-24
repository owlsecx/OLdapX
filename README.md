# 🦉 OLdapX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OReconnaissance-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OLdapX** — Offline LDAP / Directory Config Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

OLdapX is an offline LDAP / directory configuration auditor covering slapd.conf, cn=config, 389-ds/FreeIPA, ApacheDS, ldap.conf, nslcd, pam_ldap, and sssd. It flags anonymous bind, TLS/StartTLS, ACL, rootpw, syncrepl, and LDIF hash issues, with optional consented live anonymous-bind/RootDSE probe. Reports export to TXT, Markdown, JSON, CSV, or SARIF.

---

## ✨ Features

- Parsers for slapd.conf, slapd.d/cn=config, 389-ds/FreeIPA dse.ldif, ApacheDS, ldap.conf, nslcd, pam_ldap, sssd
- Checks for anon-bind, TLS/StartTLS, ciphers, TLS_REQCERT, rootpw, olcAccess/aci, limits, syncrepl, LDIF hashes
- CWE + MITRE ATT&CK mapping with severity and remediation text
- Offline `--root` tree audit and local `--scan`; secret masking by default
- Optional consented `--probe` for anonymous bind + RootDSE (requires `--i-am-authorized`)
- TXT / MD / JSON / CSV / SARIF export and `--demo` self-test

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OLdapX --scan --root ./fs
./OLdapX --slapd /etc/ldap/slapd.conf --ldif export.ldif --json report.json
./OLdapX --demo --list-rules
./OLdapX --help
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
sudo strace -f -e trace=network ./OLdapX --help   # watch every network call
firejail --net=none ./OLdapX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
