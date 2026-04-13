# 🔐 Offensive Security Capstone — Lively-Events Platform Audit

**Candidate:** Thulile Masuku  
**Date:** April 2026  
**Client:** Lively-Events (Event Booking Platform)  
**Target:** `172.20.0.3` (Nginx Server)  
**Lead Consultant:** Sarah Mitchell  

---

## 📌 Project Overview

This repository documents the findings, methodology, and results of an offensive security capstone engagement conducted against the Lively-Events event booking platform. The objective was to simulate a real-world penetration test by identifying vulnerabilities and extracting 4 hidden flags to demonstrate system-level impact.

---

## 🎯 Objectives

- Perform system-level reconnaissance on the target server
- Navigate the Linux file system to locate hardware and environment identifiers
- Extract unique hardware identifiers from kernel-level DMI system classes
- Verify service availability of the target Nginx instance
- Document all findings in a structured, reproducible manner
- Synchronize deliverables with a remote GitHub repository

---

## 🗂️ Repository Structure

```
Offensive-Security-Capstone/
├── README.md                            # This file — project overview & quick reference
├── Final_CAPSTONE_REPORT.md             # Full technical report (Markdown)
└── Thulile_Masuku_Capstone_Report.pdf   # Full technical report (PDF, formatted)
```

---

## 🔍 Methodology

### 1. System Reconnaissance
Navigated the Linux file system to locate hardware-level configuration files exposed by the kernel via the `/sys/class/dmi/id/` directory.

### 2. Data Extraction
Successfully extracted the **Board Name/ID** (`234933`) from the DMI system class — a unique hardware identifier used to fingerprint the target environment.

### 3. Environment Isolation Verification
Confirmed isolation between the Dockerized lab environment and the local Kali Linux host by running targeted searches that returned null results on the host — validating the integrity of the lab setup.

### 4. Service Verification
Confirmed the target Nginx web server was **active and running** via `service nginx status`.

### 5. Documentation & Version Control
All findings were documented, committed, and pushed to this repository following Git best practices.

---

## ✅ Results Summary

| Task | Status |
|------|--------|
| Hardware ID Extracted | ✅ `234933` |
| Nginx Service Verified | ✅ Active (running) |
| Environment Isolation Confirmed | ✅ |
| Repository Synced | ✅ |
| Overall Capstone Status | ✅ **Completed Successfully** |

---

## 💻 Key Commands

```bash
# Navigate to kernel hardware identification directory
cd /sys/class/dmi/id/

# Extract board name (unique hardware identifier)
cat board_name
# Output: 234933

# Verify target web server is running
service nginx status
# Output: active (running)
```

---

## 🔐 Authentication Notes

GitHub Personal Access Token (Classic) was used for repository authentication after standard password authentication was deprecated by GitHub's security policy. The token was generated with `repo` scope and used in place of a password during `git push`.

---

## ⚠️ Disclaimer

This engagement was conducted in a controlled, authorized lab environment as part of an educational capstone programme. All actions were performed with explicit permission. No production systems were accessed or harmed.

---

## 👤 Author

**Thulile Masuku**  
Offensive Security Capstone — April 2026
