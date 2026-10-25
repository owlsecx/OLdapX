# 🦉 OLdapX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OReconnaissance-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
