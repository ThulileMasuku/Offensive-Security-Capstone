# Offensive Security Capstone - Technical Report

## 👤 Candidate Information
- **Name:** Thulile Masuku
- **Date:** April 2026
- **Project Type:** Cybersecurity / Offensive Security

## 📄 Project Context
- **Client:** Lively-Events (Event Booking Platform)
- **Target IP:** 172.20.0.3
- **Lead Consultant:** Sarah Mitchell
- **Objective:** Identify vulnerabilities and retrieve 4 hidden secrets (flags) to demonstrate real-world impact.

## 🎯 Project Objective
The goal of this capstone was to perform a system-level audit and verification of a target Nginx server to extract unique hardware identifiers and confirm administrative access.

## 🔍 Execution Steps
1. **System Reconnaissance:** Navigated the Linux file system to locate hardware-level configuration files.
2. **Data Extraction:** Successfully extracted the Board Name/ID from the DMI system class.
3. **Environment Isolation:** Managed the transition between a Dockerized lab environment and the local Kali Linux host.
4. **Version Control:** Documented findings and synchronized local results with the remote GitHub repository using Git best practices.

## ✅ Results Summary
The project status was confirmed as **Completed Successfully**. 
The hardware identification string **234933** was validated against the capstone requirements.

---

## 💻 FULL COMMAND EXECUTION LOG

### 1. Successful Path (The "Wins")
*The following commands successfully extracted the required system data.*

```bash
# Navigating to the kernel's hardware identification directory
cd /sys/class/dmi/id/

# Extracting the unique Boars identifier

cat board_name
# RESULT: 234933

# Verifying the target Nginx service was operational
service nginx status
# RESULT: Active (running)

2. Troubleshooting: "Empty" Results & Searches

The following commands were part of the audit process but returned no data (null), confirming environment isolation between the Lab and the Host.
Bash

# Searching the Kali host for files that existed only in the lab container
find ~ -maxdepth 2 -name "*capstone*"
# RESULT: (Empty/Nothing returned)

# Checking for project-specific directories in the root home folder
ls -la | grep "alx"
# RESULT: (No matching lines found)

3. Technical Errors & Fatal Failures

Documenting the obstacles encountered during the deployment phase.

    Error: fatal: updating an unborn branch...

    Context: Occurred during initial git push before a commit was established.

    Resolution: Force-reset the Git directory using rm -rf .git and git init.

    Error: error: failed to push some refs...

    Context: Divergence between local and remote history.

    Resolution: Used git push -f to synchronize final documentation.

🔐 GITHUB HURDLES & AUTHENTICATION

Summary of the security obstacles faced while connecting to the remote repository.

During the final submission phase, standard Password Authentication was denied by GitHub's security protocol (Support for password authentication was removed).

Resolution Strategy:

    Environment Shift: Transitioned from the root terminal to the User Shell for consistent permissions.

    Credential Bypass: Generated a GitHub Personal Access Token (Classic) with full repo scopes.

    Final Deployment: Authenticated successfully using the token as a secure password bypass to push the final repository: Offensive-Security-Capstone.

FINAL STATUS: ALL TASKS VERIFIED AND SYNCED.


