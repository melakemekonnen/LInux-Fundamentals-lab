# 🗺️ Session 01 — Linux Scavenger Hunt

## Overview

This repository documents the completion of **Session 01: The Scavenger Hunt**, a hands-on Linux navigation lab focused on mapping the Filesystem Hierarchy Standard (FHS), navigating system directories, and extracting hidden system intelligence using core terminal commands.

The lab was completed by **SSH-ing into a Linux VM using VS Code** (Remote - SSH extension), allowing all terminal work to be done directly from the VS Code integrated terminal over a secure remote connection.

---

## 🎯 Objectives

- Navigate the Linux filesystem using absolute and relative paths
- Explore restricted and hidden directories
- Extract system artifacts and document findings
- Push a discovery report to a GitHub portfolio

---

## 📁 Targets & Findings

### Target 1 — System Logs
- **Location:** `/var/log`
- **Files Verified:** `syslog`, `auth.log`

### Target 2 — Secret Mission
- **Location:** `/opt/alpha/mission.txt`
- **Contents:** Mission secure message (documented in `discovery.txt`)

### Target 3 — Hidden Token
- **Location:** `/var/tmp/.blackout/token.txt`
- **Contents:** Digital token value (documented in `discovery.txt`)

---

## 📄 Artifact

The findings were documented in `discovery.txt`.

---


## 🛡️ Session 02 — Linux Permissions & Hardening

## Overview

This section documents **Session 02**, a hands-on lab focused on diagnosing and fixing Linux permission misconfigurations using core security commands such as `chmod`, `chown`, and `ls`.

---

## 🎯 Objectives

- Audit file and directory permissions
- Repair restricted access using `chmod`
- Restore secure ownership using `chown`
- Automate remediation using a hardening script

---

## 📁 Targets & Fixes

### Target 1 — Vault Directory Lockout
- **Location:** `~/Vault`
- **Issue:** Directory had no permissions (`d---------`)
- **Fix Applied:** `chmod 700 ~/Vault`

### Target 2 — Locked Secret File
- **Location:** `~/Vault/secrets.txt`
- **Issue:** File could not be read
- **Fix Applied:** `chmod 600 ~/Vault/secrets.txt`

### Target 3 — System Identity File
- **Location:** `/etc/shadow`
- **Issue:** Permissions incorrectly set to `777`
- **Fix Applied:**  
  - `sudo chmod 640 /etc/shadow`  
  - `sudo chown root:shadow /etc/shadow`

---

## 📄 Artifact

The remediation steps were automated using **`harden.sh`**.

---

*Completed as part of a Linux fundamentals course — Session 02.*